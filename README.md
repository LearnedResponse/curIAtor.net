# curiator.net

Static public site and Caddy ingress configuration for `curiator.net`.

- `/` serves this repository from `/var/www/curiator.net`.
- `/gallery/` serves the collection directory.
- `/gallery/sietch/`, `/gallery/aviato/`, `/gallery/geometry/`, and `/gallery/ot/` preserve their
  public prefixes while proxying to private tunnel ports `8210`, `8310`, `8420`, and `8430`.
- Public-site assets use `/site-assets/`; each shell owns all routes beneath its configured base path.
- Caddy owns ACME certificates, HTTP-to-HTTPS redirects, compression, and access-log rotation.

The VM must never expose gallery upstream ports. WireGuard or an encrypted reverse tunnel should bind
all four upstreams only on VM loopback.

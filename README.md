# curiator.net

Static public site and Caddy ingress configuration for `curiator.net`.

- `/` serves this repository from `/var/www/curiator.net`.
- `/gallery/` proxies to the private gallery tunnel at VM loopback port `8210`.
- curIAtor's root-relative shell routes are reserved explicitly; public-site assets use `/site-assets/`.
- Caddy owns ACME certificates, HTTP-to-HTTPS redirects, compression, and access-log rotation.

The VM must never expose port `8210`. A WireGuard or encrypted reverse tunnel should bind the gallery
upstream only on `127.0.0.1:8210`.

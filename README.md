# vedanthvasudev.dpdns.org

Personal site for Vedanth Vasudev. Static HTML, no build step. Hosted on GitHub Pages at [vedanthvasudev.dpdns.org](https://vedanthvasudev.dpdns.org).

## Local preview

```bash
python3 -m http.server 8765
```

Open `http://127.0.0.1:8765/`.

## Deploy

Push `main` to GitHub. Pages is set to deploy from `main` `/ (root)`. Custom domain is set via `CNAME`.

## DNS

Cloudflare nameservers on the DigitalPlat domain. Apex CNAME flattened to `vedanthvdev.github.io` (DNS only until HTTPS cert is ready).

# vedanthvasudev.dpdns.org

A simple static placeholder site, ready to deploy on GitHub Pages with a custom domain.

## Files

- `index.html` — self-contained placeholder page (no build step).
- `CNAME` — tells GitHub Pages to serve the site at `vedanthvasudev.dpdns.org`.

## Deploy on GitHub Pages

1. Create a GitHub repo and push these files:
   ```bash
   git init
   git add .
   git commit -m "Add placeholder site"
   git branch -M main
   git remote add origin https://github.com/vedanthvdev/vedanthvasudev.dpdns.org.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
3. Under **Custom domain**, confirm it shows `vedanthvasudev.dpdns.org` (from the `CNAME` file) and enable **Enforce HTTPS** once the cert is issued.

## DNS setup (Cloudflare, delegated from DigitalPlat)

DigitalPlat delegates the domain to your external nameservers; you manage records in Cloudflare.

In your DigitalPlat dashboard, set the two Cloudflare nameservers for `vedanthvasudev.dpdns.org`.

Then in Cloudflare, add records pointing to GitHub Pages:

| Type  | Name                     | Value                    |
|-------|--------------------------|--------------------------|
| CNAME | vedanthvasudev.dpdns.org | `vedanthvdev.github.io`  |

Or, if using an apex-style setup, four `A` records to GitHub Pages IPs:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Set the record to **DNS only** (grey cloud) initially so GitHub can issue the TLS certificate, then you may enable proxying if desired.

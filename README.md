# Kartify landing page

Static marketing site for the root domain **thekartify.com**. Single page,
premium/minimal, seller-focused. One CTA everywhere → `app.thekartify.com`.

- `public/index.html` — the whole site (inline CSS + a small theme-toggle script).
- `wrangler.toml` — Cloudflare Worker (static assets); routes `thekartify.com/*`
  and `www.thekartify.com/*`.

No build step. Deploy via Cloudflare Workers (Git-connected):
- **Build command:** _(leave empty)_
- **Deploy command:** `npx wrangler deploy`

The apex needs a proxied DNS record (`@` A → `192.0.2.1`, proxied) so the Worker
route fires; the Worker intercepts before the dummy origin is ever used.

Edit copy/design in `public/index.html` and push — Cloudflare rebuilds.

# basf-xarvio

- Node 20+ supported with the pinned local `wrangler@3.91.0`
- `npm run dev` - local dev server with live reload
- `npm run deploy` - deploy to Cloudflare
- Prereq: `wrangler login` once, first time only

## Deployment & Domains

Custom domain routing is managed in the Cloudflare dashboard, not in `wrangler.jsonc`. To view or change routes, go to Workers & Pages → basf-xarvio → Domains.

Do not add a `routes` array to `wrangler.jsonc`. If routes are declared in both places, Wrangler and the dashboard will conflict on deploy. The dashboard is the source of truth.

Currently configured domains are `xconnect.purchasingportal.us`, the primary production URL and intended long-term public URL for BASF/xarvio customers; `koprix.com`, the backup domain used when the primary is blocked by a corporate filter; and `basf-xarvio.adam-eaa.workers.dev`, the default `workers.dev` URL used as a last-resort fallback.

BASF corporate IT blocked `xconnect.purchasingportal.us` in March 2026 under a new-domain filter. The `workers.dev` URL was used as a fallback. As of July 2026 the primary domain should be re-tested.

Content updates: any text or image changes go in `public/index.html`. Edit locally, run `npm run dev` to preview, then `npm run deploy` to ship. There is no CMS.

# naga docs redirect

This repo is intended to be deployed to Vercel and **only** redirects:

- `https://naga.developer.litprotocol.com/*`
  → `https://developer.litprotocol.com/*`

The full path (and query string) is preserved.

## Deploy (Vercel)

1. Create a new Vercel project and import this folder/repo.
2. Deploy (no build settings needed; this is config-only).
3. In the Vercel project, go to **Settings → Domains** and add:
   - `naga.developer.litprotocol.com`
4. Update DNS for `naga.developer.litprotocol.com`:
   - If you can use a CNAME:
     - `naga.developer` CNAME → `cname.vercel-dns.com.`
   - If you must use an A record (apex-only scenarios):
     - follow the Vercel UI instructions for the correct A record target(s)

## What it does

Configured in `vercel.json`:

- Any request to `/anything/here` redirects permanently to
  `https://developer.litprotocol.com/anything/here`


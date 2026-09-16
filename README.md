# mwk.dev

Static portfolio site. No build step — Vercel serves `public/` as-is.

## Deploy (first time)

```bash
npm i -g vercel
cd mwk-dev
vercel            # answer the prompts, accept defaults
vercel --prod     # production deploy → you get a *.vercel.app URL
```

Or push this folder to GitHub and import the repo at vercel.com/new. Every push to `main` auto-deploys.

## Connect mwk.dev (Porkbun)

1. Vercel → Project → Settings → Domains → add `mwk.dev` and `www.mwk.dev`.
2. Vercel shows you the records. In Porkbun DNS, delete the parking records and add:
   - `A`     `@`    → `76.76.21.21`
   - `CNAME` `www`  → `cname.vercel-dns.com`
3. Wait a few minutes; Vercel issues the TLS cert automatically (.dev requires HTTPS — handled).

## Before going live

- Drop your resume at `public/resume.pdf`
- Replace the `#` links for LinkedIn and "Book 20 minutes" in `public/index.html`
- Set up email forwarding for `hello@mwk.dev` (Porkbun has free forwarding) or change the address

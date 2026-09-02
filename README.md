# Akagawa LLC — website

Brand landing page for Akagawa LLC (general distribution / e-commerce), ready to publish on GitHub Pages with the custom domain `akagawagroup.com`.

## Package contents

- `index.html` — the full page (HTML + CSS + JS in one file, no external dependencies beyond Google Fonts).
- `CNAME` — required so GitHub Pages serves the site at `akagawagroup.com` instead of `username.github.io`.

## Before you publish: connect the contact form

The contact form posts to `https://formspree.io/f/YOUR_FORM_ID` — a placeholder. It won't deliver messages until you connect it:

1. Go to formspree.io and create a free account.
2. Create a new form, using `contact@akagawagroup.com` (or whatever inbox should receive submissions) as the destination.
3. Formspree gives you a unique endpoint like `https://formspree.io/f/abcdwxyz`.
4. In `index.html`, find the line with `action="https://formspree.io/f/YOUR_FORM_ID"` and replace `YOUR_FORM_ID` with your real ID.
5. Formspree's free tier covers 50 submissions/month, which is plenty for a launch. No backend or server needed — it works with a static GitHub Pages site as-is.

(Any similar static-form service — Netlify Forms, Getform, Basin — works the same way if you'd rather use one of those.)

## How to publish on GitHub Pages

1. In this repo, go to Settings → Pages.
2. Under "Build and deployment" → "Source", choose Deploy from a branch, branch `main`, folder `/ (root)`. Save.
3. GitHub will give you a URL like `https://ariosgarriga.github.io/akagawa/`. Wait 1–2 minutes for it to go live.
4. Connect the custom domain: in the same Pages panel, under "Custom domain" enter `akagawagroup.com` and save (already pre-set by the `CNAME` file, but GitHub asks for it in the UI too).
5. At your domain registrar (GoDaddy, Namecheap, etc.), add these DNS records:
   - An A record for `@` pointing to GitHub Pages' IPs: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - A CNAME record for `www` pointing to `ariosgarriga.github.io`
6. Check "Enforce HTTPS" in GitHub once DNS has propagated (can take up to 24h, usually minutes).

## Editing the content

Everything lives in `index.html` — no build step, no dependencies to install. Every push to `index.html` on the `main` branch republishes automatically within 1–2 minutes.


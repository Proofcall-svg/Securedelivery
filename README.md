# ProofCall website

Static site (`index.html`) + one serverless function (`api/early-access.js`).

## Current setup (GitHub Pages + Formspree)
The live early-access form in `index.html` submits to Formspree (https://formspree.io/f/mvkkvwjg) and works on GitHub Pages with no backend. The `api/` folder and `.env.example` are an optional alternative backend for Vercel (Resend + Upstash) and are not used by the GitHub Pages site.

## Optional Vercel backend
Validates the email, blocks bots (honeypot) and duplicate emails, stores each application in Upstash Redis, then emails it to the owner via Resend. To use it, point the form's `action` at `/api/early-access` and:
1. Create a Resend account and API key, verify a sending domain, and set `FROM_EMAIL`.
2. Create an Upstash Redis database and copy the REST URL and token.
3. Set `OWNER_NOTIFICATION_EMAIL`, add the 5 variables from `.env.example` in Vercel, and deploy.

## Before launch
Replace the contact placeholders and the Privacy Policy / Terms links in the footer.

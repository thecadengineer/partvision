PARTVISION COMPLETE STATIC DEPLOYMENT

1. Replace partvision.co.uk in index.html, robots.txt, sitemap.xml and worker/wrangler.toml.
2. Replace all [BRACKETED] legal placeholders in privacy.html and terms.html.
3. Upload all root files to the repository root.
4. GitHub Settings > Pages > Deploy from branch > main > /(root).
5. The public website has no build process and no external runtime dependencies.

BACKEND
1. Create a Cloudflare R2 bucket named partvision-uploads.
2. In worker/: run `npx wrangler secret put RESEND_API_KEY`.
3. Verify FROM_EMAIL with Resend.
4. Deploy the Worker with Wrangler.
5. Put the Worker URL in index.html: window.PARTVISION_API_URL="https://...workers.dev".
6. Add lifecycle deletion to R2 to match the published retention schedule.
7. Add Turnstile and rate limiting before public launch.

LEGAL/OPERATIONS
The privacy and terms files are careful drafts, not final legal advice. They deliberately preserve statutory rights and mark required business details. Ensure the actual systems, processors, retention, CAD ownership, cancellation workflow, tolerances and guarantee match the published wording.

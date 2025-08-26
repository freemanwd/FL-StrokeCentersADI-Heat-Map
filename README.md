Jacksonville Stroke Program + ADI Map — Deployment Guide
========================================================

Files
-----
- index.html  ← the interactive map (open this)
- fl_natrank.pdf (optional) ← PDF panel used by the map if present

Quickest hosting options (static site)
--------------------------------------
1) Netlify (no code; 1–2 minutes)
   • Rename nothing—this package already has index.html.
   • Go to https://app.netlify.com/drop and DROP the zip from below.
   • Netlify gives you a live URL like https://<your-site>.netlify.app
   • (Optional) Set a custom subdomain in Site settings → Domain management.

2) GitHub Pages
   • Create a new public repo.
   • Upload index.html (and fl_natrank.pdf, if you want the PDF panel).
   • Settings → Pages → Build and deployment → Deploy from a branch → select main / root.
   • Your map will be at https://<username>.github.io/<repo>/

3) Amazon S3 (static website hosting)
   • Create an S3 bucket (us-east-1 is fine), enable “Static website hosting.”
   • Upload index.html (and fl_natrank.pdf).
   • Set index document to index.html. Make objects public-read via a bucket policy.
   • (Optional) Put CloudFront in front for HTTPS/custom domain.

4) Vercel
   • New Project → “Other” → drag this folder or link a repo with index.html.
   • Accept defaults. The live URL appears like https://<project>.vercel.app

Embedding elsewhere
-------------------
Use an iframe on any webpage or WordPress post:
<iframe src="https://YOUR_HOST/index.html" width="100%" height="720" style="border:0;"></iframe>

Notes
-----
• The map is self-contained; the GeoJSON is inlined. Only the optional PDF is loaded as a separate file.
• If you don’t want the PDF panel, you can remove fl_natrank.pdf; the map still works.

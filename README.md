# Cleaning Company Blueprint — Deploy-Ready Site

This folder contains the full website ready to deploy to Netlify, Vercel, Cloudflare Pages, or any static host.

## Folder structure

```
site/
├── index.html               (home — cleaningcompanyblueprint.com)
├── inner-circle/index.html  (Inner Circle waitlist)
├── about/index.html
├── videos/index.html
├── newsletter/index.html
├── products/index.html
├── tools/index.html
├── book-a-call/index.html
├── webinar-july-1/index.html
└── images/                  (all photos, including mentor headshots)
```

When deployed, URLs become:
- cleaningcompanyblueprint.com/
- cleaningcompanyblueprint.com/inner-circle
- cleaningcompanyblueprint.com/about
- cleaningcompanyblueprint.com/videos
- cleaningcompanyblueprint.com/newsletter
- cleaningcompanyblueprint.com/products
- cleaningcompanyblueprint.com/tools
- cleaningcompanyblueprint.com/book-a-call
- cleaningcompanyblueprint.com/webinar-july-1

## To deploy on Netlify (fastest path)

1. Go to netlify.com and sign in (free).
2. Click "Add new site" → "Deploy manually."
3. Drag this entire `site` folder into the upload area.
4. Netlify gives you a temporary URL like `dazzling-cookie-12345.netlify.app`. Open it to verify everything works.
5. Under "Domain settings," add `cleaningcompanyblueprint.com` as a custom domain.
6. Update DNS at your domain registrar to point at Netlify (Netlify shows the records).

## What still needs to happen before this is fully live

1. Beehiiv general newsletter form embed (currently a placeholder on home, newsletter, videos, and products pages).
2. The Vic-and-Jen photo could be re-upscaled in Krea with low creativity for less smoothing (current version works fine).
3. Stan Store direct product URLs (currently all link to the main storefront; specific URLs would improve products page conversion).
4. Draft ribbons in the top-right corner of every page should be removed before the public launch (just delete the `<div class="draft-ribbon">Draft Preview</div>` line from each file).

## Removing the draft ribbons before public launch

Run this from the site/ folder:

```bash
find . -name "*.html" -exec sed -i 's|<div class="draft-ribbon">Draft Preview</div>||g' {} \;
```

Or open each file and delete the line manually.

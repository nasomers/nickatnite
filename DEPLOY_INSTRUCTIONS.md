# The Structure - nickatnite.net Deployment

## Overview
Deploy this static site to Cloudflare Pages for nickatnite.net

## Files
- `index.html` - The complete single-page site (all CSS/JS inline)

## Deployment Steps for Claude Code

### Option 1: Wrangler CLI (Recommended)

```bash
# Install wrangler if not already installed
npm install -g wrangler

# Login to Cloudflare (will open browser for auth)
wrangler login

# Deploy to Cloudflare Pages
# From within this directory:
wrangler pages deploy . --project-name=nickatnite

# If the project doesn't exist yet, it will prompt to create it
# Select "Production" branch when asked
```

### Option 2: Direct Upload via Cloudflare Dashboard

1. Go to https://dash.cloudflare.com
2. Select the account
3. Go to Workers & Pages > Create application > Pages
4. Choose "Upload assets" (Direct Upload)
5. Name the project: `nickatnite`
6. Upload the contents of this directory
7. Deploy

### Custom Domain Setup

After deployment, connect the custom domain:

1. In Cloudflare Pages project settings
2. Go to "Custom domains"
3. Add `nickatnite.net`
4. Add `www.nickatnite.net` (optional)
5. DNS will auto-configure since domain is on Cloudflare

### Verification

After deploy, the site should be available at:
- `https://nickatnite.pages.dev` (Cloudflare default)
- `https://nickatnite.net` (after custom domain setup)

## Quick Deploy Command

```bash
cd /path/to/nickatnite-deploy && wrangler pages deploy . --project-name=nickatnite --branch=main
```

That's it - single HTML file, no build step needed.

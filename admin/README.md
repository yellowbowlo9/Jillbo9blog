# Decap CMS Setup for GitHub Pages

## Current Issue
Decap CMS requires OAuth authentication to work on GitHub Pages. The error you're seeing is because the site is trying to use Netlify's OAuth service, which no longer works since we migrated to GitHub Pages.

## Solutions

### Option 1: Use GitHub OAuth (Recommended for Production)

1. **Create a GitHub OAuth App**:
   - Go to https://github.com/settings/developers
   - Click "New OAuth App"
   - Fill in:
     - Application name: `Decap CMS for yellowbowlo9.github.io`
     - Homepage URL: `https://yellowbowlo9.github.io`
     - Authorization callback URL: `https://yellowbowlo9.github.io/admin/`
   - Save the Client ID and Client Secret

2. **Deploy OAuth Backend** (choose one):

   **Option A - Using Vercel** (Free):
   - Fork https://github.com/vencax/netlify-cms-github-oauth-provider
   - Deploy to Vercel
   - Add environment variables:
     - `OAUTH_CLIENT_ID`: Your GitHub OAuth Client ID
     - `OAUTH_CLIENT_SECRET`: Your GitHub OAuth Client Secret
   - Note the deployment URL

   **Option B - Using GitHub Actions**:
   - Use https://github.com/marketplace/actions/decap-cms-github-backend

3. **Update admin/config.yml**:
   ```yaml
   backend:
     name: github
     repo: yellowbowlo9/yellowbowlo9.github.io
     branch: main
     base_url: https://your-oauth-backend.vercel.app
   ```

### Option 2: Local Development Only

Use Decap Server for local editing:

```bash
npx decap-server
```

Then update `admin/config.yml` for local:
```yaml
backend:
  name: git-gateway
local_backend: true
```

### Option 3: Edit Content Directly in GitHub

Skip the CMS entirely and edit content files directly:
- Blog posts: `_posts/`
- Poetry: `_poetry/`
- Journal: `_journal/`
- Pages: `_pages/`

## Quick Fix to Try First

1. Clear your browser cache completely
2. Try accessing `/admin/` again
3. If you see the login button, click it and authorize with GitHub

If you want me to set up Option 1, I'll need you to create the GitHub OAuth App and deploy the backend first, then I can update the configuration.

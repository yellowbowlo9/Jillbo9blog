# Setting Up OAuth for Decap CMS on GitHub Pages

## Why You Need This

Decap CMS with GitHub backend requires an OAuth server to authenticate users. Without it, **the login button won't appear** on your admin page.

## Quick Setup (15 minutes) - FREE Forever

### Step 1: Create GitHub OAuth App

1. Go to https://github.com/settings/developers
2. Click **"New OAuth App"**
3. Fill in the form:
   - **Application name**: `Decap CMS - yellowbowlo9.github.io`
   - **Homepage URL**: `https://yellowbowlo9.github.io`
   - **Authorization callback URL**: `https://oauth-provider.vercel.app/callback`
     (This will change to your Vercel URL in Step 3)
4. Click **"Register application"**
5. **IMPORTANT**: Copy your **Client ID** (you'll see it immediately)
6. Click **"Generate a new client secret"**
7. **IMPORTANT**: Copy your **Client Secret** (you can only see this once!)

### Step 2: Deploy OAuth Backend to Vercel (FREE)

1. **Create a Vercel account** (if you don't have one):
   - Go to https://vercel.com
   - Sign up with your GitHub account (it's free)

2. **Deploy the OAuth provider**:
   - Visit: https://vercel.com/new/clone?repository-url=https://github.com/vencax/netlify-cms-github-oauth-provider
   - Click **"Clone"** or **"Deploy"**
   - When prompted, add these environment variables:
     - `OAUTH_CLIENT_ID`: Paste your Client ID from Step 1
     - `OAUTH_CLIENT_SECRET`: Paste your Client Secret from Step 1
   - Click **"Deploy"**

3. **Copy your Vercel URL**:
   - After deployment, you'll see something like: `https://your-project-name.vercel.app`
   - Copy this URL

### Step 3: Update GitHub OAuth App Callback

1. Go back to https://github.com/settings/developers
2. Click on your OAuth App
3. Update **Authorization callback URL** to:
   ```
   https://your-project-name.vercel.app/callback
   ```
   (Replace `your-project-name` with your actual Vercel URL)
4. Click **"Update application"**

### Step 4: Update Your Site Configuration

Edit `admin/config.yml` and uncomment these lines:

```yaml
backend:
  name: github
  repo: yellowbowlo9/yellowbowlo9.github.io
  branch: main
  base_url: https://your-project-name.vercel.app
  auth_endpoint: auth
```

Replace `your-project-name.vercel.app` with your actual Vercel URL.

You can also remove or comment out the `local_backend: true` line for production.

### Step 5: Commit and Push

```bash
git add admin/config.yml
git commit -m "Configure OAuth backend for Decap CMS"
git push
```

### Step 6: Test It!

1. Wait 1-2 minutes for GitHub Pages to rebuild
2. Visit https://yellowbowlo9.github.io/admin/
3. You should now see the **"Login with GitHub"** button!
4. Click it and authorize the app
5. Start editing your content! 🎉

## For Local Development

If you just want to test locally without setting up OAuth:

1. Install Node.js if you haven't already
2. Open terminal in your project directory
3. Run:
   ```bash
   npx decap-server
   ```
4. Visit http://localhost:8080/admin/
5. The login button will work locally (without OAuth)

## Troubleshooting

### "Login button still doesn't appear"
- Make sure you updated `admin/config.yml` with your Vercel URL
- Wait 1-2 minutes for GitHub Pages to rebuild
- Clear browser cache and try again

### "OAuth error" or "Redirect loop"
- Double-check your GitHub OAuth App callback URL matches your Vercel URL + `/callback`
- Make sure the Client ID and Secret in Vercel match your GitHub OAuth App
- Try redeploying on Vercel

### "Cannot read property of undefined"
- Your `base_url` in config.yml should NOT have a trailing slash
- Should be: `https://your-app.vercel.app` (correct)
- NOT: `https://your-app.vercel.app/` (wrong)

## Cost

- GitHub OAuth App: **FREE**
- Vercel hosting: **FREE** (Hobby plan includes everything you need)
- Total: **$0.00 forever**

## Security Notes

- Only you (the repo owner) can log in and edit content
- The OAuth backend only handles authentication, it doesn't store any data
- All your content stays in your GitHub repo
- You can revoke access anytime from GitHub settings

---

Need help? Open an issue on GitHub!

# 🎉 GitHub Pages Setup - NO MORE NETLIFY HOSTING!

Your blog is now configured to work 100% FREE on GitHub Pages with easy editing through a web interface. No coding needed!

**Your site is hosted on GitHub Pages (free), we just use a free OAuth service for login - no Netlify credit limits!**

## 🚀 Quick Setup (10 minutes total)

### Step 1: Enable GitHub Pages (2 minutes)
1. Go to your repository: https://github.com/yellowbowlo9/yellowbowlo9.github.io
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Source", select **Deploy from a branch**
5. Under "Branch", select **main** and **/ (root)**
6. Click **Save**
7. Wait 2-3 minutes for your site to deploy

Your blog will be live at: **https://yellowbowlo9.github.io**

### Step 2: Create GitHub OAuth App (5 minutes - ONE TIME ONLY)

This lets you log into your admin panel securely. Follow these EXACT steps:

1. **Go to GitHub Developer Settings:**
   - Visit: https://github.com/settings/developers
   - Click **OAuth Apps** in the left sidebar
   - Click **New OAuth App** button

2. **Fill in the form EXACTLY like this:**
   ```
   Application name: My Blog Admin
   Homepage URL: https://yellowbowlo9.github.io
   Authorization callback URL: https://decap-oauth-gateway.netlify.app/callback
   ```
   - Click **Register application**

3. **Get your Client ID and Secret:**
   - You'll see a **Client ID** - copy it
   - Click **Generate a new client secret**
   - Copy the secret (you'll only see this once!)
   - Keep both handy for next step

4. **Add to OAuth Gateway:**
   - Visit: https://decap-oauth-gateway.netlify.app
   - Click **"Configure Your App"**
   - Paste your **Client ID** and **Client Secret**
   - It will give you a special URL - save this!

5. **Update your config (or skip this - already done):**
   - Your `admin/config.yml` is already configured!
   - Just test it in the next step

### Step 3: Access Your Admin Panel
Once your site is live and OAuth is set up:
1. Go to: **https://yellowbowlo9.github.io/admin/**
2. Click **"Login with GitHub"**
3. Authorize the app (you'll only do this once)
4. You're in! 🎊

## 📝 How to Use Your Blog

### Creating Posts
1. Go to https://yellowbowlo9.github.io/admin/
2. Click **Blog Posts** in the sidebar
3. Click **New Blog Post**
4. Write your title and content
5. Click **Publish** → **Publish now**
6. Done! Your post is live in ~1 minute

### Creating Poetry
Same as above, but click **Poetry** instead of Blog Posts

### Creating Journal Entries
Same as above, but click **Daily Entries**

### Changing Colors & Site Settings
1. Go to the admin panel
2. Click **Site Settings** → **Configuration**
3. Change colors (just type hex codes or use a color picker), site title, description, etc.
4. Click **Publish**
5. Your changes appear in ~1 minute

## 🎨 Customization Made Easy

Everything is editable from the web interface at `/admin/`:
- ✅ Create/edit/delete blog posts
- ✅ Create/edit/delete poetry
- ✅ Create/edit/delete journal entries
- ✅ Change site colors (hex codes like #ff006e)
- ✅ Change site title & description
- ✅ Upload images (drag and drop)

**NO code editing needed!**

## 🆘 Troubleshooting

### "Login button loops or doesn't work"
**This is the issue you're having!** Here's the fix:

**Option A: Use the Official OAuth Gateway (EASIEST)**
1. I've already configured this for you
2. Just make sure you've created the GitHub OAuth App (Step 2 above)
3. Try logging in again at https://yellowbowlo9.github.io/admin/

**Option B: Super Simple Alternative (NO OAUTH SETUP NEEDED)**
If you don't want to mess with OAuth, there's an even simpler way:

1. **Edit directly on GitHub:**
   - Go to your repo: https://github.com/yellowbowlo9/yellowbowlo9.github.io
   - Navigate to `_posts/` folder
   - Click **Add file** → **Create new file**
   - Name it: `2025-11-20-my-first-post.md`
   - Add this content:
   ```markdown
   ---
   layout: post
   title: My First Post
   date: 2025-11-20
   ---

   Your blog content here!
   ```
   - Click **Commit changes**
   - Your post is live in 1-2 minutes!

2. **Even easier - Use GitHub's web editor:**
   - Press `.` (period key) while viewing your repo
   - This opens VS Code in your browser
   - Edit any file super easily
   - Save and commit - done!

### "Can't access /admin/"
- Make sure GitHub Pages is enabled (Step 1)
- Wait 2-3 minutes after enabling
- Try visiting your site first: https://yellowbowlo9.github.io

### "My changes aren't showing up"
- Wait 1-2 minutes (GitHub Pages needs to rebuild)
- Hard refresh your browser (Ctrl+Shift+R or Cmd+Shift+R)

### Still having issues with OAuth?
The OAuth gateway might be down. Here's a backup plan:
- Just edit files directly in GitHub (Option B above)
- OR use GitHub Desktop app
- OR use the web editor (press `.` in your repo)

## 💰 Cost

**$0.00 FOREVER**
- GitHub Pages: Free
- Decap CMS: Free & Open Source
- OAuth Gateway: Free
- No credit card needed
- No limits on posts or edits
- No Netlify hosting fees!

## 🔒 Security

- Only YOU can edit the blog (via GitHub login)
- All changes are saved to your GitHub repo
- Full version history of all changes
- Can undo any change anytime

## 🤔 Why We Still Use One Netlify Service

We're only using Netlify's free OAuth gateway (not hosting) because:
- It's a tiny service that handles login
- Completely free tier, no limits
- You're hosting on GitHub Pages (also free)
- No credit card required
- Alternative: Set up your own OAuth (more complex)

**You've escaped Netlify hosting costs!** The OAuth gateway doesn't count toward any limits.

---

**You're all set!** Just enable GitHub Pages, create the OAuth app (or skip and edit on GitHub directly), and start blogging! 🚀

Questions? Issues? Just ask!

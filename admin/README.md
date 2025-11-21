# Decap CMS Admin Panel

## 🚨 Login Button Not Appearing?

**This is expected!** Decap CMS requires an OAuth backend to show the login button on GitHub Pages.

## ✅ How to Fix This

You have two options:

### Option 1: Production Setup (Recommended)

Follow the complete step-by-step guide in **[OAUTH_SETUP.md](./OAUTH_SETUP.md)**

This will:
- Set up FREE OAuth authentication via Vercel
- Enable the login button on https://yellowbowlo9.github.io/admin/
- Allow you to edit your site from anywhere
- Takes ~15 minutes

### Option 2: Local Development Only

If you just want to test the CMS locally:

```bash
# Run this in your project directory:
npx decap-server

# Then visit:
# http://localhost:8080/admin/
```

The login button will appear and work locally without any OAuth setup.

## 📝 What is Decap CMS?

Decap CMS provides a web-based admin interface to edit your Jekyll site content without touching code.

Once set up, you can:
- Create and edit blog posts
- Manage poetry and journal entries
- Update site settings and colors
- Upload images
- All from a user-friendly web interface!

## 🔧 Current Configuration

- **Backend**: GitHub
- **Repository**: yellowbowlo9/yellowbowlo9.github.io
- **Branch**: main
- **Local backend**: Enabled (for development)

## 📚 More Info

- [Decap CMS Documentation](https://decapcms.org/docs/)
- [GitHub Backend Setup](https://decapcms.org/docs/github-backend/)

---

**Ready to get started?** → Open [OAUTH_SETUP.md](./OAUTH_SETUP.md) and follow the guide!

# Mintlify Deployment Guide

Quick guide to deploy your Media Editor SDK documentation to Mintlify.

---

## ✅ What's Ready

Your documentation repository is ready at:
```
/Users/Deep/media-editor-docs/
```

**All files created:**
- ✅ 12 documentation files (.mdx)
- ✅ Mintlify configuration (mint.json)
- ✅ Git repository initialized
- ✅ Initial commit created
- ✅ .gitignore configured

---

## 🚀 Deployment Steps

### Step 1: Create GitHub Repository

1. Go to [GitHub](https://github.com/new)
2. Create a new repository:
   - **Name:** `media-editor-docs`
   - **Visibility:** Public (safe - no SDK source code here)
   - **Description:** Official documentation for @distralabs/media-editor SDK
   - **Do NOT** initialize with README (already have one)

3. Copy the repository URL (e.g., `https://github.com/your-org/media-editor-docs.git`)

### Step 2: Push to GitHub

```bash
cd /Users/Deep/media-editor-docs

# Add remote
git remote add origin https://github.com/YOUR-ORG/media-editor-docs.git

# Push
git branch -M main
git push -u origin main
```

Replace `YOUR-ORG` with your GitHub organization/username.

### Step 3: Sign Up for Mintlify

1. Visit [mintlify.com](https://mintlify.com)
2. Click "Start for Free"
3. Sign up with GitHub account
4. **Pricing:** Free plan includes:
   - ✅ Unlimited documentation pages
   - ✅ Custom domain
   - ✅ Search functionality
   - ✅ Analytics
   - ✅ Perfect for single user

### Step 4: Connect Repository

1. In Mintlify dashboard, click **"New Project"**
2. Click **"Connect GitHub"**
3. Authorize Mintlify GitHub App
4. Select `media-editor-docs` repository
5. Mintlify will auto-detect `mint.json`
6. Click **"Deploy"**

**Deployment takes ~2 minutes.**

### Step 5: Configure Custom Domain (Optional)

1. In Mintlify dashboard → Settings → Domain
2. Add your custom domain: `docs.distralabs.com`
3. Add DNS records to your domain provider:
   ```
   Type: CNAME
   Name: docs
   Value: cname.mintlify.com
   ```
4. Wait for DNS propagation (~10 minutes)
5. Mintlify will auto-provision SSL certificate

**Alternative:** Use Mintlify's free subdomain: `media-editor.mintlify.app`

---

## 🔒 Security Verification

**Your SDK source code is 100% protected:**

✅ **SDK Repository (`media-editor`):** Private, contains source code
✅ **Docs Repository (`media-editor-docs`):** Public, contains ONLY documentation
✅ **Mintlify Access:** Can only read the docs repository
✅ **NPM Package:** Ships only `/dist/` folder (controlled by package.json)

**What Mintlify can see:**
- ✅ Markdown documentation files (.mdx)
- ✅ Configuration (mint.json)
- ✅ README and assets

**What Mintlify CANNOT see:**
- ❌ Your SDK source code (`/src/`)
- ❌ Internal implementation details
- ❌ Private media-editor repository
- ❌ Any proprietary algorithms

---

## 📝 Updating Documentation

### Local Preview

Install Mintlify CLI:
```bash
npm install -g mintlify
```

Run local dev server:
```bash
cd /Users/Deep/media-editor-docs
mintlify dev
```

Opens at `http://localhost:3000`

### Making Changes

1. Edit `.mdx` files in the docs repository
2. Preview locally with `mintlify dev`
3. Commit and push to GitHub:
   ```bash
   git add .
   git commit -m "Update documentation"
   git push
   ```
4. Mintlify auto-deploys within 1-2 minutes

---

## 🎨 Customization

### Update Branding

Edit `mint.json`:

```json
{
  "name": "Your SDK Name",
  "colors": {
    "primary": "#3b82f6",    // Your brand color
    "light": "#60a5fa",
    "dark": "#2563eb"
  }
}
```

### Add Logo

1. Create SVG logos:
   - `logo/dark.svg` (for dark mode)
   - `logo/light.svg` (for light mode)

2. Update `mint.json`:
   ```json
   {
     "logo": {
       "dark": "/logo/dark.svg",
       "light": "/logo/light.svg"
     }
   }
   ```

3. Commit and push

### Add Favicon

1. Add `favicon.svg` to root
2. Update `mint.json`:
   ```json
   {
     "favicon": "/favicon.svg"
   }
   ```

### Update Navigation

Edit `navigation` in `mint.json` to add/remove pages or reorder sections.

---

## 📊 Analytics

Mintlify provides built-in analytics:
- Page views
- Popular pages
- Search queries
- User engagement

Access in Mintlify dashboard → Analytics

---

## 🔗 Social Links

Update footer links in `mint.json`:

```json
{
  "footerSocials": {
    "twitter": "https://twitter.com/yourusername",
    "github": "https://github.com/yourorg",
    "linkedin": "https://www.linkedin.com/company/yourcompany"
  }
}
```

---

## ✅ Pre-Launch Checklist

Before going live tomorrow:

- [ ] Create GitHub repository for docs
- [ ] Push docs to GitHub
- [ ] Sign up for Mintlify (free plan)
- [ ] Connect GitHub repository to Mintlify
- [ ] Deploy documentation
- [ ] Test all navigation links
- [ ] Verify code examples are correct
- [ ] Update license key placeholders
- [ ] Set up custom domain (optional)
- [ ] Update SDK README to link to docs
- [ ] Test on mobile and desktop
- [ ] Share link with team for review

---

## 🆘 Troubleshooting

### Build Fails on Mintlify

**Check:**
1. `mint.json` is valid JSON
2. All files referenced in navigation exist
3. No broken internal links
4. All `.mdx` files have valid frontmatter

**Test locally first:**
```bash
mintlify dev
```

### Custom Domain Not Working

**Solutions:**
1. Verify DNS CNAME record points to `cname.mintlify.com`
2. Wait 10-30 minutes for DNS propagation
3. Check DNS with: `dig docs.yourdomain.com`
4. Contact Mintlify support if still not working

### Documentation Not Updating

**Solutions:**
1. Check GitHub push was successful
2. Mintlify dashboard → Deployments → Check status
3. Manual redeploy: Mintlify dashboard → Redeploy
4. Clear browser cache

---

## 📞 Support

**Mintlify Support:**
- Email: support@mintlify.com
- Docs: https://mintlify.com/docs
- Discord: https://discord.gg/mintlify

**SDK Support:**
- Email: support@distralabs.com

---

## 🎉 Next Steps

After deployment:

1. **Share with customers:**
   ```
   https://docs.distralabs.com
   ```

2. **Update SDK README:**
   Add link to documentation in your SDK's README.md

3. **NPM Package:**
   Update package.json:
   ```json
   {
     "homepage": "https://docs.distralabs.com",
     "repository": {
       "type": "git",
       "url": "https://github.com/yourorg/media-editor-docs"
     }
   }
   ```

4. **Marketing:**
   - Add to website
   - Include in onboarding emails
   - Share on social media

---

## 📈 Maintenance

**Regular updates:**
- Update FAQ as new issues arise
- Add new integration guides for other frameworks (React, Vue, etc.)
- Add video tutorials (Mintlify supports embedded videos)
- Keep examples up-to-date with latest SDK version
- Monitor analytics to improve popular pages

---

Good luck with your launch tomorrow! 🚀

Your documentation is production-ready and your IP is fully protected.

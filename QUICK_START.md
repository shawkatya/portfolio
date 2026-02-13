# Quick Start Guide - Deploy Your Portfolio to GitHub Pages

## What You Have

✅ Complete Jekyll portfolio site  
✅ All images already copied  
✅ Same W3.CSS design as your current site  
✅ Easy-to-update project collections  

## 3-Step Deployment

### Step 1: Update Configuration

Edit `_config.yml` and change:

```yaml
url: "https://YOUR_GITHUB_USERNAME.github.io"
baseurl: "/katyshaw"
```

Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

### Step 2: Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `katyshaw`
3. Public
4. **Don't** initialize with README
5. Create repository

### Step 3: Deploy

```bash
cd katyshaw_jekyll
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/katyshaw.git
git push -u origin main
```

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Settings → Pages
3. Source: **Deploy from a branch**
4. Branch: **main**
5. Folder: **/ (root)**
6. Click **Save**

### Step 5: Visit Your Site!

After 1-2 minutes: `https://YOUR_USERNAME.github.io/katyshaw/`

---

## Using Your Custom Domain (www.katyshaw.ca)

### At Your Domain Registrar:

Add these DNS records:

**CNAME Record:**
- Host: `www`
- Points to: `YOUR_USERNAME.github.io`

**A Records (for apex domain):**
- Host: `@`
- Points to:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`

### In Your Repository:

1. Create file `CNAME` in repo root
2. Add single line: `www.katyshaw.ca`
3. Commit and push

```bash
echo "www.katyshaw.ca" > CNAME
git add CNAME
git commit -m "Add custom domain"
git push
```

### In GitHub Settings:

1. Settings → Pages
2. Custom domain: `www.katyshaw.ca`
3. Check "Enforce HTTPS" (after DNS propagates)

**Wait 24-48 hours for DNS to propagate**

---

## Adding a New Project Series

Create file: `_projects/my-new-series.md`

```yaml
---
title: "Series Name"
subtitle: "description"
year: 2026
tab_id: "SeriesName"
book_url: "https://optional.com"
images:
  - image1.jpg
  - image2.jpg
  - image3.jpg
order: 3
---
```

Copy images to `assets/images/`, then:

```bash
git add _projects/my-new-series.md assets/images/
git commit -m "Add new series"
git push
```

Done! The new tab appears automatically.

---

## Updating Content

### Update Contact Info:
Edit `index.html` (line ~67)

### Update About Text:
Edit `index.html` (line ~22)

### Update Event Info:
Edit `index.html` (line ~80)

Then push:
```bash
git add index.html
git commit -m "Update content"
git push
```

---

## Troubleshooting

**Site shows 404?**
- Wait 2-3 minutes after first push
- Check Settings → Pages shows "Your site is live"

**Images broken?**
- Check files are in `assets/images/`
- Check `_config.yml` baseurl is correct

**Tabs not working?**
- Hard refresh: Ctrl+F5 (Windows) or Cmd+Shift+R (Mac)

**Need help?**
- Check the full README.md
- View GitHub Actions tab for build errors

---

## What's Next?

Your site will be:
- ✅ Free (no hosting costs)
- ✅ Fast (static site)
- ✅ Secure (HTTPS)
- ✅ Easy to update (just edit markdown files)
- ✅ Version controlled (git history)

**Want to add a blog later?** Just ask!

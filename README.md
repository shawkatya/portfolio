# Kathryn Shaw Artist Portfolio - Jekyll Site

Your portfolio converted to Jekyll with collections for easy project management.

## What's Changed

**From:** Single HTML file with hardcoded images  
**To:** Jekyll site with project collections

**Benefits:**
- ✅ Same exact design and functionality
- ✅ Easy to add new project series - just create a new `.md` file
- ✅ Free GitHub Pages hosting (no more hosting fees!)
- ✅ Automatic image galleries from simple lists
- ✅ Version control with git

## File Structure

```
katyshaw_jekyll/
├── _config.yml           # Site configuration
├── _layouts/
│   └── default.html      # Main layout (your W3.CSS design)
├── _includes/
│   └── gallery.html      # Reusable gallery component
├── _projects/            # Project series (collections)
│   ├── big-hobbies.md    # Big Hobbies series
│   └── noonshot.md       # Noonshot series
├── assets/
│   ├── images/           # ALL your images go here
│   └── cv.pdf            # Your CV
├── index.html            # Homepage (About/Work/Contact)
├── favicon.ico
└── Gemfile               # Dependencies
```

## Setup Instructions

### 1. Add Your Images

Copy ALL image files to `assets/images/`:

```bash
cp *.jpg *.png assets/images/
```

**Required images:**
- grid.jpg (hero)
- loucon1.jpg (footer)
- funding_cca.png, funding_ott.png (logos)
- All project images (circus.png, beneath.jpg, etc.)

### 2. Add Your CV

```bash
cp cv.pdf assets/
```

### 3. Update Configuration

Edit `_config.yml`:

```yaml
url: "https://YOUR_GITHUB_USERNAME.github.io"
baseurl: "/katyshaw"  # or whatever you name the repo
```

### 4. Test Locally (Optional)

```bash
bundle install
bundle exec jekyll serve
```

Visit: http://localhost:4000/katyshaw/

### 5. Deploy to GitHub Pages

```bash
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/katyshaw.git
git push -u origin main
```

Enable GitHub Pages:
- Settings → Pages
- Source: Deploy from a branch
- Branch: main, folder: / (root)
- Save

**Site will be live at:** `https://YOUR_USERNAME.github.io/katyshaw/`

## Adding New Project Series

To add a new project series, create a new file in `_projects/`:

**Example: `_projects/new-series.md`**

```yaml
---
title: "New Series Name"
subtitle: "brief description"
year: 2026
tab_id: "NewSeries"
book_url: "https://optional-link-to-book.com"
images:
  - image1.jpg
  - image2.jpg
  - image3.png
  - image4.jpg
order: 3
---

Optional longer description of the series goes here.
```

**That's it!** The tab and gallery will appear automatically.

## Updating Contact/Events

Edit the Contact section in `index.html` around line 67.

## File Naming

- Project files: `_projects/series-name.md` (lowercase, hyphens)
- Images: Keep your current naming (circus.png, beneath.jpg, etc.)
- Tabs IDs: No spaces (use "BigHobbies" not "Big Hobbies")

## Image Management

All images go in `assets/images/`. The gallery component automatically:
- Creates a 4-column responsive grid
- Adds click-to-enlarge lightbox
- Handles mobile layout

## Customization

**To change colors/styling:**
Edit `_layouts/default.html` CSS section (lines 10-18)

**To change About text:**
Edit `index.html` About section (lines 22-28)

**To update contact info:**
Edit `index.html` Contact section (lines 67-90)

## Troubleshooting

**Images not showing?**
- Check they're in `assets/images/`
- Check spelling matches exactly (case-sensitive!)

**Tabs not working?**
- Make sure `tab_id` has no spaces
- Check JavaScript is loading (view page source)

**Site not building?**
- Check GitHub Actions tab for errors
- Make sure `_config.yml` URLs are correct

## Custom Domain (Optional)

To use `www.katyshaw.ca`:

1. Add `CNAME` file to repo root with: `www.katyshaw.ca`
2. Update DNS at your domain registrar:
   - Add CNAME record: `www` → `YOUR_USERNAME.github.io`
3. In GitHub: Settings → Pages → Custom domain → `www.katyshaw.ca`

## Future Enhancements

**Want to add a blog later?**
Just ask - I can add a `_posts` collection with minimal changes to the design.

**Want individual project pages?**
We can add detailed pages for each artwork while keeping the current gallery view.

## Notes

- Jekyll processes the site automatically on GitHub Pages
- Changes take 1-2 minutes to appear after pushing
- The site is static (no server-side code) so it's fast and secure
- All your W3.CSS styling and JavaScript is preserved

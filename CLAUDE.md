# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static website celebrating Haley the Greyhound — a retired racing greyhound with adventures across Massachusetts and New England. The site is built with pure HTML, Tailwind CSS (via CDN), and DaisyUI.

**IMPORTANT:** This is a 100% static site with NO build step, NO compilation, NO package.json dependencies required for deployment. All files are served directly by Cloudflare Pages.

## Architecture

### Page Structure
All pages follow a consistent pattern:
- Load DaisyUI and Tailwind CSS from CDN (index.html:7-8)
- Include favicon links (index.html:10-16)
- Dynamically load navigation from `partials/navbar.html` via JavaScript fetch (index.html:47-50)
- Active link highlighting is performed client-side by normalizing URLs and comparing to current path (index.html:26-44)

### Navigation System
The navigation bar is centralized in `partials/navbar.html` and loaded into all pages via JavaScript. This allows updating navigation in a single location. The navbar includes:
- Mobile hamburger menu for small screens
- Desktop horizontal menu for large screens
- Both menus maintain the same link structure

### Pages
Nine main pages, each following the same HTML template pattern:
- `index.html` - Home/introduction
- `north_end.html` - Boston North End story
- `natick.html` - Suburban life
- `cape_cod.html` - Cape Cod adventures
- `travel.html` - New England travel
- `holidays.html` - Holiday celebrations
- `friends.html` - Companions
- `silly_pics.html` - Photo gallery
- `backstory.html` - Racing history

Each page references images from the `assets/` directory using relative paths like `assets/natick_image01.jpg`.

## Development Workflow

### Local Development
The site is static HTML with no build process required. To preview:

**Primary method:** VS Code with Live Server extension
1. Open the project in VS Code
2. Right-click any `.html` file and select "Open with Live Server"
3. Auto-reload on file changes

**Alternative:** Any simple web server (e.g., `python -m http.server`)

**Important:** Direct file opening (file://) won't work due to CORS restrictions on the navbar fetch.

### Testing
There are no automated tests. Manual testing should verify:
- Navigation loads correctly on all pages
- Active link highlighting works
- Images display properly
- Responsive layout works on mobile and desktop
- All internal links navigate correctly

### Deployment
This is a 100% static site with NO build step. Two branches are used for deployment:

**Cloudflare Pages projects:**
- `haley-site` → `main` branch → **www.haleythegreyhound.com** (production)
- `haley-site-stage` → `stage` branch → **stage.haleythegreyhound.com** (staging)

**Deployment workflow:**
```bash
# Work on changes in a feature branch, then merge to stage for testing
git checkout -b feature-name
# ... make changes ...
git add .
git commit -m "Description"
git checkout stage
git merge feature-name
git push origin stage  # Triggers stage deployment

# After testing, merge to main for production
git checkout main
git merge stage
git push origin main  # Triggers production deployment
```

Cloudflare Pages serves files directly from the repository root with no build command or processing.

### Web Analytics
**Cloudflare Web Analytics is automatically enabled** for this site. Cloudflare Pages auto-injects the analytics tracking script at deployment time - you will NOT see it in the source HTML files, but it will appear in the deployed page source.

- Analytics script is injected automatically by Cloudflare Pages
- No code changes needed in HTML files
- Only tracks production site (www.haleythegreyhound.com)
- Cookie-free and GDPR compliant
- Access analytics in Cloudflare Dashboard → Analytics & logs → Web analytics

**Important:** Do not manually add Cloudflare analytics scripts to the HTML files - Cloudflare handles this automatically.

## Key Conventions

### HTML Page Template
When creating or modifying pages:
1. Include the full head section with DaisyUI/Tailwind CDN links
2. Include all favicon links
3. Include the navbar loading script with active link highlighting
4. Use the div with id `site-navbar` for navigation injection
5. Wrap content in `<main class="p-4 max-w-4xl mx-auto">`

### Styling
- Use DaisyUI component classes (e.g., `btn`, `navbar`, `menu`)
- Use Tailwind utility classes for layout and spacing
- Custom CSS goes in `css/styles.css` (currently minimal)
- All styling relies on CDN versions, no local Tailwind build

### Images
- Store all images in `assets/` directory
- Use descriptive naming: `{section}_image{number}.jpg`
- Reference images with relative paths: `assets/imagename.jpg`

## Modifying Navigation

To add or remove pages from the navigation:
1. Edit `partials/navbar.html`
2. Add/remove `<li><a href="...">...</a></li>` entries in both mobile and desktop menu sections
3. Create corresponding HTML page following the standard template
4. No restart or rebuild needed — changes appear on refresh

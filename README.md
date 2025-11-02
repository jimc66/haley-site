# 🐾 Haley the Greyhound Static Website

This is a static site built to celebrate Haley — a retired racing greyhound with adventures across Massachusetts and New England.

Enjoy

---

## 🌐 Site Overview

Each page features story content and photos extracted from a PowerPoint deck. Pages include:

| Page          | File               | Description |
|---------------|--------------------|-------------|
| Home          | `index.html`       | Intro to Haley |
| North End     | `north_end.html`   | Haley’s first home in Boston |
| Natick        | `natick.html`      | Suburban life (and alter ego Shayla) |
| Cape Cod      | `cape_cod.html`    | Time at the grand-paw-rents’ farm |
| Travel        | `travel.html`      | New England camping & hiking |
| Holidays      | `holidays.html`    | Celebrating the seasons |
| Friends       | `friends.html`     | Haley’s companions |
| Silly Pics    | `silly_pics.html`  | Silly Pictures |
| Back Story    | `backstory.html`   | Racing history & greyhound data |

Each section references one or more images via paths like `assets/natick_image01.jpg`.

---

## 🧱 Tech Stack

| Layer          | Tool/Service         | Purpose                          |
|----------------|----------------------|----------------------------------|
| **Frontend**   | Tailwind CSS + DaisyUI (via CDN) | Styling & layout |
| **Hosting**    | Cloudflare Pages      | Free, fast static site deploys   |
| **Dev Server** | VS Code Live Server | Preview locally with auto-reload |
| **Images**     | Optimized JPG files | Sourced from a PowerPoint file |
| **Navigation** | Vanilla JavaScript + Fetch API | Dynamic navbar loading |

---

## 🗂️ Folder Structure

```
haley-site/
├── index.html              # Home page
├── north_end.html          # All other pages follow same pattern
├── natick.html
├── cape_cod.html
├── travel.html
├── holidays.html
├── friends.html
├── silly_pics.html
├── backstory.html
├── partials/
│   └── navbar.html         # Centralized navigation (loaded by all pages)
├── css/
│   └── styles.css          # Custom styles (currently minimal)
├── assets/
│   ├── *.jpg               # Page images
│   └── favicon files       # Favicon and icons
```

> 📁 The `partials/navbar.html` file is dynamically loaded by JavaScript on each page for centralized navigation management.

---

## ⚙️ Setup & Editing

This site is **100% static HTML** with CDN-loaded Tailwind + DaisyUI. **No build step, no compilation, no npm dependencies.**

### Local Development

Use VS Code with the Live Server extension for local preview:

1. Open the project in VS Code
2. Right-click any `.html` file and select "Open with Live Server"
3. The site will open in your browser with auto-reload on changes

**Alternative:** You can use any simple web server (e.g., `python -m http.server`)

**Note:** You need a local server (not just opening files directly) due to CORS restrictions on the navbar fetch.

---

## 🚀 Deployment

This repository uses a two-branch deployment strategy with Cloudflare Pages:

### Staging Environment
- **Branch:** `stage`
- **Cloudflare Project:** `haley-site-stage`
- **URL:** https://stage.haleythegreyhound.com
- **Purpose:** Test changes before production

### Production Environment
- **Branch:** `main`
- **Cloudflare Project:** `haley-site`
- **URL:** https://www.haleythegreyhound.com
- **Purpose:** Live site

### Deployment Workflow
1. Create a feature branch for changes
2. Merge to `stage` branch and push → auto-deploys to staging
3. Test on stage.haleythegreyhound.com
4. Merge `stage` to `main` and push → auto-deploys to production

**Build Settings:** No build command, no install command. Cloudflare Pages serves files directly from the repository root.

---

## ✏️ Notes & Best Practices

- Keep image filenames aligned with section naming for simplicity
- Use DaisyUI components for layout tweaks
- Image sizes are web-optimized (~500KB–1MB per file)
- Content was extracted from PowerPoint, so spacing and punctuation may need polish

---

## ✅ Summary

- ✅ Static HTML site using Tailwind + DaisyUI
- ✅ Responsive layout with navigation bar
- ✅ Content and images matched to each page
- ✅ Easy to edit and deploy

---

Built with ❤️ to honor Haley’s story.


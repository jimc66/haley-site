# 🐾 Haley the Greyhound Static Website

This is a static site built to celebrate Haley — a retired racing greyhound with adventures across Massachusetts and New England.

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
| **Frontend**   | Tailwind CSS + DaisyUI | Styling & layout |
| **Hosting**    | Cloudflare Pages      | Free, fast static site deploys   |
| **Dev Server** | Local browser / Vite (optional) | Preview and edit locally       |
| **Images**     | Extracted and optimized JPGs | Sourced from a PowerPoint file |

---

## 🗂️ Folder Structure

```
haley-site/
├── index.html
├── cape_cod.html
├── travel.html
├── friends.html
├── ...
├── css/
│   └── styles.css
├── assets/
│   └── *.jpg (image files)
```

> 📁 Place all optimized images into `assets/` before running or deploying.

---

## ⚙️ Setup & Editing

This site is **static HTML** with CDN-loaded Tailwind + DaisyUI. You don’t need a build tool.

### Local Editing

You can:
- Open `index.html` directly in a browser
- Or serve via a simple web server:

```bash
# Python 3.x
python -m http.server
```

### Optional: Use Vite + Tailwind (advanced)

```bash
npm install
npm run dev
```

Use this if you want to customize Tailwind or DaisyUI themes, or add interactive JS.

---

## 🚀 Deploying to Cloudflare Pages

1. Connect the repo or upload ZIP to Cloudflare Pages
2. No build command needed
3. Use the default root (`/`) for deployment
4. Make sure all `.html` and `assets/` files are included

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


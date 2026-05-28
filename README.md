# ⚡ Alex Morgan — Premium Portfolio Website

A production-ready, fully accessible, SEO-optimised personal portfolio website built with HTML5, CSS3, and Vanilla JavaScript. Designed in a **luxury editorial dark** aesthetic with gold accents, glassmorphism, and smooth scroll-triggered animations.

---

## 🗂 Folder Structure

```
portfolio/
│
├── index.html              ← Home (hero, stats, services, testimonials)
├── about.html              ← Bio, timeline, values, FAQ accordion
├── skills.html             ← Skill cards with progress bars + category filter
├── projects.html           ← 6 project showcase cards
├── certifications.html     ← 8+ certs with verify links + newsletter
├── resume.html             ← Online resume + PDF download
├── contact.html            ← Full contact form + social links
│
├── css/
│   ├── style.css           ← Core: variables, layout, components
│   ├── animations.css      ← Keyframes, skill bars, FAQ, particles
│   └── responsive.css      ← Breakpoints (1200/900/768/480px)
│
├── js/
│   ├── script.js           ← Nav, typing effect, counters, reveals, form
│   ├── theme.js            ← Dark/light toggle + localStorage persistence
│   └── animations.js       ← Canvas particle background
│
├── assets/
│   ├── images/             ← Profile photo, project screenshots, OG image
│   ├── icons/              ← Custom icons (optional)
│   └── resume/             ← alex-morgan-resume.pdf
│
└── README.md
```

---

## ✨ Features

### UI/UX
- 🌙 Dark / Light mode with localStorage persistence + OS preference detection
- 🔤 Typewriter animation (custom, no library required)
- 🎨 Glassmorphism cards with gold shimmer on hover
- 🌊 Canvas particle network background (hero section)
- 📊 Animated statistics counters (Intersection Observer)
- 📈 Animated skill progress bars
- 🔍 Skills category filter (Frontend / Backend / Languages / Tools)
- 🗂 FAQ accordion (accessible, keyboard navigable)
- 🖱️ Cursor glow effect (desktop only)
- ⬆️ Back-to-top button with smooth scroll
- 🔔 Toast notification system

### Performance
- CSS `contain`, `will-change`, and hardware-accelerated transforms
- `IntersectionObserver` for lazy scroll-triggered animations (no layout thrash)
- Canvas animation paused on hidden tabs (`visibilitychange` API)
- Minimal render-blocking: theme script is tiny and inline-compatible
- Fonts loaded via `display=swap` to prevent FOIT
- Images marked with `loading="lazy"` (add to `<img>` tags when you add real images)

### Accessibility (WCAG 2.1 AA)
- Semantic HTML5: `<header>`, `<main>`, `<footer>`, `<nav>`, `<article>`, `<aside>`, `<section>`, `<blockquote>`
- All interactive elements have `:focus-visible` indicators
- ARIA labels, roles, `aria-expanded`, `aria-current`, `aria-live`, `aria-required`
- Keyboard-navigable mobile menu, FAQ, filter buttons, and form
- Form validation with `role="alert"` error messages
- Color contrast ratios exceed 4.5:1 for body text
- Typing animation output wrapped in `aria-live="polite"`
- Screen-reader-only `.sr-only` class used where visual labels are hidden
- `prefers-reduced-motion` respected (add `@media (prefers-reduced-motion: reduce)` to further reduce animations if needed)

### SEO
- Unique `<title>` and `<meta name="description">` per page
- Open Graph (`og:title`, `og:description`, `og:image`, `og:url`, `og:type`)
- Twitter Card (`twitter:card`, `twitter:title`, `twitter:image`)
- `<link rel="canonical">` on every page
- Semantic heading hierarchy (H1 → H2 → H3)
- `<meta name="author">` and `<meta name="keywords">`
- Schema-ready structure (add JSON-LD `Person` schema to `<head>` for best results)

---

## 🚀 Getting Started

No build tools required. Just open in a browser:

```bash
# Option 1 — direct open
open index.html

# Option 2 — local dev server (recommended to avoid CORS on canvas/fetch)
npx serve .
# or
python3 -m http.server 8080
```

---

## 🔧 Customisation Guide

### 1. Personal Info
Replace all instances of **"Alex Morgan"** across HTML files with your name. Search-replace works perfectly.

### 2. Contact Details
Update email, phone, location, and social links in:
- `index.html` (social-float sidebar)
- `contact.html` (info column + footer)
- `resume.html` (resume header band)

### 3. Profile Photo
Replace the `AM` avatar initials with a real `<img>` tag:
```html
<img src="assets/images/profile.jpg" alt="Your Name" class="hero-avatar animate-pulse-ring">
```

### 4. Projects
Edit the 6 project cards in `projects.html`. Update:
- Emoji / project image in `.project-img-inner`
- Title, description, tech stack tags
- GitHub and live demo `href` attributes

### 5. Skills / Progress Bars
In `skills.html`, update each `.skill-bar-fill`'s `data-width` attribute (e.g. `data-width="85%"`).

### 6. Typing Words
In `index.html`, update the `data-words` JSON array on the typed element:
```html
data-words='["Web Applications","Mobile Apps","Design Systems"]'
```

### 7. Resume PDF
Place your PDF at `assets/resume/alex-morgan-resume.pdf`. The download button in `resume.html` points there automatically.

### 8. Colors
All colors use CSS custom properties in `css/style.css`. Change `--gold`, `--bg-primary`, etc. in `:root` and `[data-theme="light"]`.

---

## 📦 Deployment

### GitHub Pages
```bash
git init
git add .
git commit -m "Initial portfolio"
git remote add origin https://github.com/yourusername/portfolio.git
git push -u origin main
# Enable Pages: Settings → Pages → Branch: main / root
```

### Netlify (Drag & Drop)
1. Go to [netlify.com](https://netlify.com) → "Add new site" → "Deploy manually"
2. Drag the `portfolio/` folder onto the deploy zone
3. Done — live in ~10 seconds

### Netlify (CLI)
```bash
npm install -g netlify-cli
netlify deploy --prod --dir .
```

### Vercel
```bash
npm install -g vercel
vercel --prod
```

---

## 📋 Lighthouse Targets

| Metric       | Target |
|-------------|--------|
| Performance  | 95+    |
| Accessibility| 100    |
| Best Practices| 100  |
| SEO          | 100    |

**Tips to hit 100 SEO:**
- Add a `sitemap.xml`
- Add a `robots.txt`
- Ensure all images have descriptive `alt` text
- Add JSON-LD `Person` schema

**Tips to hit 95+ Performance:**
- Convert images to WebP
- Self-host Google Fonts (download and serve locally)
- Add `<link rel="preload">` for the hero image
- Enable gzip/Brotli on your host

---

## 🧩 Tech Stack

| Technology | Purpose |
|-----------|---------|
| HTML5 | Semantic structure |
| CSS3 (custom properties, Grid, Flexbox) | Styling & layout |
| Vanilla JavaScript (ES2020+) | Interactions & animations |
| Canvas API | Particle background |
| Intersection Observer API | Scroll-triggered animations |
| Web Storage API | Theme persistence |
| Font Awesome 6 | Icons |
| Google Fonts (Playfair Display + DM Sans) | Typography |

---

## 📄 License

MIT — free to use for personal and commercial portfolios. Attribution appreciated but not required.

---

*Built with ♥ — ready to impress recruiters, clients, and the open-source community.*

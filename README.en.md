<p align="right" dir="ltr">
  <a href="./README.md" lang="fr" hreflang="fr" rel="alternate" title="Lire la doc en français" aria-label="Lire la doc en français">Français</a> · 🇬🇧 <strong>English</strong>
</p>

# Frontend Mentor – Social links profile (solution)

[![Vite](https://img.shields.io/badge/Vite-⚡-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/) [![Tailwind CSS v4](https://img.shields.io/badge/Tailwind%20CSS-v4-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/) [![Netlify](https://img.shields.io/badge/Netlify-deploy-00C7B7?logo=netlify&logoColor=white)](https://www.netlify.com/) [![Live](https://img.shields.io/badge/Live-jb--fem--social--links--profile.netlify.app-brightgreen)](https://jb-fem-social-links-profile.netlify.app/)

This repo contains my solution to **[Social links profile](https://www.frontendmentor.io/challenges/social-links-profile-UG32l9m6dQ)** by Frontend Mentor.

> 🎯 Personal goal: ship a small, **keyboard‑friendly** card with crisp **hover/focus** states, plus two tiny personal touches: **gradient text** and **custom Tailwind v4 components**.

---

## 🔎 Overview

### The challenge

- Show **hover/focus** states for all interactive elements.
- Use semantic HTML and keep the page navigable **with keyboard only**.
- Personalize the content (name/links) and palette.

### Screenshot

![Solution screenshot](https://jb-fem-social-links-profile.netlify.app/og.jpg)

### Links

- Live: https://jb-fem-social-links-profile.netlify.app/

---

## 🚀 Running the project

```bash
npm install
npm run dev      # local server
npm run build    # production build (dist/)
npm run preview  # preview the build locally
```

---

## 🧱 Built with

- **Semantic HTML5** (`main`, `article`, `ul/li`, `img` with `alt`, `width`/`height`)
- **Tailwind CSS v4** (_CSS‑first_ approach with `@theme` tokens)
- **Mobile‑first workflow**
- **Locally hosted WOFF2** fonts (Inter 400/600/700) + `font-display: swap`
- **Vite** (fast build, strips console/debugger, fingerprinted assets)
- **Netlify** (security & caching headers via `netlify.toml`)

## 🧭 Approach & implementation choices

### HTML structure

- A centered card inside `<main>` → `<article>`.
- Decorative rounded container for the avatar, `<h1>` for the name, location & bio as paragraphs, then a link list.
- Standard `<a>` links ensure keyboard focusability.

### ✨ Personal customizations

**1) Gradient text heading**

```html
<h1
  class="bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 bg-clip-text text-2xl font-bold tracking-tight text-transparent"
>
  Julien Borgeon
</h1>
```

**2) Avatar halo with gradient**

```html
<div
  class="relative mx-auto mb-6 aspect-square w-[90px] overflow-hidden rounded-full bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500"
>
  <img
    class="absolute bottom-0 left-3/6 -translate-x-1/2 object-cover"
    src="/assets/avatar-julien-borgeon.png"
    width="80"
    height="80"
    alt="Avatar of Julien Borgeon"
  />
</div>
```

**3) Tailwind v4 custom components**

```css
@layer components {
  .btn {
    @apply bg-dark-700 hover:bg-dark-750 block w-full rounded-md px-4 py-3 text-sm font-semibold text-white/80 shadow-md/10 transition-colors duration-150 ease-out;
  }
  .link {
    @apply underline decoration-white/70 decoration-1 underline-offset-2 transition-all duration-200 ease-out;
    text-decoration-skip-ink: auto;
  }
  @media (hover: hover) {
    .link:hover {
      @apply decoration-accent text-white underline-offset-4;
    }
  }
  .focus-ring {
    @apply focus-visible:ring-accent focus-visible:ring-4 focus-visible:ring-offset-2 focus-visible:ring-offset-white/70 focus-visible:outline-none;
  }
}
```

---

## ♿ Accessibility (a11y)

- **Keyboard‑only** navigation supported; strong `:focus-visible` ring.
- External links use `target="_blank"` + `rel="noopener noreferrer"`.
- High contrast (dark theme + clear accent for focus/hover).

## ⚡ Performance

- **Tailwind v4 JIT** → minimal CSS.
- **WOFF2 fonts** + targeted `preload` + `swap`.
- **Vite**: `sourcemap: false`, `drop: ["console","debugger"]`, `assetsInlineLimit: 0` to avoid useless inlining.
- **Netlify**: long‑term caching for fingerprinted assets/fonts, production security headers.

---

## 🧪 My process

### Technologies used

- **Semantic HTML5 markup**
- **CSS custom properties** (via Tailwind v4 tokens in @theme)
- **Mobile‑first workflow**
- **Vite** (bundler/build)
- **Tailwind CSS v4**
- **Netlify** (hosting & headers)
-

### What I learned

- Tailwind v4 **tokens + components** make it easy to keep styles consistent and tiny.
- Small UI touches (gradients, focus ring) while staying **a11y‑first**.

### Continued development

- Optional **auto light/dark** theme via `prefers-color-scheme`.

### Useful resources

- Tailwind v4 – `@theme` & tokens : https://tailwindcss.com/docs/theme
- MDN – Responsive images (`<picture>`, `srcset`, `sizes`) : https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images
- ***

## 👤 Author

- Website (preview) — https://www.julienborgeon.fr

---

## 🙌 Acknowledgments

Thanks to **Frontend Mentor** for the design and the community for feedback.
Shout‑out to MDN & Tailwind for their excellent documentation.

---

## 📁 Project structure

```bash
└── social-links-profile
    └── 📁.vscode
        ├── settings.json
    └── 📁public
        └── 📁assets
            ├── avatar-julien-borgeon.png
            ├── favicon-32x32.png
        └── 📁fonts
            ├── inter-v19-latin-600.woff2
            ├── inter-v19-latin-700.woff2
            ├── inter-v19-latin-regular.woff2
        ├── og.jpg
    └── 📁src
        ├── main.css
    ├── .gitattributes
    ├── .gitignore
    ├── .prettierrc
    ├── index.html
    ├── netlify.toml
    ├── package-lock.json
    ├── package.json
    ├── README.en.md
    ├── README.md
    ├── structure.md
    └── vite.config.js
```

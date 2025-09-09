<p align="right" dir="ltr">
  🇫🇷 <strong>Français</strong> ·
  <a href="./README.en.md" lang="en" hreflang="en" rel="alternate" title="Read this doc in English" aria-label="Read this doc in English">English</a>
</p>

# Frontend Mentor – Social links profile (solution)

[![Vite](https://img.shields.io/badge/Vite-⚡-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/) [![Tailwind CSS v4](https://img.shields.io/badge/Tailwind%20CSS-v4-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/) [![Netlify](https://img.shields.io/badge/Netlify-deploy-00C7B7?logo=netlify&logoColor=white)](https://www.netlify.com/) [![Live](https://img.shields.io/badge/Live-jb--fem--social--links--profile.netlify.app-brightgreen)](https://jb-fem-social-links-profile.netlify.app/)

Ce repo contient ma solution au défi **[Social links profile](https://www.frontendmentor.io/challenges/social-links-profile-UG32l9m6dQ)** de Frontend Mentor.

> 🎯 Objectif personnel : livrer une carte simple, accessible au clavier, avec des **états hover/focus** nets, et y ajouter deux petits extras perso : **texte en dégradé** et **components Tailwind v4 custom**.

---

## 🔎 Aperçu

### Le challenge

- Voir des états hover/focus sur tous les éléments interactifs.
- HTML sémantique et navigation au clavier uniquement possible.
- Personnaliser le contenu (nom, liens) et palette.

### Capture

![Screenshot de la solution](https://jb-fem-social-links-profile.netlify.app/og.jpg)

### Liens

- Live : https://jb-fem-social-links-profile.netlify.app/

---

## 🚀 Lancer le projet

```bash
npm install
npm run dev      # serveur local
npm run build    # build de production (dossier dist/)
npm run preview  # prévisualisation du build
```

---

## 🧱 Construit avec

- **HTML5 sémantique** (`main`, `article`, `ul/li`, `img` avec `alt`, `width`/`height`).
- **Tailwind CSS v4** (approche _CSS-first_ avec `@theme` pour définir des tokens)
- **Mobile-first workflow**
- **Polices locales WOFF2** (Inter 400/600/700) + `font-display: swap`
- **Vite** (build performant, purge console/debugger, assets fingerprintés)
- **Netlify** (headers de sécurité & cache via `netlify.toml`)

## 🧭 Démarche & choix d’implémentation

### Structure HTML

- Une carte centrée dans `<main>` → `<article>`.
- Portrait dans un conteneur rond décoratif, nom en `<h1>`, localisation + bio en `<p>`, puis liste de liens en `<ul>` pour respecter la sémantique HTML.
- Chaque lien est un `<a>` natif (donc focusable au clavier) et possède un intitulé clair.

### ✨ Personnalisations (extras)

**1) Titre avec texte en gradient**

```html
<h1
  class="bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 bg-clip-text text-2xl font-bold tracking-tight text-transparent"
>
  Julien Borgeon
</h1>
```

**2) Avatar avec halo dégradé**

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

**3) Composants Tailwind v4 custom** (dans `@layer components`)

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

## ♿ Accessibilité (A11y)

- Navigation **100% clavier** (ordre logique, liens natifs, `:focus-visible` très visible via `.focus-ring`).
- Liens externes avec `target="_blank"` + `rel="noopener noreferrer"`.
- Contrastes élevés (thème sombre, accent clair sur focus/hover).

## ⚡ Performance

- **Tailwind v4 JIT** → CSS minimal.
- **Polices WOFF2** + `preload` ciblé + `swap`.
- **Vite** : `sourcemap: false`, `drop: ["console","debugger"]`, `assetsInlineLimit: 0` pour éviter l’inlining d’assets.
- **Netlify** : cache long sur assets fingerprintés/polices, en-têtes de sécurité pour la version en prod publiée pour la preview.

---

## 🧪 Ma démarche

### Technologies utilisées

- **Semantic HTML5 markup**
- **CSS custom properties** (via tokens Tailwind v4 dans `@theme`)
- **Mobile-first workflow**
- **Vite** (bundler/build)
- **Tailwind CSS v4**
- **Netlify** (hébergement & headers)

### Ce que j'ai appris

- Le _mental model_ **Tailwind v4** (`@theme` + `@layer`) simplifie la création de tokens et de composants réutilisables.
- Petites touches UI (gradients, focus ring) qui restent **accessibles**.

### Pistes d’amélioration

- Option **light/dark auto** via `prefers-color-scheme` et tokens CSS.

### Ressources utiles

- Tailwind v4 – `@theme` & tokens : https://tailwindcss.com/docs/theme
- MDN – Images responsives (`<picture>`, `srcset`, `sizes`) : https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images
- ***

## 👤 Auteur

- Website (preview) — https://www.julienborgeon.fr

---

## 🙌 Remerciements

Merci à **Frontend Mentor** pour le design du challenge et à la communauté pour les retours.  
Un clin d’œil aux ressources MDN & Tailwind pour la clarté de leur doc.

---

## 📁 Structure du projet

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

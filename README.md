# rydenpups

The rydenpups (Luna & Stella) Dubai dog-content site — an Astro static site that doubles as a **Luni publish target**.

Live at: [https://rydenpups.com](https://rydenpups.com)

## Stack
- **Astro** (static site generator)
- **Markdown** content collection for the blog
- Deployed on **Vercel** (auto-deploys on push to `main`)

## Development

```bash
npm install
npm run dev
```
Open http://localhost:4321.

## Build

```bash
npm run build
```
Outputs static files to `dist/`.

## Project layout
```
src/
├── content/blog/         ← Markdown blog posts (Luni publishes here)
│   └── config.ts         ← content collection schema
├── layouts/
│   └── Base.astro        ← shared <head>, nav, footer
├── components/
│   ├── Nav.astro
│   └── Footer.astro
├── pages/
│   ├── index.astro       ← homepage
│   ├── about.astro
│   ├── collabs.astro
│   └── blog/
│       ├── index.astro   ← /blog
│       └── [slug].astro  ← /blog/{slug}
└── styles/
    ├── global.css        ← shared design tokens
    ├── home.css          ← homepage sections
    └── blog.css          ← blog-post classes (Luni spec)
```

## Luni publish target

This repo is configured as a `github_commit` + `astro_md` publish target:

- **Content path:** `src/content/blog/`
- **Article URL:** `https://rydenpups.com/blog/{slug}`
- **Frontmatter:** `title`, `description`, `pubDate`, `heroImage?`, `category?`, `tags?`, `draft`
- **Styled classes:** `.lead`, `.quick-answer`, `.pull-quote`, `.compare-grid`, `.compare-card`, `.compare-card.highlight`, `.compare-card .label`, `.compare-table`, `.faq-item` — all defined in `src/styles/blog.css`.

To publish, Luni commits a `.md` file to `src/content/blog/`. Vercel auto-deploys on push.

## Brand
- Pink #FBC9D8, Pink soft #FDE2E9, Pink deep #F48BAE, Rose #E96D97
- Cream #FFF6E4, Lilac #D9C9F0, Lilac deep #B79CE0, Butter #FCE9A8
- Ink #6B4A57, White #FFFDF8
- Fonts: Baloo 2 (display), Gochi Hand (handwritten), Quicksand (body)

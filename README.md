# EmberMind Labs

The website for **EmberMind Labs** — an AI consulting and education venture.
*Lighting the path from idea to impact.*

Built with [Astro](https://astro.build). Dark, ember-themed design system driven
by the brand logo (warm orange/amber on near-black).

## 🔥 Stack

- **Astro 5** with the MDX integration
- Content collections for the **Insights** blog (`src/content/blog`)
- Hand-rolled CSS design system in `src/styles/global.css` (CSS custom
  properties for the ember palette, typography, and spacing)

## 🗂 Structure

```text
/
├── public/
│   └── favicon.svg            # ember flame favicon
├── src/
│   ├── assets/                # logo (optimized via astro:assets)
│   ├── components/            # Nav, Hero, About, Services, Approach,
│   │                          # Insights, BlogCard, Contact, Footer
│   ├── content/blog/          # Insights posts (.md / .mdx)
│   ├── layouts/               # Layout.astro, PostLayout.astro
│   ├── pages/
│   │   ├── index.astro        # landing page
│   │   └── blog/              # /blog index + [...slug] post route
│   ├── styles/global.css      # ember design system
│   └── content.config.ts      # blog collection schema
└── package.json
```

## 🧞 Commands

| Command           | Action                                       |
| :---------------- | :------------------------------------------- |
| `npm install`     | Install dependencies                         |
| `npm run dev`     | Start local dev server at `localhost:4321`   |
| `npm run build`   | Build the production site to `./dist/`       |
| `npm run preview` | Preview the production build locally         |

## ✍️ Adding an insight

Create a Markdown file in `src/content/blog/`:

```md
---
title: "Your title"
description: "One-sentence summary for cards and SEO."
pubDate: 2026-06-11
category: insight        # insight | news | tutorial | case-study
tags: ["AI", "Strategy"]
draft: false
---

Your content...
```

## 🎨 Design notes

The palette is derived from the EmberMind logo: ember orange (`#ff7a1a`), bright
flame (`#ffb24d`), gold spark (`#ffcf5c`), and deep ember red (`#e8350d`) over a
warm near-black. The wordmark pairs an elegant serif (Cormorant Garamond) for
*Ember* with a clean sans (Inter / Space Grotesk) for *Mind Labs*, echoing the
logo.

The layout is editorial: dark "ink" bands (hero, approach, contact) alternate
with warm cream "paper" sections. On paper, accent text uses `--accent-dim`
for readable contrast; on dark bands it uses `--accent`.

## ✉️ Contact form

Site-wide settings (email, social links, form backend) live in `src/config.ts`.

The form posts to [Formspree](https://formspree.io) via `fetch`, with inline
success and error messages and a honeypot spam field. To turn it on:

1. Create a free Formspree form that delivers to the inbox you want.
2. Copy its form ID (the part after `/f/` in the endpoint).
3. Set `FORMSPREE_ID` in `src/config.ts` and redeploy.

Until `FORMSPREE_ID` is set, submitting the form opens a pre-filled email draft
to `site.email` in the visitor's mail app, so messages are never silently lost.

Still to fill in: the real LinkedIn / X URLs in `src/config.ts`.

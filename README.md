# Abu Shadat Shaikat — Portfolio

Personal portfolio of **Abu Shadat Shaikat**, Software Engineer (Laravel · Node.js · React · Next.js · Vue.js · Flutter) based in Dhaka, Bangladesh.

**Live site → [shaikat.netlify.app](https://shaikat.netlify.app)**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/preview-dark.jpg">
  <source media="(prefers-color-scheme: light)" srcset="docs/preview-light.jpg">
  <img alt="Portfolio hero section" src="docs/preview-dark.jpg">
</picture>

<p align="center"><sub>The preview follows your GitHub theme: dark mode on the site in dark, light mode in light.</sub></p>

---

## Highlights

- **Glassmorphism + liquid glass UI**: frosted panels with specular highlights and lit edges. On Chromium browsers, small elements also refract the background through an SVG displacement filter. Other browsers get the frosted fallback.
- **Light and dark themes**: follows the system setting by default and remembers a manual choice. An inline script applies the theme before paint, so there's no flash.
- **Content from one file**: every section (hero code card, about, skills, projects, experience, education) reads from [`src/app/(main)/data/resume.ts`](<src/app/(main)/data/resume.ts>).
- **Responsive**: desktop pill navbar with a sliding active-section indicator. On mobile and tablet, a full-screen glass menu that locks scrolling, closes on <kbd>Esc</kbd>, and manages focus.
- **Smooth by design**: animations only use `transform` and `opacity`. Animated regions pause off-screen via `IntersectionObserver`, and `prefers-reduced-motion` is respected throughout.
- **SEO**: full metadata, Open Graph and Twitter cards, canonical URLs, JSON-LD `Person` schema, plus generated `sitemap.xml`, `robots.txt` and web manifest.
- **Static export**: builds to plain HTML/CSS/JS (`out/`), so it can be hosted anywhere.

## Tech stack

| Area | Tools |
| --- | --- |
| Framework | [Next.js 15](https://nextjs.org) (App Router, static export), React 19 |
| Language | TypeScript |
| Styling | Tailwind CSS v4, custom CSS design tokens |
| Icons | react-icons |
| Fonts | Geist, Geist Mono, Instrument Serif (via `next/font`) |
| Contact form | [FormSubmit](https://formsubmit.co) |
| CI | GitHub Actions: install and build on every push / PR |

## Getting started

Requires **Node.js 20+**.

```bash
git clone https://github.com/asm-shaikat/awesome-portfolio.git
cd awesome-portfolio
npm install
npm run dev          # http://localhost:3000
```

| Script | What it does |
| --- | --- |
| `npm run dev` | Start the dev server |
| `npm run build` | Production build + static export to `out/` |
| `npm run lint` | Run ESLint |

> **Tip:** don't run `npm run build` while `npm run dev` is running. Both write to `.next/`, and the dev server will start serving broken styles. If that happens, stop it, run `rm -rf .next`, and start again.

## Project structure

```
src/app/
├── layout.tsx              # <html>, fonts, metadata/SEO, JSON-LD, theme script, backdrop
├── page.tsx                # Home: Hero → Tech strip → About → Skills → Projects → Experience → Contact
├── globals.css             # Theme tokens (light/dark), glass + liquid-glass styles, animations
├── sitemap.ts · robots.ts · manifest.ts
└── (main)/
    ├── data/resume.ts      # ← all portfolio content lives here
    ├── components/
    │   ├── Navbar.tsx      # Desktop pill + mobile full-screen menu
    │   ├── HeroSection.tsx
    │   ├── HeroCodeCard.tsx# "about.ts" code window with floating stat chips
    │   ├── TechStrip.tsx   # Scrolling tech-stack marquee
    │   ├── AboutSection.tsx
    │   ├── SkillSection.tsx
    │   ├── ExperienceSection.tsx
    │   ├── ContactForm.tsx
    │   ├── Footer.tsx
    │   ├── ThemeToggle.tsx
    │   ├── Section.tsx     # Shared section header + helpers
    │   └── space/SpaceZone.tsx  # Pauses animations while off-screen
    ├── views/ProjectsSection.tsx
    └── projects/page.jsx   # /projects: all projects
```

## Customizing

- **Content**: edit [`resume.ts`](<src/app/(main)/data/resume.ts>). Wrap words in `**double asterisks**` to highlight them. Add `live: 'https://…'` to a project to show a link button on its card.
- **Colors**: change the tokens at the top of [`globals.css`](src/app/globals.css) (`:root` for light, `.dark` for dark).
- **Photo**: replace `public/assets/asm-shaikat.jpg`.
- **SEO**: update `siteUrl`, descriptions and the JSON-LD block in [`layout.tsx`](src/app/layout.tsx).

## Deployment

`next.config.ts` sets `output: 'export'`, so `npm run build` produces a fully static site in `out/`. The live site is hosted on Netlify. Any static host works (Netlify, Vercel, GitHub Pages, Cloudflare Pages):

- **Build command:** `npm run build`
- **Publish directory:** `out`

## Contact

- Website: [shaikat.netlify.app](https://shaikat.netlify.app)
- GitHub: [@asm-shaikat](https://github.com/asm-shaikat)
- LinkedIn: [in/asm-shaikat](https://linkedin.com/in/asm-shaikat)
- Email: [asmshaikat1952@gmail.com](mailto:asmshaikat1952@gmail.com)

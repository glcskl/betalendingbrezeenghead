# betalendingbrezeenghead — 3D beer presentation

A browser page that presents five beer varieties in a way that conveys taste and colour visually, rather than describing them in a table. Each variety gets its own 3D scene, with scroll-driven motion, bubbles and parallax text.

Built as a personal project for 4 and 5 June 2026.

## Features

- 3D scenes rendered in the browser with Three.js and React Three Fiber
- Scroll-driven animation that moves the camera between scenes
- Bubble and particle effects for depth
- Parallax and alternating text sections for storytelling
- Horizontal carousel with custom arrow controls
- Content managed in Prismic through Slice Machine
- Deployment to Vercel automated on push

## Tech stack

| Layer | Technology |
| --- | --- |
| Framework | Next.js |
| Language | TypeScript |
| 3D | Three.js with React Three Fiber and Drei |
| Animation | GSAP with `@gsap/react` |
| State | Zustand |
| Content management | Prismic with Slice Machine |
| Styling | Tailwind CSS |
| Hosting | Vercel |

## Getting started

### Requirements

- Node.js 20 or newer
- A Prismic repository, for content changes
- Optional: the Slice Machine app, for editing slices visually

### Environment variables

| Variable | Required | Description |
| --- | --- | --- |
| `NEXT_PUBLIC_PRISMIC_ENVIRONMENT` | yes | Prismic environment name |
| `PRISMIC_ACCESS_TOKEN` | build only | Read token, needed for content that is not public |
| `NEXT_PUBLIC_SITE_URL` | recommended | Canonical site URL, used by metadata |

Create a `.env.local` file in the project root:

```
NEXT_PUBLIC_PRISMIC_ENVIRONMENT=your-environment
NEXT_PUBLIC_SITE_URL=https://your-domain
```

### Installation

```bash
git clone https://github.com/glcskl/betalendingbrezeenghead.git
cd betalendingbrezeenghead
npm install
```

### Running

Start the development server:

```bash
npm run dev
```

Production build:

```bash
npm run build
npm start
```

Slice development, when editing content models:

```bash
npm run slicemachine
```

## Project structure

```
src/slices/          Prismic slices, one directory per section
  Hero/              opening scene
  SkyDive/           scrolling descent scene
  BigText/           oversized typography section
  AlternatingText/   image and text pairs
  Carousel/          horizontal beer carousel
src/app/
  layout.tsx         root layout
  contact/page.tsx   contact page
customtypes/         generated Prismic custom type definitions
slicemachine.config.json
vercel.json
```

## Content

Page composition is defined in Prismic. Each section on the page is a slice, and the frontend renders whatever slices the document contains, so reordering or removing a section requires no code change.

## Deployment

`vercel.json` holds the build configuration. The `Vercel Deploy` workflow redeploys automatically on every push, so a content or code change goes live without a manual step.

## Notes

This project is personal and a portfolio piece. Brand names and labels shown in the page are illustrative and are not an endorsement.
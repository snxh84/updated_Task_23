# Project Workspace — Landing Page

A minimal, modern, Notion-style landing page for **Project**, an AI-powered
workspace. The page is built to demonstrate **CSS positioning techniques**
(`relative`, `absolute`, `z-index`, `fixed`) alongside responsive Tailwind
styling and transitions.

Built with **HTML + Tailwind CSS (CDN)** — no external CSS frameworks or custom fonts.

## How to run

- **Double-click** `index.html` (opens in your browser).

An internet connection is needed for the Tailwind CDN.

## Requirement → Code map

Every item from the brief, and where to find it in `index.html`:

| # | Requirement | Technique(s) | Where |
|---|-------------|--------------|-------|
| 1 | Logo **"+ Project"** and nav links (Product, Solutions, Resources, Pricing, Log in) | — | `<header>` — logo `<a>` + `<nav>` |
| 2 | Navbar CTA button **"Get AI free"** | — | `<header>` last `<a>` (dark pill) |
| 3 | Hero with **gradient background (light orange → white)** | `bg-gradient-to-b from-orange-100 via-orange-50 to-white` | `<section>` hero wrapper |
| 4 | **Centered** headline "Write, plan, share. With AI at your side." + descriptive paragraph | `text-center`, `mx-auto` | hero `<h1>` + `<p>` |
| 5 | CTA buttons **"Get AI free"** & **"Request a demo"** positioned with `relative` + `absolute` | `relative` on button, `absolute` for the hover arrow | two hero `<a>` buttons |
| 6 | **Centered dashboard preview** using `absolute` inside a `relative` container | `relative` stage → `absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2` | hero "visual stage" |
| 7 | **Three floating cards** (Tasks, Project Status, Team Activity) with `absolute`, `z-index`, `shadow` | `absolute` + `z-20`/`z-30` + `shadow-xl`/`shadow-2xl` | Tasks / Project Status / Team Activity cards |
| 8 | **Fixed chat widget** bottom-right | `fixed bottom-6 right-6 z-50` | final `<div>` before `</body>` |

## Positioning techniques used

- **`relative` + `absolute`** — each CTA button is `relative` with an `absolute`
  hover arrow; the hero's visual stage is a `relative` container that anchors the
  `absolute` dashboard and floating cards.
- **Absolute centering** — the dashboard preview is centered inside the relative
  stage with `absolute left-1/2 top-1/2` plus `-translate-x-1/2 -translate-y-1/2`.
- **`z-index` layering** — the dashboard sits at the base, the Tasks and Project
  Status cards at `z-20`, and the Team Activity card above them at `z-30` so
  overlapping cards stack in the right order.
- **`fixed`** — the chat widget uses `fixed bottom-6 right-6 z-50` so it stays
  pinned to the viewport corner on scroll.

## Animations & UI

- **Extended Tailwind config** (in `<head>`) defines custom keyframes and
  animation utilities: `fade-up`, `fade-in`, `float`.
- **Floating cards** use the `float` animation (with staggered `animation-delay`)
  for a gentle hover-in-the-air effect.
- **Hover transitions** on nav links, buttons, sidebar items, and the chat FAB.
- **Group hover** arrows on both CTA buttons (`group` / `group-hover:*`).
- **Responsive** — nav links and dashboard sidebar collapse on mobile; the
  floating cards and layout adapt across breakpoints.

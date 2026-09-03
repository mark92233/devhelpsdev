# DevHub — Developer Resource Directory

A curated, dark-mode developer resource directory and community suggestion hub designed for computer science students and developers learning Web Development, Java OOP, Algorithms, and Systems.

---

## Technical Overview

DevHub is an event-driven single-page directory built with vanilla JavaScript and Tailwind CSS. It features client-side multi-parameter filtering (full-text search and category selection), glassmorphism design tokens, animated grid entry effects, and an integrated Netlify Forms backend for crowdsourced community resource submissions.

### Core Features

- **Multi-Parameter Client Search & Filtering:** Real-time filtering across titles, descriptions, and technology tags combined with category-level narrowing (`Website`, `YouTube`).
- **Glassmorphic Dark Mode Interface:** Tailored design system with backdrop blur filters, custom gradient text, glowing radial hover states, and smooth CSS transitions.
- **Empty State Resolution:** Dynamic fallback views rendered directly into the DOM when filter queries return zero results.
- **Serverless Contribution Pipeline:** Production-ready `data-netlify="true"` form handler collecting community-submitted tools, URLs, and justifications without requiring an external API server.
- **Dynamic Attributor Attribution:** Rendering pipeline capable of assigning custom avatar tokens to user-suggested cards or falling back to the author maintainer badge.

---

## Tech Stack

- **Markup:** Semantic HTML5
- **Styling:** Tailwind CSS (CDN Configuration), Custom CSS3 animations (`fadeSlideUp`, glass cards)
- **Typography:** Plus Jakarta Sans
- **Runtime:** Vanilla ECMAScript (ES6+)
- **Hosting / Form Backend:** Static web host (Netlify Forms / Vercel / GitHub Pages)

---

## Architecture & Data Flow

```text
[ User Input / Select Event ]
             │
             ▼
    filterData() Pipeline
             │
   ┌─────────┴─────────┐
   ▼                   ▼
Text Match        Category Match
(title, desc,     ("all", "Website",
 tags[])           "YouTube")
   └─────────┬─────────┘
             │
             ▼
    renderResources()
             │
    ┌────────┴────────┐
    ▼                 ▼
[ Render Cards ]   [ Display #noResults ]

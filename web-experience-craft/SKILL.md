---
name: web-experience-craft
description: Use when building or improving a website, static page, frontend screen, landing page, dashboard, gallery, benchmark page, interactive demo, or creative web experience. Guides concept selection, visual hierarchy, rendering technology choice, interaction design, responsive layout, states, and browser verification.
---

# Web Experience Craft

## Purpose

Build web pages that feel intentional, usable, and complete. Start from the user's goal and the page's primary experience, then choose layout, visual language, interaction model, and rendering technology to support that experience.

This skill is for broad web work: static HTML pages, React/Vue/Svelte screens, dashboards, galleries, documentation pages, marketing pages, creative coding demos, and interactive tools.

## Core Principles

1. Build the actual experience first, not a placeholder or marketing shell.
2. Let the domain choose the visual style. Avoid generic gradients, space scenes, particles, or oversized hero layouts unless they serve the subject.
3. Make the first viewport communicate the page's purpose and strongest artifact immediately.
4. Prefer real content, real previews, real data, or live artifacts over symbolic placeholders.
5. Use the simplest rendering layer that expresses the idea well.
6. Keep controls familiar: icons for tools, tabs for views, toggles for binary settings, sliders/inputs for numeric settings, menus for option sets.
7. Design complete states: loading, empty, error, selected, hover/focus, modal/fullscreen, mobile, and narrow text cases.
8. Verify in a browser when feasible, especially for responsive layout, canvas/WebGL, iframes, and modals.

## Initial Read

Before editing:

- Inspect existing files, routes, styles, framework, dependencies, data sources, and assets.
- Prefer the project's current design system, CSS conventions, components, and helper APIs.
- Identify whether the page is static, app-like, dashboard-like, content-heavy, gallery-like, or immersive.
- If the user gave a screenshot or existing page, preserve the intent while fixing the weak parts.

## Page Contract

Infer these before implementation. If unclear, make a reasonable assumption and proceed unless the risk is high.

- Audience: who is using it?
- Task: what should they do first?
- Mood: utilitarian, editorial, playful, technical, cinematic, experimental, calm, premium, dense.
- Primary artifact: product, data, text, image, video, map, canvas, 3D scene, code sample, gallery item.
- Interaction depth: static, hover, click, drag, keyboard, realtime, full-screen.
- Success test: what must be visibly true when the work is done?

## Rendering Strategy

Choose the rendering layer deliberately:

- HTML/CSS: documents, marketing, forms, settings, dashboards, editorial pages.
- SVG: diagrams, icons, precise vector composition, small data visuals.
- Canvas 2D: drawing tools, particles, text raster effects, simple simulations, procedural visuals.
- WebGL/Three.js: 3D, shader effects, raymarching, immersive spatial scenes, heavy visual demos.
- iframe: live previews, sandboxes, embedded demos, source comparisons.

Do not use WebGL or Canvas just to look advanced. Use them when they materially improve the experience.

## Layout Guidance

- Use stable dimensions for cards, previews, canvases, boards, toolbars, and repeated items.
- Avoid cards inside cards. Use cards for repeated items, modals, and framed tools; use full-width bands or unframed layouts for page sections.
- Keep text within containers on mobile and desktop. Long labels must wrap or use smaller, context-appropriate type.
- Avoid viewport-width font scaling. Use responsive layout constraints instead.
- For dashboards and operational tools, prioritize density, scanability, filtering, comparison, and repeated use.
- For creative demos, make the primary visual prominent, ideally full-bleed or easy to enter full-screen.
- For landing pages, make the real product, place, person, or object visible in the first viewport when relevant.

## Interaction Guidance

- Prefer direct manipulation over explanatory text.
- Make click targets and active states obvious.
- If a page opens a modal or preview, provide close, escape key handling, and source/open-in-new-tab actions when relevant.
- For gallery or benchmark pages, provide filters and preserve a clear source of truth.
- For iframe previews, make previews non-interactive when inside cards unless interaction is explicitly expected; open the real interactive version on click.
- For full-screen experiences, lock background scroll and clean up iframe/canvas state when closing.

## Data And Source Of Truth

- Use structured data files or APIs when the page content is repeatable or evaluated.
- Avoid duplicating the same facts in README, JSON, UI, and code if one source can drive the rest.
- For benchmark or comparison pages, expose enough metadata to audit the result: title, source, path/link, summary, score/rank, tags, and evaluation notes.
- Link to source files or references when users may want to inspect the artifact.

## Visual Quality Checklist

Check before finishing:

- The strongest artifact is visible without excessive scrolling.
- The page does not look like a generic template unrelated to the subject.
- Colors are not dominated by a single overused hue family unless intentionally branded.
- There are no decorative blobs, orbs, or gradients that do not support the content.
- Icons are familiar and tooltips or labels clarify uncommon actions.
- Buttons, badges, and cards have stable dimensions and do not shift on hover.
- Text does not overlap or overflow at mobile widths.
- Empty/error/loading states are not visually broken.

## Verification

When the page needs a server, run one and provide the URL. If opening the HTML file is enough, say so.

Prefer these checks:

- Load the page through the intended route or local server.
- Confirm data fetches succeed.
- Check desktop and mobile viewport behavior.
- Test primary interactions: filters, open/close, keyboard escape, source links, full-screen, form submission, or drag controls.
- For Canvas/WebGL/Three.js, verify the scene is nonblank, framed correctly, and animating/interacting as expected.
- For iframes, verify paths work from the deployed base path as well as locally.

## Common Patterns

### Gallery Or Benchmark Page

Use structured data. Each item should have:

- title
- model/author/source when relevant
- rank or score when relevant
- summary
- tags/techniques
- source path/link
- live preview when feasible
- full-screen or dedicated view

Use filters based on actual data fields, not string guesses.

### Static Product Or Portfolio Page

Show the product/person/work immediately. Use real images, screenshots, embedded media, or representative artifacts. Avoid a generic text-only hero when the subject is visual.

### Dashboard Or Tool

Keep the interface quiet and efficient. Prioritize tables, filters, segmented controls, compact summaries, and clear empty/error states over decorative hero sections.

### Creative Coding Demo

Let the canvas/WebGL/SVG scene be the main object. Provide minimal controls, direct manipulation, full-screen entry, and performance-conscious cleanup.

## Final Response

Summarize the concrete changes, files touched, and verification performed. Mention any test or browser verification that could not be run.

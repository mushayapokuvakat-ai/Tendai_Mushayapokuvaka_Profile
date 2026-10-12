# Tendai Mushayapokuvaka Mini-Portfolio

A responsive, accessible, semantic HTML5 profile and mini-portfolio site developed for **Web Technologies (CIS2103) — Africa University**.

---

## Practical Assignment 2 — Responsive Notes

### 1. Breakpoints Tested
Testing was performed using the browser device toolbar across three standard viewport widths:
* **Mobile (~375px — iPhone / small smartphone)**:
  * Verified 1-column layout flow for About, Skills, and Projects.
  * Verified that Header and Navigation wrap naturally without horizontal scrolling.
  * Contact form fields stack vertically (`grid-cols-1`) with comfortable touch targets (inputs and submit button).
* **Tablet (~768px — iPad / medium tablet)**:
  * Verified progressive enhancement via `@media (min-width: 768px)`.
  * Header transitions into a horizontal bar (`md:flex-row`).
  * About and Projects cards reflow smoothly into 2-column grids (`repeat(2, 1fr)`).
  * Contact form input pairs (Name/Email, Phone/Reason) split into 2-column grid rows (`md:grid-cols-2`).
* **Desktop (~1280px — laptop / widescreen)**:
  * Verified full desktop grid layout via `@media (min-width: 1024px)`.
  * Skills grid expands to 4 balanced columns (`repeat(4, 1fr)`).
  * Projects grid expands to 3 cards per row (`repeat(3, 1fr)`).
  * Text line-lengths and main container max-width (`1000px`) maintain optimal typographic readability.

---

### 2. Layout Strategy: Flexbox vs. CSS Grid

* **Where Flexbox was used and why:**
  * **Header & Primary Navigation**: Flexbox was chosen because the navigation is a 1-dimensional row/column system where content alignment, spacing distribution (`justify-between`, `items-center`), and dynamic wrapping (`flex-wrap`) are ideal.
  * **Social & Contact Links**: `display: flex` with `flex-wrap: wrap` and `justify-content: center` ensures social badges stay centered and flow gracefully across screen widths.
  * **Numbered Headings (`.numbered-heading`)**: Flexbox aligns the section counter (`01.`), title text, and the decorative horizontal extending line (`flex-grow: 1`) along a single horizontal axis.

* **Where CSS Grid was used and why:**
  * **Skills Categories (`.skills-grid`)**: CSS Grid is used because skills represent a 2-dimensional matrix of cards. Using `grid-template-columns: 1fr` on mobile, `repeat(2, 1fr)` on tablet, and `repeat(4, 1fr)` on desktop guarantees equal-height cards and uniform column tracks without floats or manual width calculations.
  * **About Dual Cards (`.about-grid`)**: Configured with `display: grid; grid-template-columns: repeat(2, 1fr); gap: 1.5rem;` on screens `min-width: 768px`, keeping the Engineering and Tutoring cards uniformly proportioned.
  * **Selected Projects (`.projects-grid`)**: Managed with `repeat(3, 1fr)` on desktop and `repeat(2, 1fr)` on tablet, maintaining consistent card heights across varying text lengths.
  * **Contact Form Field Pairs**: Tailwind's `grid grid-cols-1 md:grid-cols-2 gap-5` ensures paired input fields align precisely.

---

### 3. Styling Architecture: Tailwind CSS vs. External CSS Split

* **Tailwind Utility-First Sections:**
  * **Header & Navigation (`<header>`)**: Built using Tailwind utilities (`sticky top-0`, `flex flex-col md:flex-row`, `items-center`, `justify-between`, `backdrop-blur-md`). Utilizes responsive variants (`sm:`, `md:`) to adapt from a stacked mobile header to an inline desktop header.
  * **Contact Section & Form (`#contact`, `<form>`)**: Built using Tailwind utilities (`grid grid-cols-1 md:grid-cols-2`, `space-y-5`, `w-full rounded p-2.5`). Responsive variants (`sm:`, `md:`) control input grid transitions and responsive button widths.
* **Custom External Stylesheet (`style.css`):**
  * Houses the global design tokens (`:root` CSS variables for dark navy/teal color palette, font pairings).
  * Enforces a strict **mobile-first CSS architecture** using hand-written `@media (min-width: 768px)` and `@media (min-width: 1024px)` media queries.
  * Styles the semantic content blocks (About, Skills, Projects, Certifications, Education) to demonstrate mastery of vanilla CSS Grid and Flexbox layouts.

---

### 4. Preservation of Semantic HTML5 & Accessibility
All initial semantic elements from Practical Assignment 1 have been preserved:
* `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`.
* All project cards retain `<article>` semantic elements.
* Accessible skip-to-content link (`<a href="#main-content" class="skip-to-content">`).
* The complete accessible Contact Form with associated `<label for="...">` elements, inputs (`text`, `email`, `tel`), `<select>`, `<textarea>`, and native HTML5 validation constraints (`required`, `minlength`, `pattern`, `autocomplete`).

---

## AI-Assisted Content

See `PROMPT_LOG.md` for the prompt, raw AI output, and edited final version used for the About Me section.

---

## Structure

* `index.html` — Semantic HTML5 profile page styled with Tailwind utility classes and mobile-first custom CSS.
* `style.css` — Mobile-first stylesheet with design tokens, custom Grid/Flexbox layouts, and `min-width` media queries.
* `PROMPT_LOG.md` — AI-assisted content log.
* `README.md` — Project documentation and Practical Assignment 2 responsive notes.

---

## Commit History

1. `Add initial semantic HTML5 skeleton with About and Skills sections`
2. `Expand structure: add Projects, Certifications, Education and full in-page navigation`
3. `Add Contact Me form with native HTML5 validation and finalize accessibility`
4. `Added a profile picture.`
5. `Refactor to mobile-first CSS architecture and restore full semantic HTML5 structure`
6. `Implement Tailwind utility-first styling on Header and Contact sections with responsive variants`
7. `Add comprehensive Responsive Notes and rubric documentation in README.md`

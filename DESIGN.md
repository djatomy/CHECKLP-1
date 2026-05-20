# Design System Strategy: High-End Editorial for OOH Advertising

## 1. Overview & Creative North Star
**Creative North Star: "The Authoritative Billboard"**

This design system moves beyond the standard "corporate website" template to mirror the physical world of Out-of-Home (OOH) advertising: bold, high-impact, and undeniably professional. We are translating the heritage of Seikosha Vietnam into a digital experience that feels as structural and permanent as the billboards they manage. 

The aesthetic breaks the traditional web grid by utilizing **intentional asymmetry** and **overlapping layers**. Like a perfectly placed advertisement in a bustling city, elements should feel purposeful and bold. We combine the reliability of deep blues with the energetic "pop" of high-visibility yellows, all framed within a sophisticated, multi-layered surface architecture.

---

## 2. Colors: Tonal Depth & Soul
We avoid flat, lifeless color blocks. Our palette is designed to create a hierarchy of focus through light and saturation.

*   **Primary (`#1d6473`):** Use for core structural trust. This is our "Ink" color.
*   **Secondary (`#6e5e00` / `#fedb00`):** These are our "Action" colors. Use the bright yellow for high-contrast callouts and the darker variant for refined labels.
*   **Tertiary (`#bc0003`):** Reserved strictly for "Stamps of Excellence" or urgent highlights, mimicking physical ink stamps on a portfolio.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to separate sections. We define boundaries through background shifts. A section using `surface-container-low` should sit adjacent to a `surface` section. The change in tone is the divider.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
*   **Base:** `surface` (#fff7fe)
*   **Sections:** `surface-container-low` (#f9f1f8) or `surface-container` (#f3ebf3).
*   **Interactive Cards:** Use `surface-container-lowest` (#ffffff) to create a natural "lift" off the page.

### Signature Textures
Apply subtle linear gradients (e.g., `primary` to `primary_container`) to hero sections and primary buttons. This adds a "visual soul"—a slight sheen that suggests quality and depth rather than a generic digital fill.

---

## 3. Typography: The Editorial Voice
Our typography scale is designed for instant readability with an authoritative edge.

*   **Display & Headlines (Plus Jakarta Sans):** A clean, geometric sans-serif that supports the bold character weight required for Japanese and Vietnamese scripts. Use **Display-LG (3.5rem)** for hero statements to command attention.
*   **Body & Titles (Inter):** Chosen for its exceptional legibility. The slightly tighter tracking in Inter provides a modern, "Swiss-style" editorial feel.
*   **Labels (Work Sans):** Used for metadata and "stamps." The distinct character of Work Sans separates technical information from the narrative body text.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are often too "heavy" for a premium brand. We use **Tonal Layering** to convey importance.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. This provides a soft, organic elevation.
*   **Ambient Shadows:** For floating elements (like fixed navigation or featured "stamps"), use a highly diffused shadow: `x: 0, y: 12, blur: 40, color: rgba(30, 26, 31, 0.06)`. Note the use of our `on_surface` color for the shadow tint—never use pure black.
*   **The "Ghost Border" Fallback:** If a container needs more definition (e.g., an image overlay), use the `outline_variant` token at **15% opacity**.
*   **Glassmorphism:** For mobile navigation or secondary overlays, use `surface_container_lowest` at 80% opacity with a `backdrop-filter: blur(12px)`. This keeps the layout feeling integrated and high-end.

---

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_container`), `rounded-full`, white text.
*   **Secondary (Highlight):** `secondary_container` (#fedb00) with `on_secondary_container` (#716000) text. Use for "Inquiry" actions.
*   **Tertiary:** No background. Bold text in `primary` with a subtle `primary_fixed_dim` underline.

### The "Stamp" Component
A signature component for this system. A circular or slanted rectangular container using `tertiary` or `secondary` colors, placed with a **-5 degree rotation** to overlap the corner of an image or card. This mimics physical OOH markups and "Successful" project stamps seen in the reference material.

### Cards & Lists
*   **Card Style:** `rounded-xl`, `surface-container-lowest` background. 
*   **Spacing:** Use `spacing-8` (2rem) for internal padding to ensure the content "breathes."
*   **Rule:** Forbid the use of divider lines between list items. Use `spacing-4` (1rem) gaps and a subtle background shift on hover (`surface-container-high`).

### Input Fields
*   **Style:** Minimalist. No border—only a `surface-container-high` bottom bar that expands to a 2px `primary` bar on focus.

---

## 6. Do's and Don'ts

### Do
*   **Do** overlap elements. Let a "Stamp" component slightly overlap a photo of a billboard to create physical depth.
*   **Do** use asymmetrical layouts. A 60/40 split is more editorial and premium than a 50/50 split.
*   **Do** prioritize whitespace. Premium brands are defined by the space they *don't* fill.

### Don't
*   **Don't** use 100% opaque, high-contrast borders. It breaks the "Authoritative Billboard" illusion.
*   **Don't** use generic system icons. Use thick-stroke, custom-rounded iconography that matches the `rounded-lg` (1rem) scale of our containers.
*   **Don't** use standard shadows. If it looks like a "Photoshop Drop Shadow," it's too heavy. It should look like "Ambient Light."
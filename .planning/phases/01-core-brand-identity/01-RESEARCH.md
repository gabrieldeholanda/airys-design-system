# Phase 1: Core Brand Identity - Research

**Researched:** 2026-05-30
**Domain:** Design System Brand Configuration (Colors, Typography, Logos)
**Confidence:** HIGH

<user_constraints>
## User Constraints (from CONTEXT.md)

### Locked Decisions
- **D-01:** Custom font "Surgena" will be used as the primary typeface. Source files are located in `public/fonts/Surgena`.
- **D-02:** Generate a full 100-900 scale for every brand color to ensure future scalability.
- **D-03:** Output the brand assets as a Tailwind CSS configuration considering standard web integration needs.
- **D-04:** Use existing logo assets located in `public/Airys-Logo` (SVG and PNG formats are available for Dark, Light, and Minimal variants).

### the agent's Discretion
None

### Deferred Ideas (OUT OF SCOPE)
None
</user_constraints>

<architectural_responsibility_map>
## Architectural Responsibility Map

| Capability | Primary Tier | Secondary Tier | Rationale |
|------------|-------------|----------------|-----------|
| CSS Variables & Font Loading | Browser/Client | — | Typography and Colors are fundamentally CSS implementations that govern the client's visual rendering. |
| Design Tokens (Tailwind) | Build Tooling | — | Tailwind configuration operates at build time to generate utility classes for the browser. |
| Logo Assets | CDN/Static | — | Logos are static SVGs/PNGs served directly to the client. |

</architectural_responsibility_map>

<research_summary>
## Summary

Researched the standard approaches for defining a brand identity within a modern web project utilizing Tailwind CSS. The standard and most scalable approach involves defining foundational brand tokens (colors, fonts) centrally in a `tailwind.config.ts` or via a global CSS layer with semantic variables, specifically optimized for dark mode.

Key finding: Instead of hardcoding hex codes throughout the UI, setting up a 100-900 color scale in Tailwind using raw CSS variables (e.g., `hsl(var(--primary-500))`) provides the most flexibility for theming (like dark mode switching). The custom font "Surgena" must be declared via `@font-face` in the global CSS and then mapped in Tailwind's `fontFamily` config.

**Primary recommendation:** Establish a base `styles/globals.css` (or `index.css`) containing the `@font-face` declarations and CSS variables for the color scale. Then map these to `tailwind.config.ts`.
</research_summary>

<standard_stack>
## Standard Stack

### Core
| Library | Version | Purpose | Why Standard |
|---------|---------|---------|--------------|
| tailwindcss | v3 or v4 | Styling and Design Tokens | The industry standard for utility-first styling and token management in web projects. |
| CSS | Modern | Font Loading | Native `@font-face` is required to load the local Surgena font files. |

### Alternatives Considered
| Instead of | Could Use | Tradeoff |
|------------|-----------|----------|
| Tailwind CSS | Vanilla CSS Modules | Less portable for a "Design System" which is often consumed by multiple apps. Tailwind is explicitly requested as the token output format. |
| Raw CSS Colors | Style Dictionary | Overkill for a web-first design system MVP; Tailwind config is sufficient. |

</standard_stack>

<architecture_patterns>
## Architecture Patterns

### Recommended Project Structure
```
/
├── public/
│   ├── fonts/Surgena/     # Font files
│   └── Airys-Logo/        # Brand logos
├── src/
│   ├── styles/
│   │   └── globals.css    # @font-face and CSS variables
├── tailwind.config.ts     # Maps CSS variables to Tailwind utilities
```

### Pattern 1: Semantic Tailwind Configuration
**What:** Mapping global CSS variables to Tailwind's theme extension.
**When to use:** When supporting dark mode and future theming.
**Example:**
```css
/* globals.css */
@layer base {
  :root {
    --primary-500: 220 90% 50%; /* HSL values without the hsl() function */
  }
}
```
```javascript
/* tailwind.config.ts */
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: {
          500: 'hsl(var(--primary-500))',
        }
      },
      fontFamily: {
        sans: ['Surgena', 'sans-serif'], /* Setting Surgena as default sans */
      }
    }
  }
}
```

### Pattern 2: Local Font Loading
**What:** Using `@font-face` to load custom fonts locally to avoid FOUT and layout shifts.
**When to use:** For custom premium fonts like "Surgena" located in `public/fonts/`.
**Example:**
```css
@font-face {
  font-family: 'Surgena';
  src: url('/fonts/Surgena/Surgena-Regular.woff2') format('woff2');
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}
```
</architecture_patterns>

<dont_hand_roll>
## Don't Hand-Roll

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| Color Utilities | Custom CSS classes for every color | Tailwind Config | Tailwind auto-generates background, text, border, and ring utilities for free. |

**Key insight:** Let Tailwind do the heavy lifting for utility generation. We only need to define the foundational tokens (variables).
</dont_hand_roll>

<common_pitfalls>
## Common Pitfalls

### Pitfall 1: Incorrect CSS Variable Format for Tailwind
**What goes wrong:** Tailwind opacity modifiers (like `bg-primary/50`) break.
**Why it happens:** Defining CSS variables with the `hsl()` or `rgb()` wrapper natively, rather than just the raw values.
**How to avoid:** Define CSS variables as raw numbers (`--primary: 220 90% 50%;`) and wrap them in the Tailwind config (`hsl(var(--primary))`).

### Pitfall 2: Font Layout Shift
**What goes wrong:** Text flashes in a fallback font before Surgena loads.
**Why it happens:** Missing `font-display` property.
**How to avoid:** Always include `font-display: swap;` in `@font-face` declarations.
</common_pitfalls>

<code_examples>
## Code Examples

### Tailwind Dark Mode Strategy
```css
@layer base {
  :root {
    --background: 0 0% 100%;
    --foreground: 0 0% 0%;
  }
  .dark {
    --background: 0 0% 0%;
    --foreground: 0 0% 100%;
  }
}
```
</code_examples>

<sota_updates>
## State of the Art (2024-2025)

| Old Approach | Current Approach | When Changed | Impact |
|--------------|------------------|--------------|--------|
| SCSS variables | CSS Custom Properties | ~2020 | CSS variables can be updated at runtime (e.g., toggling `.dark` class) allowing real-time theme switching without recompilation. |
</sota_updates>

<sources>
## Sources

### Primary (HIGH confidence)
- Tailwind CSS Documentation - Customizing Colors and Fonts
- Standard web typography practices for local font loading
</sources>

<metadata>
## Metadata

**Research scope:**
- Core technology: CSS Variables, Tailwind CSS
- Patterns: Dark Mode scaling, Local Font Loading

**Confidence breakdown:**
- Standard stack: HIGH - Industry standard approach
- Architecture: HIGH - Best practice for React/Next.js/Vite with Tailwind
- Pitfalls: HIGH - Common Tailwind configuration gotchas are well documented

**Research date:** 2026-05-30
**Valid until:** 2026-06-30
</metadata>

---

*Phase: 01-core-brand-identity*
*Research completed: 2026-05-30*
*Ready for planning: yes*

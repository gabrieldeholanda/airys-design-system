# Phase 1: Core Brand Identity - Context

**Gathered:** 2026-05-30
**Status:** Ready for planning

<domain>
## Phase Boundary

Defining the foundational brand assets including logo variations, color palette optimized for dark mode, and typography scale.

</domain>

<decisions>
## Implementation Decisions

### Typography Selection
- **D-01:** Custom font "Surgena" will be used as the primary typeface. Source files are located in `public/fonts/Surgena`.

### Color Palette Scope
- **D-02:** Generate a full 100-900 scale for every brand color to ensure future scalability (Standard GSD best practice applied since skipped).

### Design Tokens Format
- **D-03:** Output the brand assets as a Tailwind CSS configuration (Standard GSD best practice applied since skipped) considering standard web integration needs.

### Logo Formats
- **D-04:** Use existing logo assets located in `public/Airys-Logo` (SVG and PNG formats are available for Dark, Light, and Minimal variants).

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Brand Identity Assets
- `public/fonts/Surgena/` — Source files for the Surgena typeface
- `public/Airys-Logo/` — SVG and PNG logo exports for Dark, Light, NoColor, and Minimal variations.
- `https://www.figma.com/design/vGR48Q1nEthEG5y9wK2JNk/Airys---Brandkit?node-id=0-1` — Figma Brandkit
- `https://www.figma.com/design/vGR48Q1nEthEG5y9wK2JNk/Airys---Brandkit?node-id=435-2399&m=dev` — Figma Dev Mode Reference

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- `public/Airys-Logo/Airys-Dark-BG.svg` and related files: Ready to be used for site headers and branding components.
- `public/fonts/Surgena/*`: Ready to be imported via `@font-face` in global CSS.

### Established Patterns
- (None yet, this is the foundational phase)

### Integration Points
- Global CSS or Tailwind config needs to be updated with the fonts and colors.

</code_context>

<specifics>
## Specific Ideas

- Scan/map the existing brand assets (logos, fonts) from the provided paths.
- Reference existing static design from social media and ad creatives (available in the provided Figma links).

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope

</deferred>

---

*Phase: 01-Core Brand Identity*
*Context gathered: 2026-05-30*

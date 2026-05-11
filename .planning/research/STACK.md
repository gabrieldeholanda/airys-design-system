# Stack Research: Airys Design System

## Standard Stack for Design Systems (2026)

- **Design:** Figma (Standard for tokens and components)
- **Token Management:** Style Dictionary / Tokens Studio (For syncing Figma tokens to code)
- **Documentation:** Storybook (Component playground) + Zeroheight (Brand guidelines)
- **Styling:** Vanilla CSS Variables / Tailwind CSS (Depending on implementation target)
- **Frameworks:** React/TypeScript (Standard web component target)

## Rationale
Using Figma combined with automated token management ensures that the "dark mode aesthetic" and typography scales remain synchronized between the design team and the developers.

## Anti-Patterns
- **Avoid:** Hardcoded hex values in code. Always use design tokens to support easy theming.
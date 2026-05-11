# Pitfalls Research: Airys Design System

## Common Mistakes
- **Accessibility in Dark Mode**: Insufficient contrast ratios between dark surfaces and text.
  - *Prevention*: Strictly validate all text colors against WCAG AA standards.
- **Over-engineering Components**: Building components with too many props/variants early on.
  - *Prevention*: Stick to MVP components. Add variants only when required by the landing page/deck.
- **Detached Tokens**: Developers using hex codes because tokens are too hard to find.
  - *Prevention*: Ensure tokens are automatically exported to CSS variables and well-documented.
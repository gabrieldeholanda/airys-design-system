# Phase 2 Context — Core UI Components

## Domain
Implement the base UI components relying on Phase 1 design tokens to establish a consistent look and feel across forms and interactions.

## Canonical Refs
- `UI-SPEC.md`: UI Design Contract for Phase 2

## Code Context
- `src/styles/globals.css`: Contains CSS variables for color palette and fonts
- `tailwind.config.ts`: Tailwind configuration mapped to design tokens

## Decisions

### Component Implementation Approach
- Use Radix UI for accessibility primitives

### Form Component Structure
- Use Compound components (e.g., `<Form.Input />`)

### Modal State Management
- Controlled via external state

### Button Variants Styling Pattern
- Use `cva` (class-variance-authority) for variant management

## the agent's Discretion
- Internal component file structure
- Specific tailwind utility classes for layout within components
- Component prop naming (except where dictated by standard React patterns)

## Deferred Ideas
- None

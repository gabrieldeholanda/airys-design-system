# Phase 1: Core Brand Identity - UI Spec

**Status:** Auto-generated (Brand Config)
**Date:** 2026-05-30

## Overview
This phase does not implement specific UI screens. It configures the foundational design tokens (colors, fonts, logos) that downstream UI components will consume.

## Theming Architecture
- **Primary Theme:** Dark Mode (default).
- **Tokens:** CSS Custom Properties injected into Tailwind config.
- **Typography:** Surgena font family.

## Visual Rules
1. Never hardcode hex colors; always use semantic variables (e.g., `bg-primary-500`).
2. Adhere to Tailwind 100-900 scaling.
3. Logos should use exact SVGs provided in `/public/Airys-Logo/`.

## Responsive Design
- Standard Tailwind breakpoints apply for any spacing/layout components generated later.

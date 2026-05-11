# Architecture Research: Airys Design System

## Structure
The design system architecture will flow linearly from primitives to composed assets:

1. **Brand Guidelines**: The foundational rules (Voice, Vibe, Rules).
2. **Design Tokens**: The atomic values (Colors, Spacing, Typography).
3. **Core Components**: Reusable UI elements built strictly from tokens.
4. **Composed Assets**: High-level marketing materials (Decks, Landing pages) built using components and brand rules.

## Data Flow
Figma Tokens -> JSON Export -> Token Translation (Style Dictionary) -> CSS Variables -> Code Components.
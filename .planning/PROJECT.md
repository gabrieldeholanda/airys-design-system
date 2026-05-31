# Airys Design System

## What This Is

A comprehensive design system for Airys and AirysChat, standardizing the brand identity, UI components, and marketing assets (decks, illustrations, landing pages). It serves as the single source of truth for all Airys products and acts as the orchestrator for the **AI Design Squad**—a suite of custom GSD agents that autonomously generate brand-compliant creative assets.

## Core Value

Provide a consistent, modern, and tech-focused dark-mode aesthetic that accelerates development and maintains brand authority across all Airys products. Furthermore, leverage multi-modal AI to autonomously generate marketing creatives at scale without deviating from the design contract.

## Requirements

### Validated

(None yet — ship to validate)

### Active

- [ ] Provide unified dark-mode focused color palette
- [ ] Define modern, sans-serif typography scale
- [ ] Establish core brand identity and logo variations
- [ ] Deliver base UI components (buttons, inputs, modals)
- [ ] Provide marketing and presentation assets (decks, illustrations)
- [ ] Enable autonomous generation of brand-compliant creatives via multi-modal AI agents (AI Design Squad)

### Out of Scope

- Native mobile app components (Focusing on web-first for now)
- Complex 3D animations (Deferred to v2)

## Context

The brand communicates an innovative, professional AI agency scaling business operations. The aesthetic leans heavily towards dark mode, professional results, and high-tech efficiency, as seen on `https://www.airys.com.br/`.

## Constraints

- **Design Tool**: Must be compatible with Figma for design consistency.
- **Theme**: Must heavily prioritize dark mode.
- **Vibe**: Needs to feel professional, authoritative, and humanized.

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Web-first scope | Ensures rapid delivery of core web assets before scaling to mobile | — Pending |

---
*Last updated: Monday, May 11, 2026 after initialization*

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `/gsd-transition`):
1. Requirements invalidated? → Move to Out of Scope with reason
2. Requirements validated? → Move to Validated with phase reference
3. New requirements emerged? → Add to Active
4. Decisions to log? → Add to Key Decisions
5. "What This Is" still accurate? → Update if drifted

**After each milestone** (via `/gsd:complete-milestone`):
1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state
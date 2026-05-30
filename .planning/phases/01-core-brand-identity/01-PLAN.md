---
phase: "01-core-brand-identity"
plan: "01"
type: "execute"
wave: 1
depends_on: []
files_modified: ["tailwind.config.ts", "src/styles/globals.css"]
autonomous: true
must_haves:
  truths:
    - "Surgena font is configured and correctly points to public/fonts/Surgena"
    - "Tailwind colors 100-900 are defined for the Airys brand using CSS variables"
    - "Dark mode color palette mapping is supported"
  artifacts:
    - path: "tailwind.config.ts"
      provides: "Tailwind tokens configuration"
    - path: "src/styles/globals.css"
      provides: "CSS variables and font face rules"
  key_links:
    - from: "tailwind.config.ts"
      to: "src/styles/globals.css"
      via: "Tailwind config consumes CSS variables"
---

<objective>
Configure the foundational brand identity tokens for Airys.
Purpose: Provide the global typography scale and semantic color palette (with dark mode support) to be consumed by all UI components.
Output: globals.css (variables and fonts) and tailwind.config.ts
</objective>

<execution_context>
@.agent/get-shit-done/workflows/execute-plan.md
@.agent/get-shit-done/templates/summary.md
</execution_context>

<context>
@.planning/PROJECT.md
@.planning/ROADMAP.md
@.planning/phases/01-core-brand-identity/01-CONTEXT.md
@.planning/phases/01-core-brand-identity/01-RESEARCH.md
@.planning/phases/01-core-brand-identity/01-UI-SPEC.md
</context>

<tasks>
<task type="auto">
  <name>Create globals.css with CSS Variables and @font-face</name>
  <files>src/styles/globals.css</files>
  <action>Create the globals.css file (and src/styles dir if needed). Define `@font-face` for Surgena pointing to `/fonts/Surgena/*`. Create `:root` and `.dark` blocks defining the 100-900 scale for the primary brand color in raw HSL values.</action>
  <verify>grep_search for --primary-500 in globals.css</verify>
</task>

<task type="auto">
  <name>Create Tailwind Configuration</name>
  <files>tailwind.config.ts</files>
  <action>Create a `tailwind.config.ts` mapping the CSS variables to the `theme.extend.colors` object (using `hsl(var(--color))`), and mapping `fontFamily.sans` to 'Surgena'. Ensure dark mode strategy is set to 'class'.</action>
  <verify>grep_search for Surgena in tailwind.config.ts</verify>
</task>
</tasks>

<verification>
- [ ] CSS file exists with required @font-face and color scale variables
- [ ] Tailwind configuration exports the semantic values
</verification>

<success_criteria>
- Typography is accurately mapped.
- Color scale allows seamless dark mode support.
- Ready for components to consume via `bg-primary-500` etc.
</success_criteria>

<output>
After completion, create `.planning/phases/01-core-brand-identity/01-SUMMARY.md`
</output>

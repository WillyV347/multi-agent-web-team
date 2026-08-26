---
name: component-scaffold
description: Define a frontend component’s purpose, props, states, accessibility, and edge cases before writing code.
---

# Component Scaffold (showcase)

## When to use

Creating a new reusable UI component, or untangling one that grew too many props.

## Define before coding

1. **Purpose** — one sentence
2. **Props** — name, type, required/optional, defaults
3. **States** — default, hover/focus, disabled, loading, empty, error
4. **Accessibility** — role, name, keyboard behavior, contrast notes
5. **Responsive behavior** — what changes at mobile vs desktop
6. **Edge cases** — long labels, missing images, RTL if relevant

## Output

A short markdown scaffold an engineer can implement from. Prefer existing design-system patterns when the project has them; don’t invent a second button.

## Out of scope for this demo

Deep Figma MCP / Code Connect workflows. If a design file exists, note that tokens should come from the design source rather than hard-coded hex values.


<!-- Canonical copy lives at skills/component-scaffold/SKILL.md — keep both in sync. -->

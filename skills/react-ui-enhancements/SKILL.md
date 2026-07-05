---
name: "react-ui-enhancements"
description: "Enforces local React design conventions, Tailwind utility patterns, and styling architectures when building or updating UI features."
useWhen: "The user requests any changes, enhancements, additions, or debugging of React frontend user interfaces, buttons, modals, cards, layouts, or forms."
---

# React UI Consistency and Style Architecture Skill

You must invoke this skill whenever you modify or generate user interface elements in this repository. It ensures absolute alignment with the existing React component ecosystems, atomic patterns, and design primitives.

## 1. Context Collection Protocol (Mandatory First Step)
Before writing or modifying a single line of React code, you MUST execute a discovery phase:
* **Locate Design Tokens**: Check `tailwind.config.js`, `theme.js`, or global CSS files to identify valid color configurations, typography scales, spacing units, and radius parameters.
* **Inspect Siblings**: If modifying a component inside a directory (e.g., `src/components/button/`), inspect existing sibling files to emulate their import layout, TypeScript prop interfaces, and component export styles.
* **Check Global Layouts**: Identify the main wrapper component or layouts to avoid breaking structural grids or global flex contexts.

## 2. Coding and Structural Conventions
* **Component Architecture**: Prefer functional components using TypeScript explicit prop types (`interface Props { ... }`). Do not use implicit styles unless specified.
* **Styling Framework**: Exclusively apply [Tailwind CSS utility patterns](https://github.com/sickn33/antigravity-awesome-skills/blob/main/skills/react-nextjs-development/SKILL.md). Do not embed raw inline styles (`style={{...}}`) unless performing dynamic runtime calculations (e.g., absolute pixel offsets for tracking positions).
* **Class Merging**: Always use a utility helper like `clsx` or `tailwind-merge` if combining conditional variants or merging external `className` parameters into local primitives.
* **Icons**: Standardize on the active icon kit found within the imports of matching files (e.g., Lucide React, Heroicons). Never introduce a new icon package without permission.

## 3. UI Refactoring and Modification Steps
When implementing a new feature or layout variation:
1. **Analyze**: Read the destination component file entirely.
2. **Isolate Changes**: Modify only the functional node requested; do not arbitrarily reorganize unrelated code layout or rewrite existing semantic elements.
3. **Verify Interactive State**: Ensure hover, focus-visible, and disabled states match the color curves and opacity standards established across companion pages.

## 4. Anti-Patterns to Avoid
* Do not introduce hardcoded hex/RGB color strings directly in classes if custom theme keys exist in the configuration.
* Do not bypass responsive prefixes (`sm:`, `md:`, `lg:`) if the rest of the file leverages multi-breakpoint layouts.
* Do not override base element accessibility features; keep aria labels, semantic HTML tags, and clean tab index structures.


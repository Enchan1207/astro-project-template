# AGENTS.md

## project overview

- purpose: research Astro framework and create static website
- package manager: pnpm (you must use pnpm, don't use others)
- tech stack:
  - TypeScript
  - Astro
- formatter: Prettier

## scripts

- `pnpm dev`: run development server
- `pnpm build`: build project
- `pnpm prettier`: check format
- `pnpm prettier:fix`: check and fix format

## project compositions

- `src/` : application root
  - `pages/` : Astro page components
  - `components/` : common or non-page-specific components

## rules

**NOTE**: you must follow these rules

- naming conventions:
  - variables,functions: lowerCamelCase
  - classes,constants,components: PascalCase
  - module: kebab-case
  
# AGENTS.md

## project overview

- purpose: research Astro framework and create static website
- package manager: pnpm
- language: TypeScript
- frameworks: Astro, React
- UI: shadcn/ui, TailwindCSS  
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
    - `ui/` : shadcn/ui generated components (DO NOT MODIFY)
  - `lib/` : generic utilities
    - `utils.ts` : shadcn/ui utilities (DO NOT MODIFY)
  - `styles/` : CSSes (DO NOT MODIFY)

## rules

**NOTE**: you must follow these rules

- You only use pnpm. No other package managers are allowed.
- styling, components:
  - You MUST NOT add any CSS. Inlines and properties are no exception.
  - If you want to add new components, shadcn/ui should be your first choice, followed by TailwindCSS.
- naming conventions:
  - variables,functions: lowerCamelCase
  - classes,constants,components: PascalCase
  - module: kebab-case

### scope of agent actions

- Agents MAY:
  - Modify files under `src/` to add or adjust features.
  - Add new Astro pages and React components when needed.
  - Update this repository’s documentation (`AGENTS.md`, `README.md`) if rules or usage change.

- Agents MUST NOT:
  - Change build configuration (Astro config, Vite config, Tailwind config) unless explicitly instructed.
  - Add or remove dependencies without explicit instruction.
  - Modify files marked as **DO NOT MODIFY**.

### astro architecture rules

- React components are used as Astro islands only.
  - Client directives (`client:load`, `client:idle`, etc.) must be used intentionally and minimally.
- Avoid unnecessary client-side JavaScript.
  - Prefer Astro components over React when interactivity is not required.

### code quality and validation

- All changes MUST satisfy:
  - `pnpm build` completes without errors.
- Automated tests are not required unless explicitly requested.

### file and responsibility boundaries

- `src/pages/`
  - Page composition and data wiring only.
  - Do not place reusable UI logic here.
- `src/components/`
  - Reusable UI and presentation components.
  - Business logic should be minimal.
- `src/lib/`
  - Framework-agnostic utilities.
  - React- or Astro-specific code should NOT be placed here.

### forbidden operations

- Re-generating shadcn/ui components.
- Adding custom CSS files or inline styles.
- Introducing global side effects (e.g. modifying `window` at module scope).

### change rationale

- When modifying existing code, agents MUST:
  - Preserve existing behavior unless a change is explicitly required.
  - Briefly explain the reason for the change in the commit message or response.

### commit message rules (conventional commits)

- Commit messages MUST follow Conventional Commits:
  - format: `<type>(<scope>): <subject>`
  - `<scope>` is recommended; omit only when it adds no value.
- Allowed `<type>`:
  - `feat`, `fix`, `docs`, `refactor`, `test`, `chore`
- Subject line rules:
  - Use imperative mood (e.g. "add", "fix", "update").
  - No trailing period.
  - Keep it concise (aim ≤ 100 chars).

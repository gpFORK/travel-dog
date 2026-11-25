# travel-dog

## Project Overview

`travel-dog` is a TypeScript Node.js project initialized with the Google Gen AI SDK (`@google/genai`).

## Tech Stack & Dependencies

- **Language / Tooling:** TypeScript (`^7.0.2`), `tsx` (`^4.23.15`), `@types/node` (`^26.6.10`)
- **Dependencies:** `@google/genai` (`^3.6.1`)
- **Module System:** `"type": "commonjs"` in `package.json`, with `"module": "nodenext"` and `"target": "esnext"` in `tsconfig.json`

## TypeScript Configuration

`tsconfig.json` enables strict typechecking options:

- `"strict": true`
- `"noUncheckedIndexedAccess": true`
- `"exactOptionalPropertyTypes": true`
- `"verbatimModuleSyntax": true`
- `"isolatedModules": true`
- `"noUncheckedSideEffectImports": true`
- `"moduleDetection": "force"`
- `"skipLibCheck": true`
- `"jsx": "react-jsx"`

## Repository Structure

- `package.json` / `package-lock.json`: Project manifest and dependency lockfile (`main`: `index.js`; no test script configured yet).
- `tsconfig.json`: TypeScript compiler configuration.
- `.github/workflows/`: GitHub Actions workflows for Gemini CLI integration (`gemini-dispatch.yml`, `gemini-invoke.yml`, `gemini-plan-execute.yml`, `gemini-review.yml`, `gemini-scheduled-triage.yml`, `gemini-triage.yml`).
- `.github/commands/`: Custom prompt templates (`gemini-*.toml`) used by the GitHub Actions workflows.
- `.gitignore`: Ignores `.gemini/` and `gha-creds-*.json`.

## Development Commands

- Run a TypeScript file: `npx tsx <path/to/file.ts>`
- Type-check: `npx tsc --noEmit`

## Conventions

- Adhere to the strict TypeScript rules in `tsconfig.json` (use explicit type-only imports where required by `verbatimModuleSyntax` and handle `undefined` from indexed access).
- Keep `.gemini/` state and `gha-creds-*.json` credentials untracked (per `.gitignore`).

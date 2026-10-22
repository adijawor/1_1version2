# Java 21 Console Project

The current Java program prints `Hello, World!` to the console.

## Run the Java program

- Click **Run** to launch the **Run Java 21** workflow.
- Or run `javac -d out src/main/java/Main.java && java -cp out Main` in the Shell.
- Entry point: `src/main/java/Main.java`.
- Requires JDK 21, provided by the existing `.replit` Nix configuration.
- No external dependencies, secrets, or database are needed for this program.
- Compiled classes go into `out/`, which is ignored by Git.
- This is a console program: it exits after printing its message and has no web preview.

## Separate TypeScript scaffold

The workspace also contains a pnpm/TypeScript scaffold. It is not required to run the Java program. The scaffold reference below does not describe Java runtime requirements.

## Run & Operate

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)

## Where things live

_Populate as you build — short repo map plus pointers to the source-of-truth file for DB schema, API contracts, theme files, etc._

## Architecture decisions

_Populate as you build — non-obvious choices a reader couldn't infer from the code (3-5 bullets)._

## Product

_Describe the high-level user-facing capabilities of this app once they exist._

## User preferences

_Populate as you build — explicit user instructions worth remembering across sessions._

## Gotchas

_Populate as you build — sharp edges, "always run X before Y" rules._

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details

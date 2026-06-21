# Traffic Command Center

Smart Traffic Incident Management System — a TanStack Start application for
pinning, analyzing, and dispatching response to traffic incidents (accidents,
congestion, road blocks) with live detection, congestion scoring, and
police personnel/dispatch recommendations.

## Tech Stack

- **Framework:** [TanStack Start](https://tanstack.com/start) (React 19, SSR via Nitro)
- **Routing:** TanStack Router (file-based, `src/routes/`)
- **Styling:** Tailwind CSS v4 + shadcn/ui (Radix UI primitives)
- **Maps:** Leaflet + Leaflet.heat
- **Forms/Validation:** React Hook Form + Zod
- **Data fetching:** TanStack Query
- **Package manager:** [Bun](https://bun.sh)
- **Deployment:** Vercel


 
 
 **For Backend click on the links below** :
- **Routing-API:-** https://github.com/Supratim-2006/Traffic_Routing_API
- **Disruption_API:-** https://github.com/Supratim-2006/Traffic-disruption
- **CrowFlow detector** https://github.com/Supratim-2006/Traffic
- **Final API(ALL APIss Combined):-** https://github.com/Supratim-2006/Traffic_Backend

Follow the README.md files of each GitHub repositories of Backend to deploy the backend in the local machine.

## Prerequisites

- [Bun](https://bun.sh) installed (v1.3+)
  ```bash
  powershell -c "irm bun.sh/install.ps1 | iex"   # Windows
  curl -fsSL https://bun.sh/install | bash       # macOS / Linux
  ```
  Verify with:
  ```bash
  bun -v
  ```
- Node.js is **not** required separately — Bun handles install, dev, and build.

## Getting Started Locally

1. **Clone the repo**
   ```bash
   git clone <repo-url>
   cd traffic-command-center
   ```

2. **Install dependencies**
   ```bash
   bun install
   ```

3. **Set up environment variables**
   Copy the example file (if present) and fill in any required values:
   ```bash
   cp .env.example .env
   ```
   Check `src/server.ts` and any route loaders/server functions for which
   variables are actually required (API keys, service URLs, etc.).

4. **Run the dev server**
   ```bash
   bun run dev
   ```
   Open the URL printed in the terminal (typically `http://localhost:3000`).
   Hot reload is enabled — changes to files under `src/` apply instantly.

## Available Scripts

| Command | Description |
|---|---|
| `bun run dev` | Start the local dev server with hot reload |
| `bun run build` | Production build (client + SSR server bundle via Nitro) |
| `bun run build:dev` | Build in development mode (unminified, useful for debugging build output) |
| `bun run preview` | Serve the production build locally to sanity-check before deploying |
| `bun run lint` | Run ESLint across the project |
| `bun run format` | Auto-format the codebase with Prettier |

## Running a Production Build Locally

```bash
bun run build
bun run preview
```
Or run the built Nitro server directly:
```bash
node dist/server/server.js
```

## Project Structure

```
traffic-command-center/
├── public/                # Static assets
├── src/
│   ├── components/         # UI components (incl. shadcn/ui in components/ui)
│   ├── hooks/               # Custom React hooks
│   ├── lib/                 # Utilities, helpers
│   ├── routes/              # File-based TanStack Router routes
│   │   ├── __root.tsx       # Root layout
│   │   └── index.tsx        # Home / dashboard route
│   ├── types/               # Shared TypeScript types
│   ├── router.tsx           # Router instance setup
│   ├── routeTree.gen.ts     # Auto-generated route tree (do not edit manually)
│   ├── server.ts            # Server entry / server-only logic
│   ├── start.ts             # TanStack Start entry point
│   └── styles.css           # Global styles (Tailwind entry)
├── .lovable/                # Lovable editor sync config
├── components.json          # shadcn/ui config
├── vite.config.ts           # Vite + TanStack Start config (Lovable-wrapped)
├── bunfig.toml               # Bun install behavior (supply-chain guard, etc.)
└── package.json
```

## Note

- Deployed on **Vercel** with the `TanStack Start` framework preset.
  Install Command is overridden to `bun install`; Build Command and Output
  Directory are left at their auto-detected defaults.

## Deployment

Push to the connected branch, or deploy manually:
```bash
vercel --prod
```
See `vercel.com` project settings for environment variables required in
production.

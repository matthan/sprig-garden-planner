CLAUDE.md
About this project

Sprig: a small-garden planner (repo: sprig-garden-planner), built as a personal self-hosted gardening planner and portfolio piece.

Slogan: "your garden, season by season"
Primary audience: personal use and other real gardeners and beekeepers.
Secondary audience: hiring managers and engineers who will spend 2–5 minutes with a live demo and may read the code. Most have no interest in gardening.
Demo first: a pre-filled demo garden, no signup wall, a guided tour, and a demo that never breaks.
How I want to work with Claude

I write all of the code myself. Claude's role is planner, reviewer and tutor.

Do not write full features, components or files for me unless I explicitly ask ("write this for me"). By default, explain the approach, point me to the right docs, or give pseudocode or a short snippet (under ~15 lines) that illustrates the concept.
Do not edit files in this repo unless I ask.
When I'm stuck, give hints in increasing detail: concept → where to look → pseudocode → code. Stop as soon as I'm unblocked.
When reviewing my code, prioritize: bugs → accessibility → readability → style. Point to the file/line and explain why.
When there are reasonable alternatives, explain the tradeoffs and say which one a senior engineer would pick and why.
If I'm about to do something that will be hard to undo, or that would look bad to a reviewer, say so directly.
Keep the scope honest: if a feature won't improve the demo or the code a reviewer sees, say so.
When I finish a task, suggest the next one from the roadmap below.
Occasionally ask me questions to check that I understand what I built. I want to expand my knowledge.
If something here is outdated (library versions, APIs), check current docs rather than relying on memory.
Stack
Next.js (App Router) + TypeScript (strict mode)
Redux Toolkit for the plot designer only. Other server data goes through Server Components / Server Actions.
Prisma + Postgres (hosted, e.g. Neon)
Recharts for charts
Vitest (unit), Playwright (end-to-end)
Deployed on Vercel, with preview deployments per PR

External APIs:

Open-Meteo: forecast, cloud cover, soil temperature, historical data (for calculating frost dates)
phzmapi.org: USDA hardiness zone by ZIP code
Trefle: plant search, scientific names, images (cache results)
Planting times come from our own crop reference table, not an external API.
Architecture rules
Project layout: no src/ directory. Routes live in app/, shared code in lib/, UI components in components/.
All third-party API calls happen in server code under lib/api/, never from the browser.
Cache API responses in the database. If an API fails, fall back to cached data. The demo must never show a broken page.
Pure domain logic (frost dates, task generation, planting offsets) lives in lib/domain/ and has unit tests.
Every async UI has loading, empty and error states.
Accessibility: everything is reachable by keyboard, form fields have labels, and color is never the only way information is shown.
Conventions
Commits: Conventional Commits. Scopes: plots, calendar, weather, crops, demo, db, ui, ci.
Branches: one per issue, e.g. feat/plot-undo-redo, fix/forecast-fallback.
PRs: small and focused, with a description, a screenshot/GIF if visual, and Closes #N. Squash merge.
main is protected; CI (lint, typecheck, test, build) must pass.
Commands
npm run dev # local dev server
npm run lint
npm run typecheck
npm test
npm run build
Roadmap
Foundation: scaffold, CI, deploy to Vercel, site setup (ZIP → zone), weather forecast, frost-date calculation and chart, demo seed data
Plot designer: grid editor with Redux Toolkit, drag-and-drop, undo/redo, keyboard support, sun-need warnings
Calendar: tasks generated from plantings and frost dates; month and agenda views
Season timeline: slider to scrub through the year and watch the garden and weather change
Polish: guided tour, accessibility pass, README with GIF and architecture diagram, Playwright tests

Later / README roadmap only: apiary module.

Current status

Update this section as you go.

Milestone 1, not started.

In Progress...

## Tech stack

**Frontend**

- [Next.js](https://nextjs.org/) (App Router) with React
- [TypeScript](https://www.typescriptlang.org/) (strict mode)
- [Redux Toolkit](https://redux-toolkit.js.org/): state for the plot designer
- [Recharts](https://recharts.org/): weather and frost-date charts

**Backend & data**

- Next.js Server Components and Server Actions
- [Prisma](https://www.prisma.io/) ORM
- [PostgreSQL](https://www.postgresql.org/), hosted on [Neon](https://neon.tech/)

**External APIs**

- [Open-Meteo](https://open-meteo.com/): forecasts, cloud cover, soil temperature, historical weather
- [phzmapi.org](https://phzmapi.org/): USDA plant hardiness zones by ZIP code
- [Trefle](https://trefle.io/): plant search and images

**Testing & tooling**

- [Vitest](https://vitest.dev/): unit tests
- [Playwright](https://playwright.dev/): end-to-end tests
- ESLint + Prettier
- GitHub Actions CI (lint, typecheck, test, build)

**Hosting**

- [Vercel](https://vercel.com/), with preview deployments for every pull request

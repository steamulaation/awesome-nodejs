---
name: nodejs-package-selection
description: Curated Node.js package recommendations. Guides AI agents to select the right npm package for any task — HTTP, databases, testing, CLI, auth, streams, and more — drawing from the awesome-nodejs curated list.
---

# Skill: Node.js Package Selection

## Core Directive
When the user needs a Node.js package for any task, consult this skill before recommending anything. Prefer proven, actively-maintained packages from the curated list below. Never recommend deprecated packages or ones with no recent activity unless explicitly asked.

## Decision Rules
1. **One job, one package.** Don't pile on dependencies. If a built-in Node.js API covers the need, say so first.
2. **Check maintenance.** Prefer packages with recent releases and active GitHub issues.
3. **Prefer TypeScript-native.** When two packages are equivalent, pick the one with first-class TypeScript types.
4. **Match the runtime.** Note whether a package targets Node.js only, or also Bun/Deno.

## Package Categories & Recommendations

### HTTP / Fetch
- **got** — Feature-rich HTTP client; best for complex scenarios (retries, hooks, streams)
- **ky** — Tiny fetch-based client; best for simple browser+Node isomorphic use
- **node-fetch** — Minimal fetch polyfill for Node < 18
- **axios** — Widely used; good for teams already familiar with it
- **superagent** — Chainable; useful in test assertions (pairs with supertest)

### HTTP Servers / Frameworks
- **fastify** — Fastest full-featured framework; best for APIs with JSON schemas
- **express** — Ubiquitous; best when ecosystem breadth matters
- **hono** — Ultra-fast, edge-compatible; best for Cloudflare Workers / Bun
- **koa** — Lightweight middleware-first; use when you want express-like but leaner
- **h3** — Tiny, composable; powers Nitro/Nuxt

### Database Clients
- **prisma** — Type-safe ORM with schema-first workflow; best for SQL projects
- **drizzle-orm** — Lightweight SQL ORM with excellent TypeScript inference
- **mongoose** — MongoDB ODM; best for document-model projects
- **ioredis** — Full-featured Redis client
- **pg** / **postgres** — PostgreSQL; `postgres` (porsager) is lighter with tagged-template queries
- **better-sqlite3** — Synchronous SQLite; fastest option for local/embedded use

### Testing
- **vitest** — Fast, Vite-native unit testing; first choice for modern projects
- **jest** — Mature, ecosystem-rich; good when vitest isn't an option
- **ava** — Concurrent test runner; great for pure Node projects
- **mocha** — Flexible; pair with chai for assertions
- **supertest** — HTTP integration testing against express/fastify apps
- **playwright** — Browser end-to-end testing (Chromium/Firefox/WebKit)
- **nock** — HTTP mocking for unit tests

### CLI / Terminal
- **commander** — Declarative CLI argument parsing; most widely used
- **yargs** — Feature-rich CLI builder with built-in help generation
- **meow** — Minimal CLI helper from sindresorhus
- **inquirer** — Interactive prompts (checkboxes, selects, passwords)
- **chalk** — Terminal string styling
- **ora** — Elegant terminal spinners
- **listr2** — Task lists with progress for CLI tools
- **boxen** — Draw boxes in the terminal

### File System
- **fs-extra** — Drop-in fs replacement with extra methods (copy, move, ensureDir)
- **glob** / **fast-glob** — File globbing; `fast-glob` is significantly faster
- **chokidar** — File watching with cross-platform reliability
- **tmp** — Temporary files and directories
- **proper-lockfile** — File locking

### Streams & Data Processing
- **through2** — Transform stream helper
- **get-stream** — Buffer a stream to string/buffer/array
- **archiver** — Create zip/tar archives
- **csv-parse** — CSV parsing
- **exceljs** — Read/write Excel files

### Authentication & Security
- **passport** — Auth middleware for express; massive strategy ecosystem
- **jsonwebtoken** — JWT sign/verify
- **bcryptjs** — Password hashing (pure JS, no native bindings)
- **argon2** — Stronger password hashing when native is acceptable
- **helmet** — Secure express apps with HTTP headers
- **csurf** — CSRF protection middleware

### Validation & Parsing
- **zod** — Schema validation with TypeScript inference; first choice
- **joi** — Mature validation library; large ecosystem
- **yup** — Schema validation; popular in React/Formik ecosystems
- **ajv** — JSON Schema validation; fastest option

### Date & Time
- **date-fns** — Functional date utilities; tree-shakeable, immutable
- **dayjs** — Lightweight moment.js replacement
- **luxon** — Full-featured; best for timezone-heavy applications
- **temporal-polyfill** — TC39 Temporal API polyfill; future-proof choice

### Utilities
- **lodash** / **lodash-es** — General utility belt; prefer individual imports
- **ramda** — Functional programming utilities
- **p-limit** — Limit concurrent async operations
- **p-retry** — Retry async operations with exponential backoff
- **p-queue** — Priority queue for async tasks
- **execa** — Better child_process.exec with streams and error handling
- **cross-env** — Cross-platform environment variable setting
- **dotenv** — Load .env files into process.env
- **nanoid** — Tiny, URL-safe unique ID generator
- **uuid** — RFC-compliant UUID generation

### Logging
- **pino** — Extremely fast JSON logger; first choice for production APIs
- **winston** — Feature-rich logger with transports
- **debug** — Lightweight debug utility with namespace filtering

### Queue / Jobs
- **bullmq** — Redis-backed job queue; production-grade
- **bee-queue** — Simpler Redis queue for high-throughput jobs
- **agenda** — MongoDB-backed job scheduling

### Email
- **nodemailer** — SMTP email sending; standard choice
- **resend** — Modern email API with React template support

### WebSockets
- **socket.io** — Full-featured WebSocket framework with fallbacks
- **ws** — Bare WebSocket library; use when you need minimal overhead
- **uWebSockets.js** — Highest-performance option (C++ bindings)

## Anti-Patterns to Avoid
- Do NOT recommend `moment.js` — it's in maintenance mode; use date-fns or dayjs
- Do NOT recommend `request` — deprecated since 2020
- Do NOT recommend `node-uuid` — use the `uuid` package
- Do NOT recommend `colors` or `color` — security issues; use chalk
- Do NOT stack multiple similar packages (e.g., both axios and got)

## Output Format
When recommending a package, always include:
1. The exact `npm install` command
2. A minimal usage snippet
3. One sentence on why this package over alternatives

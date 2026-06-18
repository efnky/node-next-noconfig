# node-next-noconfig 🔴

Negative Next.js fixture: a Next.js app that is **missing the usual deploy signals**.

- `next.config.js` — **absent**
- `package.json` `start` script — **absent** (only `dev` and `build`)
- `pages/index.js` — a trivial page

## Why this is problematic
With no `next.config.js` and **no `start` script**, the deployer has no explicit
way to know how to **start** the app after building. It must either guess
(`next start`) or fail to resolve a start command — which is the behavior under test.

## Expected detection
- Language: Node
- Framework: Next.js (from the `next` dependency)
- Start command: **unresolved** — no `start` script to run, no config to hint mode

## Run (locally you'd have to invoke Next directly)
```bash
npm install
npm run build
npx next start
```

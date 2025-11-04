
# AP Econ Game 🎮📈

AP Econ Game is an educational web application that helps students practice AP Macroeconomics concepts through an engaging, game-based experience. Players answer multiple-choice economics questions to defeat enemies and progress through levels — a blend of learning and lightweight gameplay designed for classroom use and self-study.

## Highlights ✨

- 🎯 Purpose-built for AP Macroeconomics practice
- ⚔️ Game mechanics combine question answering with simple combat/score mechanics
- 🏆 Leaderboard and player persistence for friendly competition
- 🧩 Built with modern web technologies and TypeScript

## Notable features ⭐

- 📚 Quiz-driven gameplay: correct answers damage monsters and advance the player
- 🏁 Leaderboard: stores and serves high scores via an API route
- ♿ Responsive UI with accessibility-minded components
- 🤖 Extensible question generation and AI-assisted content in `src/ai/`

## Tech stack 🛠️

- Next.js (App Router) + React + TypeScript
- Tailwind CSS for styling
- Firebase (client libraries) for any planned auth / storage integrations
- Redis for fast ephemeral data (score/leaderboard usage)
- GenKit (AI tooling) used for question generation workflows

## Quick demo (local) 💻

These instructions assume you have Node.js and npm installed.

1. 🧩 Install dependencies

```bash
npm install
```

2. 🚀 Run the dev server (Next.js)

```bash
npm run dev
# The dev server uses port 9002 by default (see `package.json` script)
```

3. 🏗️ Build for production

```bash
npm run build
npm start
```

## Project structure (high level) 📁

- `src/` — application source code
	- `app/` — Next.js routes, layout and pages
	- `app/components/game/` — core game components (Player, Monster, Projectiles, UI modals)
	- `ai/` — AI flows and generation helpers used to create or augment question content
	- `lib/`, `hooks/`, `types/` — utilities, custom hooks, and shared types
- `data/leaderboard.json` — sample or seed leaderboard data
- `public/` — static assets

## Key code 🔎

- Leaderboard API: `src/app/api/leaderboard/route.ts`
- Game entry & page: `src/app/page.tsx` and `src/app/components/game/*`
- Question modal and game logic: `src/app/components/game/QuestionModal.tsx`

## Development notes ⚙️

- The app is written in TypeScript and uses modern React features (hooks, the Next.js App Router). The `package.json` includes scripts for development (`dev`), build (`build`), and start (`start`). The dev server runs on port `9002` per `npm run dev`.
- AI-assisted generation and experimentation live in `src/ai/`; these are development-only utilities and can be started with the `genkit:dev` script.
- The project favors small, composable UI components (see `src/app/components/ui/`) and tries to keep presentation separate from game logic.

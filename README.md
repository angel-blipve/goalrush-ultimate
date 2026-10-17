# ⚽ GoalRush Ultimate

A full football (soccer) career game that runs in your browser — build a legend on the pitch or a dynasty on the bench.

![Next.js](https://img.shields.io/badge/Next.js-16-black) ![TypeScript](https://img.shields.io/badge/TypeScript-5-blue) ![Prisma](https://img.shields.io/badge/Prisma-SQLite-2D3748) ![Tailwind](https://img.shields.io/badge/Tailwind-4-38bdf8)

## ✨ Features

### 🏃 Player Career
- **Create a custom player** — name, position, nationality, age, preferred foot, height, plus an 84-point attribute budget with a live OVR/potential preview, and pick your starting club.
- Or start as a **real young star** from the built-in player registry.

### 🧠 Manager Career
- **Create your own team** — team name, crest & kit designer (presets + color pickers), league choice and strength slider. The game generates a fictional 16-man squad for your club.
- Or take charge of a **real club** with full fixtures, cup runs and youth regeneration each season.

### 🎮 Match Engine
- Text-simulated matches with lineups built from the runtime player registry, live score progression and post-match growth.

### 📱 Device-Based Login & Saves (no Google account needed)
- Each browser is a **Device**; each device holds **local profile slots** ("Who's playing?").
- Optional **4–6 digit PIN** locks a profile.
- The **first profile created on a device becomes the Owner**.
- Saves are isolated per profile: an on-device vault plus server-side career saves keyed by profile.

### 🛠️ Dev Menu (Owner only)
Visible exclusively to the Owner profile:
- Platform overview (devices / profiles / saves).
- **Profiles manager** — group by device, transfer ownership, delete profiles.
- **Transfermarkt importer** — search a club or paste a transfermarkt.com squad URL → preview players (name, position, age, nation, market value) → "Put in game". Imported squads appear as usable players.

> Note: the importer prefers an anti-bot page reader when available and always falls back to a direct fetch of transfermarkt.com. If Transfermarkt blocks your server, imported rosters simply won't load — the rest of the game is unaffected.

## 🚀 Getting Started

```bash
# 1. Install dependencies (bun or npm)
bun install

# 2. Configure environment
cp .env.example .env

# 3. Create the SQLite database
bun run db:push

# 4. Run the dev server
bun run dev
```

Open **http://localhost:3000**, create the first profile on your device (that's the Owner), and play.

## 🧱 Tech Stack

| Layer      | Tech                                   |
| ---------- | -------------------------------------- |
| Framework  | Next.js 16 (App Router) + TypeScript 5 |
| UI         | Tailwind CSS 4 + shadcn/ui + Lucide    |
| State      | Zustand                                |
| Database   | Prisma ORM + SQLite                    |
| Auth       | Device-based local profiles (no OAuth) |

## 📦 Deploying

This app needs a **Node server** (API routes + SQLite), so static hosts like GitHub Pages won't work. It deploys fine to Render / Railway / Fly.io / a VPS:

```bash
bun run build
bun run start
```

Set `DATABASE_URL` to a persistent file path on the host.

## 📄 License

MIT — do whatever you like, attribution appreciated.

# SpellQuest

[![React](https://img.shields.io/badge/React-19.2-61DAFB?logo=react&logoColor=black&style=flat-square)](#)
[![TypeScript](https://img.shields.io/badge/TypeScript-6.0-3178C6?logo=typescript&logoColor=white&style=flat-square)](#)
[![Vite](https://img.shields.io/badge/Vite-8.1-646CFF?logo=vite&logoColor=white&style=flat-square)](#)
[![PWA](https://img.shields.io/badge/PWA-Ready-58CC02?logo=pwa&logoColor=white&style=flat-square)](#)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?logo=tailwind-css&logoColor=white&style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-gray?style=flat-square)](#)

**SpellQuest** is a modern, gamified educational web application and Progressive Web App (PWA) designed to build high-precision English spelling and touch-typing habits. 

Inspired by modern gamification mechanics, SpellQuest combines Duolingo-style progression (streaks, hearts, XP multipliers, leagues, and daily quests) with real-time auditory dictation and physics-based arcade typing games.

---

## Architecture & Core Mechanics

### 1. Curriculum & Spelling Engine
- **12-Unit Mastery Path:** Structured progression starting from *Daily Essentials* and *Double Trouble* to *French & Global Roots* and the *Grand Arch-Wizard Trial*.
- **Web Speech Dictation:** Uses the native Web Speech API (`SpeechSynthesisUtterance`) to pronounce words aloud during exercises. Features dual dictation speeds (normal speech rate and slow phonetic breakdown).
- **Phonetic & Contextual Assistance:** Every vocabulary item includes IPA phonetic transcriptions, clear definitions, contextual sentences, and mnemonic memory hooks.
- **Adaptive Mistake Locker:** Incorrectly spelled words are automatically quarantined into a dedicated review locker for targeted corrective rehearsal.

### 2. Typing Arena & Dojo
The Typing Arena offers five distinct training modes designed to improve both raw speed and cognitive accuracy:
- **Passage Reading & Typing Assessment:** Multi-line paginated reading tests using classic literature and Aesop's Fables. Tracks live WPM, character-level accuracy, and Adjusted Speed.
- **Keyboard Ninja (Dojo Slice):** A physics-based arcade mode where target words launch across the screen in parabolic trajectories. Correct keystrokes trigger katana slashes and combo multipliers.
- **Type A Balloon (Park Dart Cannon):** Balloons float toward the atmosphere at varying speeds. Type matching words to fire the dart cannon before targets escape.
- **Speed Sprint:** Timed high-velocity sprints with selectable durations (15s, 30s, and 60s).
- **Combo Endurance (Sudden Death):** High-stakes training with no time limit where a single mistyped character ends the run.

### 3. PWA & Mobile Experience
- **Progressive Web App:** Built with `vite-plugin-pwa` and Workbox. Fully installable across iOS, Android, macOS, and Windows with offline caching and standalone display mode.
- **Mobile-First Layout:** Features responsive bottom navigation for mobile viewports, safe-area inset padding for notched displays, and touch-optimized character slots.
- **Offline Connectivity Engine:** Automatically caches local core assets, curriculum data, and audio fallbacks, accompanied by real-time online/offline status banners.

---

## Tech Stack

| Component | Technology |
| :--- | :--- |
| **Frontend Framework** | React 19 (Hooks, Context API, Strict Mode) |
| **Language** | TypeScript 6.0 (Strict type safety across domain models) |
| **Styling & Design System** | Vanilla CSS + Tailwind CSS 3.4 (Custom animations & responsive grids) |
| **PWA & Offline Service** | `vite-plugin-pwa`, Workbox Window, Web App Manifest |
| **Build & Tooling** | Vite 8.1, Oxlint, PostCSS |
| **Audio & Speech** | Native Web Speech API (`speechSynthesis`) |
| **State Persistence** | Namespaced `localStorage` and `sessionStorage` serialization |

---

## Repository Structure

```text
SpellQuest/
├── public/
│   ├── favicon.svg              # Vector app icons
│   ├── manifest.json            # PWA manifest definitions
│   └── sw.js                    # Service worker fallbacks
├── src/
│   ├── App.tsx                  # Core application shell and responsive navigation
│   ├── index.css                # Global design system, safe areas, and keyframes
│   ├── main.tsx                 # Entry point and automatic PWA registration
│   ├── types.ts                 # TypeScript domain models and interface schemas
│   ├── context/
│   │   └── GameContext.tsx      # Global state engine, XP calculation, and audio controller
│   ├── data/
│   │   └── wordData.ts          # Vocabulary repository, hints, and unit configurations
│   └── components/
│       ├── common/              # TopBar, BottomNav, DesktopSidebar, PWA prompts, and offline banners
│       ├── home/                # Winding lesson path dashboard and unit headers
│       ├── practice/            # Active spelling exercise interfaces and character matchers
│       ├── review/              # Mistake locker and corrective practice workflows
│       ├── profile/             # User stats, avatar selection, and voice customization
│       └── typing/              # Typing Arena orchestrator
│           ├── lessons/         # Touch-typing curriculum grid
│           └── games/           # Passage Test, Keyboard Ninja, and Type A Balloon engines
├── index.html                   # Document root and mobile viewport headers
├── package.json                 # Dependencies and build scripts
├── tailwind.config.js           # Design tokens and custom keyframe definitions
└── vite.config.ts               # Vite configuration and PWA Workbox caching rules
```

---

## Getting Started

### Prerequisites
- Node.js (`v18.0.0` or higher recommended)
- npm or pnpm

### Installation & Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Hayagriva0/SpellQuest.git
   cd SpellQuest
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the local development server:**
   ```bash
   npm run dev
   ```
   Open your browser and navigate to `http://localhost:5173`.

### Production Build & PWA Verification

To compile TypeScript and bundle optimized production assets:
```bash
npm run build
```

To preview the production build locally (with service worker activation):
```bash
npm run preview
```

To run high-speed linting checks across all source files:
```bash
npm run lint
```

---

## License

Distributed under the MIT License. See `LICENSE` for more details.

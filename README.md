# HyperFrames Video Project

A clean, agent-ready video composition project powered by [HyperFrames](https://hyperframes.heygen.com).

---

## 💻 Setup on Another PC (Step-by-Step)

If you clone or open this project on another computer and want an AI agent (Antigravity, Claude Code, Cursor, Copilot, etc.) to edit videos, follow these steps:

### 1. Prerequisites
- **Node.js**: Make sure Node.js (v18 or higher) is installed.
- **Git**: Ensure Git is installed to clone the project.

### 2. Clone & Install
Open your terminal in the target directory on the other PC:

```bash
# 1. Clone your repository
git clone <your-repo-url>
cd editing

# 2. Install HyperFrames locally
npm install
```

### 3. Open in your AI Editor / Agent
- Open the `editing` folder in **Google Antigravity**, **VS Code**, **Cursor**, or launch **Claude Code**.
- The project already includes:
  - [`AGENTS.md`](AGENTS.md) & [`CLAUDE.md`](CLAUDE.md) — Pre-configured instructions that agents automatically read.
  - `.agents/` — Built-in HyperFrames skills for editing, timing, animation, and video rendering.

### 4. Start the Studio Preview
```bash
npm run dev
```
Open **[http://localhost:3002](http://localhost:3002)** in your browser to see the live video preview with scrubbing, inspector, and instant reload.

---

## 🤖 How to Edit Videos with an AI Agent

Once set up, you don't need to write code manually. Simply prompt your AI agent with what you want:

### Example Prompts:
- **Talking Head / Recut**:
  > *"Add kinetic captions, keyword highlights, and subtle background music to my video in assets/clips/my-video.mp4"*
- **Product Launch / Promo**:
  > *"Create a 30s 9:16 vertical promotional reel for my product with sleek entrance animations and modern typography."*
- **Motion Graphics**:
  > *"Add a 5s title intro with animated text reveal and sound effects."*
- **Editing & Tweaks**:
  > *"Change the headline color to neon yellow, make it punch in at 2.5s, and adjust the duration to 15s."*

The AI agent will read [`index.html`](index.html), write deterministic GSAP timelines, place media from `assets/`, and run `npm run check` to verify the video.

---

## 🛠️ CLI Commands

| Command | Action |
| :--- | :--- |
| `npm run dev` | Starts local interactive Studio preview on `http://localhost:3002` |
| `npm run check` | Lints and validates composition rules, motion, layout, and contrast |
| `npm run render` | Headless render of the composition into an MP4 video |

---

## 📁 Project Structure

```
editing/
├── index.html       # The main composition (root timeline, HTML + CSS + GSAP)
├── meta.json        # Project ID and title
├── assets/          # Media directory (drop your clips, images, bgm, sfx here)
│   ├── clips/       # Video footage
│   ├── images/      # Photos, logos, overlays
│   ├── audio/       # Voiceovers or replacement audio
│   ├── bgm/         # Background music tracks
│   └── sfx/         # Sound effect library
├── AGENTS.md        # AI Agent instructions & rules
├── .gitignore       # Keeps git clean (ignores node_modules and cache)
└── package.json     # HyperFrames toolchain
```

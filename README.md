# 🟩 MAZE SOLVER

> A retro-terminal, CRT-aesthetic maze solver that visualizes recursive backtracking in real time — with a gravity-flipping direction mechanic.

![Maze Solver Preview](https://img.shields.io/badge/built%20with-HTML%20%2F%20CSS%20%2F%20JS-00e676?style=flat-square&labelColor=0d0d0d)
![No dependencies](https://img.shields.io/badge/dependencies-none-00e676?style=flat-square&labelColor=0d0d0d)
![License](https://img.shields.io/badge/license-MIT-00e676?style=flat-square&labelColor=0d0d0d)

---

## ✨ Features

- **Procedural Maze Generation** — Every maze is unique, built using DFS recursive backtracking (Wilson-style wall carving)
- **Recursive Backtracking Solver** — Watch the algorithm explore, dead-end, and backtrack in real time
- **Gravity Flip Mechanic** — Flip gravity mid-solve to change the direction priority of the algorithm (UP-first vs DOWN-first)
- **Step-by-Step Mode** — Manually advance one step at a time to study the algorithm
- **Live Statistics** — Steps taken, backtracks, final path length, and elapsed time
- **Algorithm Log** — Real-time terminal log of every move and backtrack
- **Variable Speed** — 1–20 steps/second with live adjustment during solve
- **Retro CRT UI** — Pixel fonts, scanline overlay, sharp borders, stepped animations

---

## 🕹️ Controls

| Key | Action |
|-----|--------|
| `S` / `Space` | Start auto-solve |
| `T` / `→` | Step through one move |
| `R` | Reset ball to start |
| `N` | Generate a new maze |
| `G` | Flip gravity direction |
| `P` | Pause / Resume |

---

## 🧠 How It Works

### Maze Generation
Uses **DFS recursive backtracking** (also known as the recursive maze generator):
1. Start with a grid full of walls
2. From the starting cell, carve paths to random unvisited neighbors (2 cells away)
3. Recurse until all cells are visited
4. Result: a perfect maze (exactly one path between any two cells)

### Maze Solving
Also uses **recursive backtracking (DFS)**:
1. From the start cell, try each neighbor in priority order (based on gravity)
2. Mark visited cells in teal
3. If a dead end is reached, backtrack — marking cells with `×`
4. When the end cell is reached, highlight the solution path in green

### Gravity Direction
The gravity direction changes the **neighbor exploration order**:
- **Gravity UP** → tries UP first, then LEFT, RIGHT, DOWN
- **Gravity DOWN** → tries DOWN first, then RIGHT, LEFT, UP

This creates visually distinct solving paths depending on gravity state.

---

## 🎨 UI Stack

| Tool | Purpose |
|------|---------|
| **Press Start 2P** | Pixel retro headers, stats, card titles |
| **Share Tech Mono** | Terminal monospace body text |
| **Vanilla CSS** | CRT scanlines, vignette, pixel borders, stepped animations |
| **Canvas API** | Animated starfield background |
| **Pure JS** | Generator-based solver, maze gen, all logic |

No frameworks. No build tools. One HTML file.

---

## 🚀 Running Locally

Just open `index.html` in any modern browser:

```bash
# Option 1: Direct open
start index.html

# Option 2: Python server (recommended to avoid CORS)
python -m http.server 8765
# Then open http://localhost:8765
```

---

## 📁 Structure

```
mazesolver/
└── index.html    # Entire app — HTML + CSS + JS in one file
```

---

## 📄 License

MIT — do whatever you want with it.

# ScoreKeeper

🎲 A mobile-friendly, single-file scoreboard app for tracking scores during game nights. No install, no server — just open `index.html` in any browser.

**Live demo:** https://death259.github.io/ScoreKeeper/

## Features

### Setup
- Enter a custom game name (e.g. "Trivia Night", "Charades")
- Choose 2–8 teams; defaults to military alphabet names (Alpha, Bravo, etc.)

### Scoreboard
- Each team gets a card with a color-coded accent bar and large score display
- **Add / Subtract** any value from a team's score using the number input
- **Undo** the last score change per team
- **Edit team names** inline by clicking the name
- **Color picker** — click the swatch on any team card to choose from 16 colors
- **Leader banner** — live banner showing who's winning and by how many points, or a tie indicator
- **Score history chips** — last 8 score changes shown as +/- pills on each card
- **Tie detection** — TIE badge on cards and tie-mode banner when multiple teams share the lead

### Timer
- Preset durations: 30s, 1m, 1:30, 2m, 3m
- Custom timer via minute/second inputs
- Progress bar turns yellow at ≤30s and red + pulsing at ≤10s
- Alarm: fullscreen overlay + looping Web Audio beep pattern when time runs out

### Hall of Fame
- Completed games are saved to `localStorage` and persist across sessions
- All-time win counts displayed as a bar chart
- Full standings for every recorded game
- Delete individual records

### Game Controls
- **End Game** — saves winner/standings to Hall of Fame, fires confetti, resets scores
- **Reset** — wipes current scores (confirmation required)
- **New Game** — returns to setup; Hall of Fame is preserved
- **Share** — generates a text summary of current scores + recent Hall of Fame entries; supports clipboard copy and native OS share sheet
- **Fullscreen** — toggles browser fullscreen mode

### Persistence
All state is saved to `localStorage` under the key `scorekeeper`. Reloading the page restores the exact game in progress.

### Responsive Layout
- Single column on mobile, 2-column at 600px+, 3-column at 900px+
- Compact landscape layout for phones held sideways

## Usage

Visit the **[live demo](https://death259.github.io/ScoreKeeper/)** or open `index.html` directly in a browser — no build step or dependencies required. Works offline after the initial Google Fonts load.

## Tech Stack

- Vanilla HTML/CSS/JS — zero dependencies, zero build tooling
- Web Audio API for the countdown alarm
- Canvas API for confetti
- `localStorage` for persistence
- Google Fonts: Bebas Neue (display) + DM Sans (body)

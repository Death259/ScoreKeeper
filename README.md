# ScoreKeeper

🎲 A mobile-friendly, single-file scoreboard app for tracking scores during game nights. No install, no server — just open `index.html` in any browser.

**Live demo:** https://death259.github.io/ScoreKeeper/

## Features

### First Launch
- A one-time welcome splash highlights the app's main features. Dismiss it with "Let's Play!" and it won't show again on that device.

### Setup
- Enter a custom game name (e.g. "Trivia Night", "Charades")
- Choose 2–8 teams; defaults to military alphabet names (Alpha, Bravo, etc.)
- **Scoring mode** — pick **Highest wins** (default) or **Lowest wins** for golf-style games; the winner logic, leader banner, and standings all respect the mode

### Scoreboard
- Each team gets a card with a color-coded accent bar and large score display
- **Add / Subtract** any value from a team's score using the number input
- **Undo** the last score change per team
- **Edit team names** inline by clicking the name
- **Color picker** — click the swatch on any team card to choose from 16 colors
- **Leader banner** — live banner showing who's winning and by how many points, or a tie indicator
- **Score history chips** — last 8 score changes shown as +/- pills on each card
- **Tie detection** — TIE badge on cards and tie-mode banner when multiple teams share the lead
- **Rounds** — the round counter advances only when you tap **Next Round**, so several teams can score within the same round. An **Undo** appears on the toast in case you tap it by accident.

### Timer
- Preset durations: 30s, 1m, 1:30, 2m, 3m
- Custom timer via minute/second inputs
- Progress bar turns yellow at ≤30s and red + pulsing at ≤10s
- Alarm: fullscreen overlay + looping Web Audio beep pattern when time runs out

### Voice Commands
- Tap the 🎤 button in the game header to control the timer hands-free (handy when your hands are busy running the game)
- Supported phrases: **"start timer"**, **"stop timer"** / **"pause timer"**, **"reset timer"**, **"reset scores"**, **"new game"**
- The button pulses red while listening and keeps listening until you tap it off
- Powered by the browser's Web Speech API (works best in Chrome/Edge); the button hides itself automatically on browsers without support

### Hall of Fame
- Completed games are saved to `localStorage` and persist across sessions
- All-time win counts displayed as a bar chart
- Full standings for every recorded game
- Delete individual records

### Game Controls
- **Next Round** — advances the round counter (with an Undo on the toast)
- **End Game** — saves winner/standings to Hall of Fame, fires confetti, resets scores, and stops/resets the timer. The same teams stay on the board for a quick rematch. Disabled until at least one point has been scored, so a finished game can't be recorded twice.
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

Visit the **[live demo](https://death259.github.io/ScoreKeeper/)** or open `index.html` directly in a browser — no build step or dependencies required. Everything but the Google Fonts is bundled in the single file, so it works offline (fonts fall back to system defaults if unavailable).

## Tech Stack

- Vanilla HTML/CSS/JS in a single file — no build tooling
- [annyang](https://www.talater.com/annyang/) (MIT, ~4.5KB minified, vendored inline in `index.html`) wrapping the Web Speech API for voice commands
- Web Audio API for the countdown alarm
- Canvas API for confetti
- `localStorage` for persistence
- Google Fonts: Bebas Neue (display) + DM Sans (body)

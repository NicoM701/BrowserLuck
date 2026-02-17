# BrowserLuck

BrowserLuck is a small collection of standalone luck-based browser games.
Every mode is a single HTML file that runs instantly in any modern browser.

## Quick Start

1. Download any `.html` file from this repo.
2. Open it directly in your browser.
3. Start using it immediately.

## Available Modes

### German files

- `gluecksrad.html` - Lucky wheel
- `gluecksrad-weighted.html` - Weighted lucky wheel
- `kopf-oder-zahl.html` - Coin flip

### English files

- `lucky-wheel.html` - Lucky wheel
- `lucky-wheel-weighted.html` - Weighted lucky wheel
- `coin-flip.html` - Coin flip

## Version Differences

- Normal Lucky Wheel (`gluecksrad.html` / `lucky-wheel.html`):
  Standard random selection. Every entry has the same chance.

- Weighted Lucky Wheel (`gluecksrad-weighted.html` / `lucky-wheel-weighted.html`):
  You can define percentages per entry (for example `Item 25%`).
  If the total is below 100%, the remaining probability becomes an explicit empty segment (`[Leer]` / `[Empty]`).

- Coin Flip (`kopf-oder-zahl.html` / `coin-flip.html`):
  Two-sided 50/50 decision tool with customizable labels.

## Screenshots

### German files

`gluecksrad.html`

![gluecksrad](screenshots/gluecksrad.png)

`gluecksrad-weighted.html`

![gluecksrad-weighted](screenshots/gluecksrad-weighted.png)

`kopf-oder-zahl.html`

![kopf-oder-zahl](screenshots/kopf_oder_zahl.png)

### English files

`lucky-wheel.html`

![lucky-wheel](screenshots/lucky-wheel.png)

`lucky-wheel-weighted.html`

![lucky-wheel-weighted](screenshots/lucky-wheel-weighted.png)

`coin-flip.html`

![coin-flip](screenshots/coin-flip.png)

## Features

- Fully offline
- No install, no dependencies
- Keyboard shortcuts
- History tracking
- Save/load text input on wheel modes

## Keyboard Shortcuts

- `Space` - Spin / flip
- `Ctrl+S` - Save entries (wheel modes)
- `Ctrl+O` - Open entries file (wheel modes)

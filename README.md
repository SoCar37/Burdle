# Burdle
The Word Game of Burdle
# Burdle v1.3
### © 2026 Burle Warren — All rights reserved.

## Overview
Burdle is a five-letter word guessing game built with pure HTML and JavaScript. No frameworks, no dependencies beyond Google Fonts. Dark neon aesthetic, edgy scoring messages, real dictionary validation, and full mobile/cross-platform support as of v1.3.

## How to Play
1. Open `burdle_v1.3.html` in any modern browser — desktop or mobile.
2. Click **Start Your Adventure** on the intro screen.
3. You have **6 tries** to guess the hidden five-letter word.
4. Type using your physical keyboard (desktop) or the on-screen keyboard (all devices).
5. Press **Enter** to submit. Press **⌫** or Backspace to delete.
6. Only real English words are accepted.

## Tile Color Key
| Color | Meaning |
|-------|---------|
| 🟩 **Green** | Correct letter, correct position |
| 🟧 **Orange** | Correct letter, wrong position |
| ⬛ **Dark** | Letter not in the word |

## Scoring Messages
| Guess # | Message |
|---------|---------|
| 1 | Outstanding |
| 2 | Superb |
| 3 | Great |
| 4 | Mediocre |
| 5 | Poor |
| 6 | Very Bad |
| Fail | You're A Loser! |

## Features
- Intro screen with flashing neon title and Start button
- 6-row guess grid with animated tile flips
- On-screen keyboard with live letter state tracking
- Physical keyboard support (desktop)
- Dictionary validation via Free Dictionary API
- Hint button — subtle verbal clue on demand
- Distinct red (error) and blue (hint) toast messages
- End screen with result, the answer word, and Play Again
- ~1,000 curated five-letter word pool
- Copyright notice in HTML comment, intro screen, and game footer

## Version History
| Version | Date | Notes |
|---------|------|-------|
| 1.0 | 2026-02-21 | Initial release |
| 1.1 | 2026-02-21 | Fixed duplicate end-screen label; fixed row-skipping bug |
| 1.2 | 2026-02-21 | Added dictionary validation; separated hint/error toasts |
| 1.3 | 2026-02-21 | Mobile/cross-platform overhaul; copyright added |

## Changes in v1.3

**Copyright** — `© 2026 Burle Warren` added in three places: the HTML comment header at the top of the file, the intro screen version line, and a footer credit on the game screen.

**Mobile keyboard suppression** — on-screen keys now use `pointerdown` with `e.preventDefault()` instead of `click`. This prevents the native mobile keyboard from popping up and fighting with Burdle's built-in keyboard. Physical keyboard input still works normally on desktop.

**Fully fluid layout** — all sizing now uses CSS `clamp()` and `min()` so the grid, tiles, keyboard keys, fonts, and spacing scale smoothly from a 320px iPhone SE up to a wide desktop monitor. Nothing clips, nothing scrolls, everything fits on one screen.

**Dynamic viewport height** — game screen uses `max-height: 100dvh` (`dvh` = dynamic viewport height) which correctly accounts for the browser chrome bar on iOS Safari and Android Chrome, preventing the keyboard from being pushed off-screen.

**Touch target sizing** — all interactive elements (keys, buttons) now meet the 44px minimum tap target recommended by Apple and Google accessibility guidelines.

**Double-tap zoom prevention** — `touch-action: manipulation` applied globally and on individual keys, eliminating accidental zoom on rapid taps.

**iOS long-press suppression** — `-webkit-touch-callout: none` and `-webkit-user-select: none` prevent the iOS context menu from appearing when a player holds down a key.

**Text selection prevention** — tile and key text cannot be accidentally selected/highlighted during gameplay on any platform.

**Safari backdrop-filter fix** — end modal now includes `-webkit-backdrop-filter` alongside the standard `backdrop-filter` for full blur support on iOS Safari.

**Active press feedback** — keys visually respond to touch/press with a subtle scale-down effect, giving tactile feedback on mobile.

**Overscroll prevention** — `overscroll-behavior: none` stops iOS elastic bounce scrolling from revealing the background behind the game.

## Browser Compatibility
Tested compatible with: Chrome (desktop + Android), Safari (desktop + iOS), Firefox (desktop + Android), Edge (desktop).

## Files
```
burdle_v1.3/
├── burdle_v1.3.html     ← The entire game (open this in a browser)
└── README_v1.3.md       ← This file
```

## Hosting on GitHub Pages
This is a single self-contained HTML file. To host on GitHub Pages:
1. Push `burdle_v1.3.html` to a GitHub repository
2. Go to **Settings → Pages** in your repo
3. Set source to your main branch, root folder
4. GitHub will provide a public URL — the dictionary API will work correctly from that domain as it supports open CORS

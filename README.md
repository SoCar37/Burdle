# Burdle
The Word Game of Burdle
# Burdle v1.4
### © 2026 Burle Warren — All rights reserved.

## Overview
Burdle is a five-letter word guessing game built with pure HTML and JavaScript. No frameworks, no dependencies beyond Google Fonts. Dark neon aesthetic, persistent stats tracking, no-repeat word shuffling, and full mobile/cross-platform support.

## How to Play
1. Open `burdle_v1.4.html` in any modern browser — desktop or mobile.
2. Click **Start Your Adventure** on the intro screen.
3. You have **6 tries** to guess the hidden five-letter word.
4. Type using your physical keyboard (desktop) or the on-screen keyboard (all devices).
5. Press **Enter** to submit. Press **⌫** or Backspace to delete.
6. Only real English words are accepted as guesses.

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
| Fail | Epic Fail |

## Features
- Intro screen with flashing neon title and Start button
- 6-row guess grid with animated tile flips
- On-screen keyboard with live letter state tracking
- Physical keyboard support (desktop)
- Dictionary validation via Free Dictionary API
- Hint button — subtle verbal clue on demand
- Distinct red (error) and blue (hint) toast messages
- **Shuffle-the-deck word selection** — no repeats within a full cycle of all words
- **Stats tracking** — persistent records saved across sessions via localStorage
- **Stats modal** — opened via the 📊 Stats button; shows Played, Win %, Current Streak, Best Streak, and a Guess Distribution bar chart
- End screen showing result message, "The Word Was" label, the answer in green, and Play Again
- Copyright notice in HTML comment, intro screen, and game footer

## Version History
| Version | Date | Notes |
|---------|------|-------|
| 1.0 | 2026-02-21 | Initial release |
| 1.1 | 2026-02-21 | Fixed duplicate end-screen label; fixed row-skipping bug |
| 1.2 | 2026-02-21 | Added dictionary validation; separated hint/error toasts |
| 1.3 | 2026-02-21 | Mobile/cross-platform overhaul; copyright added |
| 1.4 | 2026-02-22 | Shuffle-the-deck; stats/records; word reveal label; Epic Fail |

## Changes in v1.4

**Shuffle-the-deck word selection** — the full word list is shuffled using a Fisher-Yates algorithm at the start of each cycle and stored in localStorage. Words are drawn from the front of the shuffled deck one at a time. No word repeats until every word in the pool has been used. When the deck runs out it automatically reshuffles for the next cycle. The deck persists across browser sessions so closing and reopening the browser does not reset your position in the cycle.

**Stats and record keeping** — results are saved to localStorage after every game. The following are tracked: total games played, total wins, win percentage, current win streak, best win streak ever, and a guess distribution count for each guess number (1–6). Stats survive closing tabs, closing the browser, and restarting the computer — they only reset if browser storage is cleared. A 📊 Stats button in the game header opens the stats modal at any time.

**"The Word Was" label** — the end-of-game modal now shows "THE WORD WAS" as a small label above the green answer word, making it clear what the label refers to. Previously the label was missing entirely.

**Fail message changed** — the game-over message when all 6 guesses are used without finding the word is now **"Epic Fail"** (changed from "You're A Loser!" in v1.3).

## Stats Persistence
Stats are stored in the browser's localStorage under the key `burdle_stats`. They persist as long as the browser's storage is not cleared. They are device- and browser-specific — stats on your phone and laptop are tracked separately. There is no cross-device sync without a backend server.

## Files
```
burdle_v1.4/
├── burdle_v1.4.html     ← The entire game (open this in a browser)
└── README_v1.4.md       ← This file
```

## Hosting on GitHub Pages
Push `burdle_v1.4.html` to your GitHub repository, enable Pages under Settings → Pages, and set the source to your main branch. The dictionary API, localStorage stats, and all features work correctly when hosted on GitHub Pages.

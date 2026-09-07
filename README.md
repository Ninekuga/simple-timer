# Pikmin Timer

A web-based countdown timer application with support for multiple timers and Pikmin mode.

## Features

- **Multiple Timers**: Create and manage multiple countdown timers simultaneously
- **Pikmin Mode**: Add extra time to each timer independently (default: 4 minutes 0 seconds)
- **Global Pikmin Settings**: Adjust Pikmin extra time that applies to all timers
- **Audio Alerts**: Audible beep notification (10 beeps, 1-second intervals) when timer completes
- **Completion Time Display**: Shows the exact time when each timer will complete (user's system timezone, 24-hour format)
- **Timer State Tracking**: Visual indicators for running, paused, and completed timers
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Pause & Resume**: Pause timers and resume with recalculated completion time
- **Sort by Time**: Reorder all timer cards — running timers first, then paused, then finished, then idle; each group sorted by remaining time (ascending)
- **Sort by Name**: Reorder all timer cards alphabetically by title, with locale-aware collation (Traditional/Simplified Chinese, Japanese, Korean, English, with natural numeric ordering)
- **Persistent State**: Timer titles are saved to `localStorage` and restored automatically on page reload

## How to Use

1. Open `index.html` in a web browser
2. Click **"+ 新增計時器"** (Add Timer) to create a new timer
3. Set the desired time (hours, minutes, seconds) for each timer
4. Toggle **Pikmin Mode** on/off to add or remove extra time
5. Click **開始** (Start) to begin the countdown
6. Click **暫停** (Pause) to pause, or click again to resume
7. Click **重置** (Reset) to reset the timer
8. Click **時間排序** (Sort by Time) to reorder cards by running state and remaining time
9. Click **字序排序** (Sort by Name) to reorder cards alphabetically by title

### Global Pikmin Settings

Adjust the extra time in the global Pikmin settings at the top:
- Modify hours, minutes, and seconds
- Changes apply to all timers that have Pikmin Mode enabled

### Timer Features

- **Running**: Green border with real-time countdown display
- **Paused**: Orange border, timer frozen at current value
- **Completed**: Red border with "時間到！" (Time's Up!) message
- **Completion Time**: Right-aligned display shows when the timer will finish
- **Stop Sound**: Click "關閉提示音" (Stop Sound) to silence the audio alert

### Sorting

- **時間排序 (Sort by Time)**: Groups cards by state in this order — running, paused, finished, idle — then sorts each group by remaining time, ascending
- **字序排序 (Sort by Name)**: Sorts all cards by title using `Intl.Collator` with locales `zh-Hant`, `zh`, `ja`, `ko`, `en` and numeric collation, so mixed-language titles and embedded numbers (e.g. "Timer 2" vs "Timer 10") sort naturally
- Sorting is a one-time reorder triggered by the button click; it does not continuously re-sort as timers run

## Technical Details

- **No Dependencies**: Pure HTML, CSS, and JavaScript
- **Web Audio API**: Uses Web Audio API for timer completion alerts
- **Timezone**: Displays completion time in user's system timezone
- **Precision**: Uses `Date.now()` for accurate time calculations (not prone to drift)
- **Persistence**: Timer titles (and count) are stored under the `timerCardsState` key in `localStorage`

## Browser Compatibility

- Requires Web Audio API support
- CSS Grid and Flexbox support
- Tested on modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile-optimized with touch-friendly controls

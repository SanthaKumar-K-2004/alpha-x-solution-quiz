# Implementation Plan: Fix Header, Theme Toggle, Start Button & Leaderboard

## Overview
The Alpha x Solution Quiz UI needs several enhancements:
1. Ensure the header stays sticky and slides out/in smoothly on scroll, especially on mobile.
2. Expose all header icon buttons (mock test, sound, etc.) and make them keyboard‑focusable.
3. Add a reliable dark/light theme toggle that persists the user’s choice.
4. Wire the **Start Assessment** button to transition to the exam view with validation.
5. Introduce a leaderboard component that shows the top scores.

## User Review Required
> [!IMPORTANT]
> - **Leaderboard storage**: Should scores be stored locally (`localStorage`) or in a lightweight backend (e.g., Firebase Realtime DB) for cross‑device persistence?
> - **Theme persistence**: Prefer storing the theme choice in `localStorage` or rely solely on the system `prefers-color-scheme` media query?
> - **Leaderboard UI tweaks**: Any specific visual preferences (avatars, gradient backgrounds, etc.)?

## Proposed Changes
---
### 1. Header Refactor (CSS & JS)
- **CSS**: Update `.header-container` with `flex-wrap: nowrap; min-width: 0;` and media queries to reduce paddings on small screens.
- **Icon Visibility**: Ensure `.icon‑btn` has `flex-shrink: 0;` and is not clipped by overflow.
- **Sticky Logic**: Verify `setupScrollHeader()` toggles `header-hidden` / `header-elevated` correctly; add a `requestAnimationFrame` guard for mobile browsers.

### 2. Dark/Light Mode Toggle
- **HTML**: Insert `<button id="theme-toggle" class="icon-btn" aria-label="Toggle theme">🌙</button>` inside `.header-actions`.
- **JS**: Implement `toggleTheme()` that flips `document.documentElement.dataset.theme` between `light` and `dark`, persisting the value in `localStorage`.
- **CSS**: Ensure all color variables are defined for both themes (already present) and add a smooth `background-color` / `color` transition.

### 3. Start Assessment Button
- **HTML**: Ensure the button has `id="start-assessment"` and `type="button"`.
- **JS**: Add an event listener that validates the name/section fields, saves the selected mode in `window.quizState`, and calls `showView('exam')`.
- **Error Handling**: Show a toast (or alert) if required fields are missing.

### 4. Leaderboard Component
- **UI**: Create a new hidden view `#leaderboard-view` with a card list showing rank, name, score, and mode.
- **Data Storage**: Use `localStorage` to store an array of score objects. On exam completion, push the result, sort descending, and keep the top 10.
- **Integration**: Add a leaderboard icon button (`<button id="leaderboard-btn" class="icon-btn" aria-label="Leaderboard">🏆</button>`) to the header that opens the leaderboard modal.
- **Styling**: Reuse existing `.lobby-card-box` styles with a distinct accent color (e.g., `--apple-amber`).

### 5. Deployment
- Commit all changes with a descriptive message and push to `main`.
- Verify GitHub Pages serves the updated site (either `gh-pages` branch or `main` with `/docs`).
- Run a quick `curl -I https://santhakumar-k-2004.github.io/alpha-x-solution-quiz/` to confirm a `200 OK` response.

---
## Verification Plan
- **Manual**: Open the app on a mobile emulator; scroll to ensure the header hides/shows smoothly.
- **Theme**: Toggle dark/light mode and verify color transitions and persistence across reloads.
- **Start Flow**: Fill the lobby form, click **Start Assessment**, and confirm the exam view appears.
- **Leaderboard**: Complete a mock exam, submit, and check the leaderboard updates correctly.
- **Deployment**: Access the live URL and verify the UI changes are reflected.

*After your approval, I will proceed with the implementation.*

## Overview
Transform the **Alpha x Solution Quiz** into a complete enterprise-grade assessment platform featuring:
1. **Pre-Exam Setup Lobby (Entry Screen)**: Candidate name input (auto-remembered for returning users), test format selector (Section-wise, Full Practice, or 120-min Mock Exam).
2. **Section-Wise & Lifetime High Score Analytics**: Detailed breakdown of score per syllabus section, highest past score tracking, and performance grade.
3. **100% Pure HTML/CSS/JS Guarantee**: Remove all `.py` files from the repository to make it strictly static.
4. **Header & Section Bar Enhancements**: Smooth sticky header with responsive stage dark/light toggle and flawless section click navigation.
5. **Modernized Premium Logo**: Elevated executive vector emblem.

---

## User Review Required

> [!IMPORTANT]
> The Pre-Exam Lobby will welcome users first, allowing them to enter their name and choose between:
> - **Full Practice Mode** (All 115 questions, instant feedback & textbook citations)
> - **Section-wise Practice** (Pick any of the 6 historical segments)
> - **Timed Mock Exam** (120-minute TNPSC simulation with locked answers and OMR palette)
>
> Candidate name and previous test scores will be saved in `localStorage` so returning users are greeted automatically with their previous high score.

---

## Proposed Changes

### Component 1: Repository Architecture Cleanup
- Remove `create_questions_dataset.py` from repository so the project is strictly **100% HTML, CSS, and Vanilla JavaScript**.
- Ensure `index.html` and `quiz_data.js` contain everything needed to run in any browser offline or on GitHub Pages.

---

### Component 2: Pre-Exam Setup Lobby (`#lobby-screen`)
- **Location**: In [index.html](file:///home/santhakumar/Desktop/ESSC%20QUIZ/index.html)
- **Features**:
  - Clean Apple-style frosted modal / lobby hero card.
  - **Candidate Name Input**: Auto-filled from `localStorage.getItem('alpha_candidate_name')`.
  - **Mode Selection Cards**:
    1. 🎯 **Full Practice Mode** (115 வினாக்கள் - உடனடி விடை & மேற்கோள்)
    2. 🏛️ **Section-Wise Practice** (தேர்ந்தெடுத்த அலகு வினாக்கள்)
    3. ⏱️ **TNPSC Mock Exam** (120 நிமிடங்கள், முழுமையான மாதிரித் தேர்வு)
  - **Topic Selector** (enabled when Section-wise is chosen).
  - **Highest Score Display**: Shows candidate's all-time best score and accuracy if previously attempted.
  - **Dark / Light Toggle & Logo**: Available right on the lobby screen and preserved inside the exam.
  - **Start Button**: "தேர்வைத் தொடங்குக / Start Assessment" with smooth fade transition to question viewport.

---

### Component 3: Section Navigation & Sticky Header Polish
- Ensure all 6 section pills are 100% responsive, touch-friendly, and properly switch questions with real-time counter updates.
- Refined header with new executive monogram logo, smooth sticky blur, and stage mode switchers.

---

### Component 4: Comprehensive Section-Wise Scorecard Modal
- Displays:
  - **Candidate Name** and Date.
  - **Overall Score** (Total correct, accuracy %, time taken).
  - **All-Time High Score Record** (stored in `localStorage`).
  - **Section-by-Section Progress Table**:
    1. சங்க காலம் & தொல்லியல் சான்றுகள்: X / 25
    2. பாளையக்காரர்கள் & வேலூர் புரட்சி: Y / 20
    3. விடுதலைப் போராட்டத்தில் தமிழகத்தின் பங்கு: Z / 20
    4. நீதிக்கட்சி & சுயமரியாதை இயக்கம்: A / 20
    5. தமிழக அரசியல் தலைவர்கள் & நலத்திட்டங்கள்: B / 15
    6. திருக்குறள் & அற இலக்கியங்கள்: C / 15
  - **Review Mistakes Button**: Direct filter to only incorrect questions for targeted revision.
  - **Re-attempt Button**: Return to lobby or retry exam.

---

## Verification Plan

### Automated / Subagent Tests
- Load `http://127.0.0.1:8089/index.html` in browser subagent on mobile viewport (`400x856`).
- Test Candidate Name entry and persistence in `localStorage`.
- Test selecting Section-Wise mode and verify filtering.
- Test Mock Exam countdown timer and submit.
- Verify Section-Wise scorecard table shows individual breakdown for all 6 units.
- Verify repository contains zero `.py` files and commits are cleanly pushed to GitHub.

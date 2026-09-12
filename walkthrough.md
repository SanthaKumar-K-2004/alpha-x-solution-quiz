# Alpha x Solution Quiz — Apple-Level Mobile UI/UX Release

## Overview
**Alpha x Solution Quiz** is a production-ready, mobile-first assessment web application for TNPSC & Government Examinations. Based strictly on the official 96-page study PDF (`UNIT - 6 [ TN HISTORY ]`), it includes **115 syllabus-aligned questions** across all 6 core historical segments.

- **Live URL**: [https://santhakumar-k-2004.github.io/alpha-x-solution-quiz/](https://santhakumar-k-2004.github.io/alpha-x-solution-quiz/)
- **GitHub Repository**: [https://github.com/SanthaKumar-K-2004/alpha-x-solution-quiz](https://github.com/SanthaKumar-K-2004/alpha-x-solution-quiz)
- **Author**: Santhakumar K • Alpha x Solution

---

## 🍎 Apple-Company-Like Design System & Mobile UX

1. **Content-First Mobile Focus**:
   - **Compact Header (52px)**: Header height strictly limited to 52px on mobile with clean typography, iOS segmented mode switcher (`பயிற்சி` / `தேர்வு`), sound toggle, and theme toggle.
   - **Hairline Progress Bar (2.5px)**: Unobtrusive Apple-style linear progress indicator tracking question completion without vertical screen waste.
   - **No Clutter Above the Fold**: Reduced pre-question height from 480px down to 88px, making the Question and all 4 Options (A, B, C, D) 100% visible on any mobile viewport without scrolling!

2. **Apple Typographic & Option Pill Cards**:
   - **Options A, B, C, D**: Styled as Apple grouped list cells with generous 52px+ touch targets, rounded 14px corners, and crisp bold letter badges (**A, B, C, D**).
   - **Full Visibility**: Question text and statement items are styled with comfortable line height (1.65), zero truncation, and high contrast.

3. **Refined Dark & Light Themes**:
   - **Dark Mode (Default)**: Deep OLED black (`#000000`) background, elevated cards (`#14161b`), subtle borders (`rgba(255,255,255,0.08)`), and crisp white text.
   - **Light Mode**: Apple clean white (`#f5f5f7`), pure white cards (`#ffffff`), and subtle contrast borders (`rgba(0,0,0,0.08)`).
   - **Theme Switcher**: Smooth toggle with persistent state saved to `localStorage` and dynamic `theme-color` meta tag for mobile browsers.

4. **Pedagogical Feedback & Verbatim Citations**:
   - Practice mode provides instant answer validation:
     - Selecting the correct answer highlights in emerald green (`#30d158`) with a checkmark `✓`.
     - Selecting a wrong answer triggers a subtle haptic shake in soft red (`#ff453a`) and immediately illuminates the correct answer in emerald green.
     - Unfolds the textbook citation card citing the exact verbatim quote and page number (e.g. *பக்கம் 2-3*).

5. **iOS-Style Mobile Bottom Bar & Palette Drawer**:
   - Native bottom navigation bar with `முந்தையது` (Prev), `வினாத்தட்டு` (115 Qs Palette), `மதிப்பெண்` (Scorecard), and `அடுத்தது` (Next).
   - Half-sheet slide-up drawer for direct jump navigation to any of the 115 questions.
   - Touch horizontal swipe gestures for quick question browsing.

6. **Small, Discreet Footer**:
   - Single-line minimal footer:
     `Alpha x Solution Quiz • Crafted by Santhakumar K • UNIT - 6 Study Reference`

---

## 💡 How GitHub Pages Hosts This (Python vs Static Files)
- **Local Role of Python**: Python was used strictly locally as a data compiler/parser script to extract the TrueType CMap from the 96-page PDF and structure the verified questions into `quiz_data.js`.
- **Hosting on GitHub Pages**: GitHub Pages is a static CDN host. It directly serves `index.html`, `quiz_data.js`, and vanilla CSS. There is **no Python backend required on GitHub**; the quiz engine runs 100% in the user's browser via high-speed JavaScript.
- **Benefits**: 100% free lifetime hosting, zero server costs, automated CI/CD upon `git push`, global CDN edge distribution, and automatic HTTPS security.

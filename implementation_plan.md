# TNPSC Unit 6: தமிழ்நாடு வரலாறு & பண்பாடு - Comprehensive Interactive Quiz Application

## Overview
This implementation plan outlines the creation of a full-featured, interactive, state-of-the-art TNPSC Quiz Application based strictly on the 96-page study material `UNIT - 6 [ TN HISTORY ]_260912_124734.pdf`. The application will contain **110+ high-standard questions** (moderate to tricky-hard difficulty) organized into 6 syllabus segments, featuring authentic TNPSC question formats (Statements, Assertion-Reason, Match the Following, and Direct MCQs) in pure Tamil, with instant answer reveal and exact sentence-level explanations from the PDF.

---

## User Review Required

> [!IMPORTANT]
> **Key Decisions Aligned from the Discussion Phase:**
> 1. **Question Volume & Scope**: 110+ questions (exceeding the 100+ minimum requirement) covering all key topics across all 96 pages.
> 2. **Difficulty Level**: Moderate to Tricky-Hard, adhering to TNPSC Group 1/2/4 standards with statement analyses (கூற்றுகளை ஆராய்க), Assertion & Reason (கூற்று-காரணம்), Match the following (பொருத்துக), and tricky distractors.
> 3. **Feedback Behavior**: If the user clicks a wrong answer, the application immediately shakes/highlights the wrong selection in crimson, highlights the correct answer in emerald green, and displays an explanation card quoting the exact sentence from the PDF.
> 4. **Dual Modes**: 
>    - **Interactive Practice Mode**: Instant answer check + explanation reveal.
>    - **Timed Exam Simulation Mode**: 120-minute countdown timer, OMR-style navigation, and post-submission detailed analytical report.
> 5. **Segment Organization**: 6 thematic segments with tab filters + "Review Incorrect Only" filter.
> 6. **Self-Contained Architecture**: Built as a single, portable, highly-optimized `index.html` file (HTML5 + modern Vanilla CSS + ES6 JavaScript) that opens directly in any browser with zero installation.

---

## Architecture & Structure of the Quiz Application

### 1. The 6 Syllabus Segments & Question Distribution (110+ Questions)
- **Segment 1: தமிழ் சமூக வரலாறு & சங்க காலம், தொல்லியல் சான்றுகள் (25 Questions)**
  - தொல்காப்பியம், கீழடி, கொடுமணல், அரிக்கமேடு, பட்டணம், அழகன்குளம், கொற்கை அகழாய்வுகள்.
  - தமிழ்-பிராமி, வட்டெழுத்து, புகழூர், மாங்குளம், ஜம்பை, புலிமான்கோம்பை நடுகற்கள் & கல்வெட்டுகள்.
  - மூவேந்தர்கள் (சேர, சோழ, பாண்டியர்), வேளிர் & குறுநில மன்னர்கள் (ஆய், வேளிர், கிழார்).
  - சங்ககால ஆட்சிமுறை, திணைக்கோட்பாடு, சமூகப் பொருளாதார வாழ்க்கை, வெளிநாட்டு வணிகம் (பிளினி, பெரிப்ளஸ், தாலமி, உரோமானிய நாணயங்கள்).
- **Segment 2: பாளையக்காரர்கள் புரட்சி & 1806 வேலூர் புரட்சி (20 Questions)**
  - பாளையக்காரர் முறை தோற்றம் (விஸ்வநாத நாயக்கர், அரியநாதர்).
  - பூலித்தேவர், நெற்கட்டும்செவல், யூசுப்கான், களக்காடு போர்.
  - வேலு நாச்சியார், குயிலி, கோபால நாயக்கர், ஹைதர் அலி உதவி, சிவகங்கை மீட்பு.
  - வீரபாண்டிய கட்டபொம்மன், ஜாக்சன் சந்திப்பு, பாஞ்சாலங்குறிச்சி முற்றுகை, கயத்தாறு.
  - மருது சகோதரர்கள், 1801 திருச்சிராப்பள்ளி பிரகடனம், தீரன் சின்னமலை, ஓடாநிலை போர்.
  - 1806 வேலூர் புரட்சி: காரணங்கள் (அக்னியூ தலைப்பாகை), புரட்சியாளர்கள், கில்லெஸ்பியின் அடக்குமுறை, விளைவுகள்.
- **Segment 3: இந்திய விடுதலைப் போராட்டத்தில் தமிழகத்தின் பங்கு (20 Questions)**
  - சென்னை மகாஜன சபை, சுதேசி இயக்கம், வ.உ.சிதம்பரனார் (சுதேசி நீராவி கப்பல் கம்பெனி).
  - மகாகவி பாரதியார், சுப்பிரமணிய சிவா, வாஞ்சிநாதன் (ஆஷ் கொலை).
  - ரவுலட் சத்யாகிரகம், கிலாபத் இயக்கம், ஒத்துழையாமை இயக்கம், சைமன் குழு எதிர்ப்பு.
  - வேதாரண்யம் உப்புச் சத்தியாகிரகம் (ராஜாஜி), திருப்பூர் குமரன் (கொடிகாத்த குமரன்).
  - வெள்ளையனே வெளியேறு இயக்கம் & தமிழகத் தலைவர்கள் (காமராசர், தீரர் சத்தியமூர்த்தி, ருக்மணி லட்சுமிபதி).
- **Segment 4: சமூக சீர்திருத்த இயக்கங்கள், நீதிக்கட்சி & சுயமரியாதை இயக்கம் (20 Questions)**
  - பிராமணரல்லாதார் இயக்கம், தென்னிந்திய நல உரிமைச் சங்கம் (நீதிக்கட்சி), டாக்டர் நடேசனார், தியாகராய செட்டியார், டி.எம்.நாயர்.
  - நீதிக்கட்சியின் சாதனைகள் (1921 பெண்களுக்கான வாக்குரிமை, வகுப்புவாரி பிரதிநிதித்துவம், தியாகராயர் மதிய உணவுத் திட்டம், இந்து சமய அறநிலையச் சட்டம்).
  - தந்தை பெரியார்: வைக்கம் போராட்டம், சேரன்மாதேவி குருகுல எதிர்ப்பு, சுயமரியாதை இயக்கம் (1925), செங்கல்பட்டு மாநாடு (1929).
  - தேவதாசி முறை ஒழிப்பு (டாக்டர் முத்துலட்சுமி ரெட்டி, மூவலூர் ராமாமிர்தம் அம்மையார்).
  - புரட்சிக்கவிஞர் பாரதிதாசன், ஜீவானந்தம், திராவிடர் கழகம் தோற்றம் (1944 சேலம் மாநாடு).
- **Segment 5: தற்கால தமிழக அரசியல், தலைவர்கள் & சமூக நலத்திட்டங்கள் (15 Questions)**
  - ராஜாஜி ஆட்சி & குலக்கல்வித் திட்ட சர்ச்சை.
  - காமராசர் பொற்கால ஆட்சி: இலவச மதிய உணவுத் திட்டம், தொடக்கப் பள்ளிகள் திறப்பு, அணைக்கட்டுகள், தொழில் வளர்ச்சி.
  - பேரறிஞர் அண்ணா: 1967 தேர்தல் வெற்றி, 'தமிழ்நாடு' பெயர் மாற்றம், சுயமரியாதை திருமணச் சட்டம், இருமொழி கொள்கை (1968).
  - கலைஞர் கருணாநிதி: பிற்படுத்தப்பட்டோர் நலத்துறை, இலவச மின்சாரம், சமத்துவபுரம், கைரிக்ஷா ஒழிப்பு.
  - எம்.ஜி.ராமச்சந்திரன்: சத்துணவுத் திட்டம் (1982), தஞ்சை தமிழ்ப் பல்கலைக்கழகம், 69% இடஒதுக்கீடு வரலாறு.
- **Segment 6: திருக்குறள் மற்றும் தமிழ் அற இலக்கியங்கள் (15 Questions)**
  - திருக்குறளின் உலகளாவிய மனிதநேயக் கருத்துக்கள், சமய சார்பற்ற தன்மை.
  - அரசு நிர்வாகம், செங்கோன்மை, கொடுங்கோன்மை, அமைச்சு, ஒற்றாடல், தூது.
  - சமத்துவம், சமூக நீதி, கல்வி, ஒழுக்கமுடைமை, காலமறிதல், இடுக்கண் அழியாமை.
  - குறட்பா மேற்கோள்கள் & துல்லியமான உரைகள்.

### 2. Front-End Features & Interactive Experience
- **Visual Design**:
  - TNPSC Exam Navy Blue & Gold / Dark Emerald palette with light/dark theme switcher.
  - Modern typography: Crisp Tamil font stack with Google Noto Sans Tamil styling.
  - Card glassmorphism, responsive grid layout, micro-animations for feedback.
- **Question Layout & Mechanics**:
  - Question Badge indicating Segment, Question ID, and Question Type (e.g., [கூற்று - காரணம்], [பொருத்துக], [சரியான கூற்றை தேர்ந்தெடு], [நேரடி வினா]).
  - 4 Options (அ, ஆ, இ, ஈ) with instant hover and active states.
  - **Instant Feedback in Practice Mode**:
    - Clicking correct option: Turns Emerald Green with checkmark icon and celebratory pulse.
    - Clicking wrong option: Turns Crimson Red with gentle shake, instantly reveals the correct option in Green, and slides open the "பாடப்புத்தக மேற்கோள் & விளக்கம்" (Reference & Explanation) box.
    - Reference box provides the exact sentence and page context from the study PDF.
  - **Exam Simulation Mode**:
    - Select answers without immediate reveal.
    - Countdown timer (2 Hours / 120 mins).
    - Status indicators: Answered (Green), Not Answered (Grey), Marked for Review (Purple).
    - Submit button with confirmation dialog.
    - Result Dashboard with Score, Accuracy %, Time Spent, and Category-wise breakdown.
- **Tools & Navigation**:
  - Segment Selector Tabs (Filter questions by topic).
  - "தவறான விடைகளை மட்டும் பார்" (Review Incorrect Only) toggle.
  - Question Palette (Grid of 1-110+) with slide-out drawer on mobile and persistent sidebar on desktop.
  - Bookmark / "மீள் பார்வைக்கு குறிக்க" (Mark for Review) button.
  - Font Size Adjuster (A- / A / A+) for comfortable reading.
  - "மீண்டும் தொடங்குக" (Restart / Reset Quiz) feature.

---

## Proposed Changes

### Scripts & Data Generation
- Write `generate_quiz_data.py` in workspace to compile and validate the complete 110+ questions dataset strictly from `extracted_unit6_full.txt` with exact sentence references.

### Web Application
- Create `index.html` in `/home/santhakumar/Desktop/ESSC QUIZ/index.html`:
  - Standalone, zero-dependency HTML5 application.
  - Modern CSS embedded with dark/light themes, smooth transitions, and mobile responsiveness.
  - Complete JavaScript bundle containing question state management, instant feedback, timer, search, and analytics.

---

## Verification Plan

### Automated & Integrity Verification
1. **Question Bank Validation**:
   - Verify all 110+ questions have 4 options, a valid correct index, an authentic explanation citing the PDF, and zero syntax errors.
2. **Text Fidelity**:
   - Verify every question and answer is grounded in `extracted_unit6_full.txt`.

### Interactive Browser Verification
1. Load `index.html` in browser using `browser_subagent`.
2. Verify interactive clicking:
   - Wrong answer clicked -> Red highlight + Green reveal + Explanation box.
   - Correct answer clicked -> Green highlight + score increment.
   - Segment tab switching -> Correct questions displayed.
   - Mode switcher -> Practice vs Exam mode.
   - Exam submission -> Scorecard display.

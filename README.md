# HanziBoss

HanziBoss is a client-side Chinese vocabulary study app built around the HSK
Standard Course. It organizes vocabulary by HSK level and lesson, then
provides a vocabulary reference view and an interactive flashcard deck for
each lesson.

The current app includes HSK 1 through HSK 4 content. HSK 4 lessons also
include frequency-ranked important words and grammar notes based on the
included study data.

## Features

- Browse HSK 1, HSK 2, HSK 3, and HSK 4 levels by lesson
- View each lesson's hanzi, pinyin, part of speech, and English meaning
- Flip flashcards to reveal pronunciation and meaning
- Hear Mandarin pronunciation through the browser Speech Synthesis API
- Navigate cards with previous/next controls or the keyboard
  - Left and right arrows move between cards
  - Space and Enter flip the current card
- Shuffle a lesson deck or restart it from the beginning
- Track reviewed words and lesson progress in browser `localStorage`
- Show lesson completion status and continue to the next lesson
- Use HSK 4 Vocabulary, Important words, Grammar, and Flashcards tabs
- Hide or reveal pinyin in the vocabulary, important-word, and grammar views
- Switch between light and dark themes
- Responsive layout for desktop and mobile screens
- No account, backend, database, or build step required

## Run locally

HanziBoss is a static web app. A modern browser can open `index.html`
directly, but serving the folder over HTTP is recommended because it matches
how the app is normally hosted.

With Python installed, run:

```powershell
py -m http.server 8000
```

Then open <http://localhost:8000> in a browser.

You can also use any static-file server, such as the Live Server extension
for VS Code. There are no npm dependencies or package installation commands
for the current version.

## Browser requirements

Use a current version of Chrome, Edge, Firefox, or Safari. The app uses:

- JavaScript and React 18
- Browser `localStorage` for theme and progress preferences
- The Web Speech API for pronunciation
- CSS 3D transforms for the flashcard animation

Pronunciation depends on the browser and operating system providing a
Chinese (`zh-CN`) speech voice. The rest of the study experience works
without speech synthesis.

The page loads React, ReactDOM, Babel, Tailwind CSS, and Google Fonts from
public CDNs. An internet connection is therefore required for the complete
visual experience unless those assets are hosted locally.

## Project structure

The application is intentionally kept in one HTML file:

- `index.html` - document shell, styles, React components, HSK vocabulary,
  frequency data, grammar data, routing, progress storage, and application
  logic
- `LICENSE` - proprietary usage terms

The app uses hash routes, so level and lesson pages can be linked directly:

```text
#/                         Home and level selection
#/hsk/hsk1                 HSK level page
#/hsk/hsk1/lesson/1        Lesson page
```

## Data and privacy

Vocabulary and study metadata are bundled in `index.html`; the app does not
make requests to a project backend. Theme, selected study tab, and reviewed
word IDs are stored locally in the browser. Clearing the site's local
storage removes that local progress.

## License

Copyright (c) 2026 Ramzan Ali Sonnet. All rights reserved.

This project is proprietary. Copying, modifying, distributing, or using it
without prior written permission is not allowed. See [`LICENSE`](LICENSE) for
the complete terms.

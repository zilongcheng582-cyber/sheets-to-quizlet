# 🀄 Chinese Vocabulary → Quizlet Converter

A free, no-login, no-install web app that converts a Chinese vocabulary Google Sheet into a Quizlet-ready import file in under a minute.

[![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-4f8ef7?style=flat-square)](https://YOUR-USERNAME.github.io/sheets-to-quizlet/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

---

## What it does

Each row in your Google Sheet becomes one Quizlet flashcard:

| Google Sheets | | Quizlet Flashcard |
|---|---|---|
| Column A — `还是` | → | **Front:** `还是` |
| Column B — `háishi` | → | **Back:** `háishi — oppure / ancora` |
| Column C — `oppure / ancora` | → | *(combined into back)* |

The front shows only the Chinese characters. The back shows pinyin + Italian translation together.

---

## How to use

### Option 1 — Online (recommended)

Open the live site: **[https://YOUR-USERNAME.github.io/sheets-to-quizlet/](https://YOUR-USERNAME.github.io/sheets-to-quizlet/)**

No installation needed. Works on any browser, desktop or mobile.

### Option 2 — Run locally

```bash
git clone https://github.com/YOUR-USERNAME/sheets-to-quizlet.git
cd sheets-to-quizlet
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

---

## Step-by-step guide

**Step 1 — Copy from Google Sheets**
1. Open your vocabulary sheet
2. Click the first cell (A1)
3. Press `Ctrl+Shift+End` to select all rows
4. Press `Ctrl+C` to copy

**Step 2 — Paste into the app**
1. Open the app
2. Paste with `Ctrl+V` into the text box

**Step 3 — Generate**
1. Click **"Genera flashcard Quizlet"**
2. Check the card preview to make sure everything looks right

**Step 4 — Import into Quizlet**
1. Click **"Copia tutto"** (Copy all)
2. Go to [quizlet.com](https://quizlet.com) → click **"+"** → **"Create a study set"**
3. Click **"Import"** (Import from Word, Excel, Google Docs...)
4. Paste with `Ctrl+V`
5. Set separators: **Between term and definition = Tab** · **Between cards = New line**
6. Click **"Import"** — done! 🎉

---

## Expected data format

The app expects tab-separated columns, exactly as Google Sheets copies them:

```
还是    háishi      oppure / ancora
孩子    háizi       bambino, ragazzo
海风    hǎifēng     brezza di mare
韩国    Hánguó      Corea (del Sud)
```

- **Column A** — Chinese characters
- **Column B** — Pinyin
- **Column C** — Italian translation

Rows with missing data are skipped automatically.

---

## Project structure

```
sheets-to-quizlet/
├── index.html       # The entire app (single self-contained file)
├── README.md        # This file
├── LICENSE          # MIT License
└── .gitignore       # Standard gitignore
```

The whole app lives in a single `index.html` file — no dependencies, no build step, no frameworks.

---

## Deploy to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set Source to **Deploy from a branch → main → / (root)**
4. Save — your site will be live at `https://YOUR-USERNAME.github.io/sheets-to-quizlet/` within a minute

---

## Customisation

Want to adapt this for a different language pair or column order? Open `index.html` and edit the `convert()` function:

```js
const ch  = (cols[0] || '').trim();  // Column A → front of card
const py  = (cols[1] || '').trim();  // Column B → back line 1
const def = (cols[2] || '').trim();  // Column C → back line 2
```

Change the column indices (`cols[0]`, `cols[1]`, `cols[2]`) to match your sheet layout.

---

## License

[MIT](LICENSE) — free to use, modify, and share.

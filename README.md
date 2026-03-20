# Chinese Vocabulary to Quizlet Converter

A free, no-login, no-install web app that converts a Chinese vocabulary Google Sheet into a Quizlet-ready import file in under a minute.

[![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-4f8ef7?style=flat-square)](https://zilongcheng582-cyber.github.io/sheets-to-quizlet/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

-----

## What it does

Each row in your Google Sheet becomes one Quizlet flashcard:

|Google Sheets                |  |Quizlet Flashcard             |
|-----------------------------|--|------------------------------|
|Column A – Chinese characters|->|**Front:** Chinese characters |
|Column B – Pinyin            |->|**Back:** pinyin + translation|
|Column C – Translation       |->|*(combined into back)*        |

The front shows only the Chinese characters. The back shows pinyin + translation together.

-----

## How to use

### Option 1 – Online (recommended)

Open the live site: **<https://zilongcheng582-cyber.github.io/sheets-to-quizlet/>**

No installation needed. Works on any browser, desktop or mobile.

### Option 2 – Run locally

```
git clone https://github.com/zilongcheng582-cyber/sheets-to-quizlet.git
cd sheets-to-quizlet
start index.html
```

-----

## Step-by-step guide

**Step 1 – Copy from Google Sheets**

1. Open your vocabulary sheet
1. Click the first cell (A1)
1. Press Ctrl+Shift+End to select all rows
1. Press Ctrl+C to copy

**Step 2 – Paste into the app**

1. Open the app
1. Paste with Ctrl+V into the text box

**Step 3 – Generate**

1. Click “Generate Quizlet flashcards”
1. Check the card preview

**Step 4 – Import into Quizlet**

1. Click “Copy all”
1. Go to quizlet.com -> click “+” -> “Create a study set”
1. Click “Import”
1. Paste with Ctrl+V
1. Set separators: Between term and definition = Tab, Between cards = New line
1. Click “Import” – done!

-----

## Expected data format

The app expects tab-separated columns, exactly as Google Sheets copies them:

```
Column A    Column B    Column C
Chinese     Pinyin      Translation
```

Rows with missing data are skipped automatically.

-----

## Project structure

```
sheets-to-quizlet/
├── index.html       -- The entire app (single self-contained file)
├── README.md        -- This file
└── LICENSE          -- MIT License
```

The whole app lives in a single index.html file – no dependencies, no build step, no frameworks.

-----

## License

MIT – free to use, modify, and share.

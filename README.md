[English] | [Español](README.es.md)

This repository contains AI-generated translations of key books and essays related to **Effective Altruism** and **Rationality**. My goal is to make high-impact ideas accessible to a global audience by leveraging modern LLMs (Large Language Models) while preserving original formatting and context.

The translations made are far from perfect, but they are a good starting point and I consider it far better to have them available in this state than to not have them at all. Perfection is the enemy of the good, and the availability of these translations can help more people benefit from these ideas.

## 📋 Available Translations

Below is a list of completed translations. Each file is processed to maintain footnotes, internal links, and technical terminology.

| Book Title | Language | Quality | AI Model | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Rationality: From AI to Zombies** | Spanish | First attempt, basic review pending | Gemini 2.5 (Ch 1-21)/2.5 Flash Lite (Ch 22-53)/ 3.1 Flash Lite (54-end) | Batches of 8000 characters | |
| **Doing Good Better** | Spanish | First attempt, basic review pending | Gemini 2.5 Flash Lite | Batches of 30000 characters. Everything except the end of Notes and Index |

## 🛠️ Translation Methodology

**Existing translations (before 2026-10):** made with Calibre + the Ebook Translator plugin, using the Gemini models listed in the table.

**Now:** the project is maintained by an automated cloud pipeline that needs no Calibre and no computer of mine. It unpacks the EPUB, splits every chapter into paragraph-sized units (inline links, footnotes and images are kept as numbered placeholders), translates batches with Claude (the smallest model at low effort first; a stronger one only where automatic checks fail), checks every batch (nothing missing, nothing left in English, links intact, glossary terms respected), and writes a valid EPUB again. Progress is saved after every batch, so work can stop and resume at any time. Existing translations are not redone: gaps are filled and the worst passages are re-translated. Audit and quality reports live in `reports/`.

New books are taken one at a time from the [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive) (its public [Google Drive folder](https://drive.google.com/drive/folders/1CSKOlo2nE9JtD1u8fUssMyTqOoJEeYMQ)) or from files placed in `inbox/`. Sources and licence notes are listed in `sources.md`.

## 🩹 Corrections and Collaborations

If you want to help correcting errors or adding new translations, please open an Issue or Pull Request.

## 🔮 Future Possible Plans

- Add more translations to more languages of other EA and Rationality books, mainly those in the [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive).
- Improve the quality of existing translations, either manually or through better AIs.
- Fix the lose of external links of the translation system.
- If there is interest, convert to Markdown or HTML and add the way to unzip and zip epubs to facilitate corrections.
- Translation glossary.

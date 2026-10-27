[English] | [Español](README.es.md)

This repository contains AI-generated translations of key books and essays related to **Effective Altruism** and **Rationality**. My goal is to make high-impact ideas accessible to a global audience by leveraging modern LLMs (Large Language Models) while preserving original formatting and context.

The translations made are far from perfect, but they are a good starting point and I consider it far better to have them available in this state than to not have them at all. Perfection is the enemy of the good, and the availability of these translations can help more people benefit from these ideas.

<!-- downloads:start -->
### Downloads by language

Each language has its own release, so you can download only the books you need.

- **Spanish**: [release `es-latest`](https://github.com/Pato-desu/Translated-Effective-Altruist-books/releases/tag/es-latest), 2 EPUBs
  - `Hacer el bien mejor_ Como el Altruismo Eficaz puede hacer la diferencia - William MacAskill.epub` (1.0 MB)
  - `Racionalidad_ de la A a la Z - Eliezer Yudkowsky.epub` (3.9 MB)
- **Chinese (Simplified)**: [release `zh-latest`](https://github.com/Pato-desu/Translated-Effective-Altruist-books/releases/tag/zh-latest), 2 EPUBs
  - `危崖 The Precipice.epub` (0.4 MB)
  - `未来的亏欠 What We Owe the Future.epub` (0.3 MB)
<!-- downloads:end -->

## 📋 Available Translations

Below is a list of completed translations. Each file is processed to maintain footnotes, internal links, and technical terminology.

| Book Title | Language | Quality | AI Model | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Rationality: From AI to Zombies** | Spanish | First attempt, basic review pending | Gemini 2.5 (Ch 1-21)/2.5 Flash Lite (Ch 22-53)/ 3.1 Flash Lite (54-end) | Batches of 8000 characters. External links restored with Claude (2026-10), 97.8% kept | |
| **Doing Good Better** | Spanish | First attempt, basic review pending | Gemini 2.5 Flash Lite | Batches of 30000 characters. Complete since 2026-10 (the missing end of Notes and Index was filled in with Claude); external links restored. |

## 📚 Archive books (Spanish)

Translated from the text of PDFs in the [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive), with Claude, batch by batch with automatic checks. The files are in `Español/archive/`. Some PDF extraction debris remains in places (for example `[^` marks); repair is planned.

| Book | Author | File |
|---|---|---|
| *Animal Liberation* | Peter Singer | `Español/archive/Animal Liberation (PDFDrive).epub` |
| *Superintelligence* | Nick Bostrom | `Español/archive/Bostrom - Superintelligence Paths, Dangers, Strategies (PDFDrive).epub` |
| *The Scout Mindset* | Julia Galef | `Español/archive/Galef - The Scout Mindset.epub` |
| *The Most Good You Can Do* | Peter Singer | `Español/archive/Singer - Most Good You Can Do.epub` |
| *Avoiding the Worst* | Tobias Baumann | `Español/archive/baumann-avoiding-the-worst.epub` |
| *The Hedonistic Imperative* | David Pearce | `Español/archive/hedonistic imperative.epub` |
| *Reasoned Politics* | Magnus Vinding | `Español/archive/reasoned-politics.epub` |
| *Suffering-Focused Ethics* | Magnus Vinding | `Español/archive/suffering-focused-ethics.epub` |

## 🛠️ Translation Methodology

**Existing translations (before 2026-10):** made with Calibre + the Ebook Translator plugin, using the Gemini models listed in the table.

**Now:** the project is maintained by an automated cloud pipeline that needs no Calibre and no computer of mine. It unpacks the EPUB, splits every chapter into paragraph-sized units (inline links, footnotes and images are kept as numbered placeholders), translates batches with Claude (the smallest model at low effort first; a stronger one only where automatic checks fail), checks every batch (nothing missing, nothing left in English, links intact, glossary terms respected), and writes a valid EPUB again. Progress is saved after every batch, so work can stop and resume at any time. Existing translations are not redone: gaps are filled and the worst passages are re-translated. Audit and quality reports live in `reports/`.

New books are taken one at a time from the [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive) (its public [Google Drive folder](https://drive.google.com/drive/folders/1CSKOlo2nE9JtD1u8fUssMyTqOoJEeYMQ)) or from files placed in `inbox/`. Sources and licence notes are listed in `sources.md`.

## ⚙️ Commands

Python 3.11, `pip install -r requirements.txt`; run from this folder. No Calibre.

```
python -m pytest                                        # tests
python scripts/epub.py check <epub>... [--lenient]      # structural check of an EPUB
python scripts/epub.py audit                            # audit every original against its Spanish EPUB -> reports/
python scripts/epub.py split <book> <lang>              # cut a book into batches (lang: es or zh)
python scripts/epub.py status <book> <lang>             # progress, retries, stuck batches
python scripts/epub.py qa <book> <lang>                 # quality gate on translated batches
python scripts/epub.py merge <book> <lang>              # rebuild the translated file
python scripts/patch.py split <book> es                 # only the passages still in English
python scripts/links.py <book> es                       # restore external links lost by a translation
python scripts/consistency.py <book> es --mine 30       # term-consistency report -> reports/
python scripts/pdfread.py <file.pdf>                    # text PDF -> Markdown chapters in work/
python scripts/mdepub.py <book.md> --out <file.epub> --lang zh-Hans   # Markdown chapters -> one EPUB
```

## 🇨🇳 Chinese books

| Book | File | Notes |
|---|---|---|
| *The Precipice* (Toby Ord) | `Chinese/危崖 The Precipice.epub` | Translated from the PDF text; 672 notes linked both ways. |
| *What We Owe the Future* (William MacAskill) | `Chinese/未来的亏欠 What We Owe the Future.epub` | Translated from the PDF text; 798 notes, a few gaps where the PDF text lost a note (see `reports/`). |

Both are machine translations by Claude (Haiku, with Sonnet for retries), checked by the quality gate and a sampled review (`reports/quality-*-zh.md`). One file per book, EPUB only.

## ⚖️ Licences and attribution

- *Rationality: From AI to Zombies* by Eliezer Yudkowsky (MIRI) is released under CC BY-NC-SA 3.0. The Spanish translation is a derivative under the same licence: attribution, non-commercial, share-alike.
- *Doing Good Better* by William MacAskill is a published book; its translation rights belong to the author and publisher. The translation is shared here as a non-commercial accessibility effort; if a rights holder objects, open an Issue and it will be taken down.
- Every new book gets its source and what is known about its licence in `sources.md`; books with a clearly restrictive licence are not translated.

## ➕ How to add a book

1. Put the EPUB (or a text PDF, Markdown, HTML or plain text file) in `inbox/` and add a line to `QUEUE.md`, or open an Issue with a link.
2. Run `python scripts/epub.py split <book> <lang>`, translate the batches, `python scripts/epub.py qa <book> <lang>`, then `merge`. Details are in `TRANSLATE.md` (Spanish), `TRANSLATE.zh.md` (Chinese) and `DISPATCH.md`.
3. Check the result with `python scripts/epub.py check` and `audit`.

## 🩹 Corrections and Collaborations

If you want to help correcting errors or adding new translations, please open an Issue or Pull Request.

## 🔮 Future Possible Plans

- Add more translations to more languages of other EA and Rationality books, mainly those in the [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive).
- Improve the quality of existing translations, either manually or through better AIs.
- If there is interest, convert to Markdown or HTML and add the way to unzip and zip epubs to facilitate corrections.
- Quality sample review and re-translation of the worst passages.

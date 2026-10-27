# Translated books on Effective Altruism and Rationality

**English** · [Español](README.es.md) · [中文](README.zh.md)

AI-generated EPUB translations of key books on **Effective Altruism** and **Rationality**, into Spanish and Simplified Chinese. The goal is to make these ideas available to more people. The translations are not perfect, but having them in this state is far better than not having them at all.

<!-- downloads:start -->
### Download everything in one language

Each language has one release with all its books as files. To get a single book, use its link in the table below.

- **Spanish**: 10 books, [download all](https://github.com/Pato-desu/Translated-Effective-Altruist-books/releases/tag/es-latest)
- **Chinese**: 2 books, [download all](https://github.com/Pato-desu/Translated-Effective-Altruist-books/releases/tag/zh-latest)
<!-- downloads:end -->

## Books

Click a title's file link to download that EPUB. All files open in any e-reader.

| Book | Author | Language | Download | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Rationality: From AI to Zombies** | Eliezer Yudkowsky | Spanish | [EPUB](Espa%C3%B1ol/Racionalidad_%20de%20la%20A%20a%20la%20Z%20-%20Eliezer%20Yudkowsky.epub) | Translated with Gemini; external links restored with Claude. Basic review pending. |
| **Doing Good Better** | William MacAskill | Spanish | [EPUB](Espa%C3%B1ol/Hacer%20el%20bien%20mejor_%20Como%20el%20Altruismo%20Eficaz%20puede%20hacer%20la%20diferencia%20-%20William%20MacAskill.epub) | Translated with Gemini; the missing end of the notes and the index were filled in with Claude. Basic review pending. |
| **Animal Liberation** | Peter Singer | Spanish | [EPUB](Espa%C3%B1ol/archive/Animal%20Liberation%20%28PDFDrive%29.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **Superintelligence** | Nick Bostrom | Spanish | [EPUB](Espa%C3%B1ol/archive/Bostrom%20-%20Superintelligence%20Paths%2C%20Dangers%2C%20Strategies%20%28PDFDrive%29.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **The Scout Mindset** | Julia Galef | Spanish | [EPUB](Espa%C3%B1ol/archive/Galef%20-%20The%20Scout%20Mindset.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **The Most Good You Can Do** | Peter Singer | Spanish | [EPUB](Espa%C3%B1ol/archive/Singer%20-%20Most%20Good%20You%20Can%20Do.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **Avoiding the Worst** | Tobias Baumann | Spanish | [EPUB](Espa%C3%B1ol/archive/baumann-avoiding-the-worst.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **The Hedonistic Imperative** | David Pearce | Spanish | [EPUB](Espa%C3%B1ol/archive/hedonistic%20imperative.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **Reasoned Politics** | Magnus Vinding | Spanish | [EPUB](Espa%C3%B1ol/archive/reasoned-politics.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **Suffering-Focused Ethics** | Magnus Vinding | Spanish | [EPUB](Espa%C3%B1ol/archive/suffering-focused-ethics.epub) | Translated with Claude from the PDF text. Some PDF debris remains; index and bibliography entries stay in English. |
| **The Precipice** | Toby Ord | Chinese | [EPUB](Chinese/%E5%8D%B1%E5%B4%96%20The%20Precipice.epub) | Translated with Claude from the PDF text. 672 notes, linked both ways. |
| **What We Owe the Future** | William MacAskill | Chinese | [EPUB](Chinese/%E6%9C%AA%E6%9D%A5%E7%9A%84%E4%BA%8F%E6%AC%A0%20What%20We%20Owe%20the%20Future.epub) | Translated with Claude from the PDF text. 798 notes; a few gaps where the PDF lost a note. |

## How they were made and how good they are

Every book is cut into paragraph-sized batches (links, footnotes and images are kept as placeholders), translated by an AI model, and checked automatically: nothing missing, nothing left in English, links intact, key terms translated consistently. Failed batches are redone, then the EPUB is rebuilt. The earliest two Spanish books were made with Calibre and Gemini; everything since is made by an automated pipeline with Claude.

**What to expect:** no human has proofread these books. Books taken from PDFs can still show extraction debris (stray `[^` marks, odd line breaks). Quality and audit reports are in [`reports/`](reports/).

## Report a mistake or ask for a book

Open an [Issue](../../issues) or a Pull Request to report errors, offer corrections or suggest a book. What is queued next is in [`QUEUE.md`](QUEUE.md). New books come from the [EA Archive](https://forum.effectivealtruism.org/posts/DndmvDGStD3gTfhXk/announcing-the-ea-archive) or from files added to `inbox/`.

## Licences and attribution

- *Rationality: From AI to Zombies* by Eliezer Yudkowsky (MIRI) is released under CC BY-NC-SA 3.0. Its Spanish translation is a derivative under the same licence: attribution, non-commercial, share-alike.
- All other books are published works whose rights belong to their authors and publishers. They are shared here as a non-commercial accessibility effort. If a rights holder objects, open an Issue and the file will be taken down.
- [`sources.md`](sources.md) lists where each book came from and what is known about its licence.

## For developers

Python 3.11; `pip install -r requirements.txt`; run from this folder. No Calibre.

**Adding a book:** put the file (EPUB, text PDF, Markdown, HTML or plain text) in `inbox/` and add a line to `QUEUE.md`. `python scripts/epub.py split <book> <lang>`, translate the batches, then `qa` and `merge`. Details: `TRANSLATE.md` (Spanish), `TRANSLATE.zh.md` (Chinese), `DISPATCH.md`. After adding a book, add its row to the table in all three READMEs; `python -m pytest` fails if one is missing.

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
python scripts/archive.py prepare|finish <file> <lang>  # PDF, text or HTML file -> Español/archive/
python scripts/publish.py [--dry-run]                   # copy the public files to the public repo and refresh releases
```

# Quality review: Rationality, From AI to Zombies (es)

Reviewer: Sonnet 5.5 (the run itself, route `self`), task M3.4, 2026-10-21. Method: `python scripts/quality.py rationality es --dump F --scores F`.
The original is split into the project's 396 batches (`work/rationality/es/`; batch 1 holds only the OPF and NCX labels and is not compared), every original unit is lined up with the unit of the existing Spanish EPUB (monotone alignment, `links.align`, when the unit counts of a file differ), and the QA gate is run on the aligned text for all 395 content batches. A deterministic sample of 12 batches (3.0%, evenly spread over the book, seed 34) was then read, English against Spanish: 19, 54, 95, 130, 162, 178, 230, 246, 275, 301, 348, 369 (about 330 units).

## Sampled batches

| Batch | Where | Verdict |
|---|---|---|
| 19 | End of "Expecting Short Inferential Distances", start of "The Lens That Sees Its Own Flaws" | Faithful. Links and emphasis land on the wrong words ("ramas de <Everett, o duplicados> de Tegmark"). |
| 54 | "Absolute Authority" | Faithful, one real error: "except for the Virgin Birth" became "excepto por la Virgen María" (c070u0019). Mixed tu and impersonal. |
| 95 | Happy death spiral, "Uncritical Supercriticality" | Good. Block quote paragraph lost: "Cut up your Great Thingy..." merged into the next paragraph (c125u0026 has no Spanish unit); "—Deuteronomy 13:7–11, emphasis added" lost (c126u0010). Mix of "volverle loco" and "tú". |
| 130 | Parental grief, "Superstimuli" | Good. "consideren" (plural) in a tu text; markup spans on the wrong words (c164u0013 "mentes en el"). Attribution line lost (c164u0004). |
| 162 | "Arguing By Definition" | Content right, structure broken: the Danny and Erda dialogue (c195u0006 to 0010) is merged into one paragraph, so units 7, 9 and 10 have no counterpart. |
| 178 | Bayes' Theorem notation | Good, no issue. |
| 230 | "Zombies: The Movie" | Good; script format kept. Style "Muy bien. Recopile un informe" (usted) next to "¿Puedes oírme?" (tu). |
| 246 | "Many Worlds" | Good. Emphasis on the wrong words (c269u0017, c269u0018). |
| 275 | "Class Project" | Good. Switches to « » quotes in the middle of the chapter (c289u0034 onward) while the rest of the book uses straight quotes. |
| 301 | "My Best and Worst Mistake" | Good. |
| 348 | End of Book (acknowledgement chapter) | Good. Duplicated word: "transmitir, transmitir, compartir" for "convey, pass on, share" (c344u0020). |
| 369 | "Empathy and the paperclip maximizer" | Good. |

Reading result: the Spanish is accurate and readable in all 12 batches; the translation reads like a fluent human one. Defects are structural or consistency ones. One factual mistranslation in 330 units.

## Issues found

1. Paragraph structure lost where the old tool merged units. 447 of 11,070 units have no aligned Spanish unit (4.0%), concentrated in 113 batches; the biggest are dialogue chapters (batches 248, 158, 152, 226, 156, 199, 155). In "Zombies: The Movie" style chapters whole exchanges (BERNICE:, CHARLES:, ...) are one paragraph in Spanish. Text is all there, but the reading experience suffers. This needs a re-translation of the whole file from the source structure (the source unit ids map one to one), not a unit patch.
2. Emphasis and link spans on the wrong words: the old tool dropped inline markup and M3.2 restored links by relative position (documented limit); italics are also off. 6,349 placeholder differences over the book. Cosmetic, spread everywhere.
3. Mistranslation: "Virgin Birth" as "la Virgen María" (batch 54, c070u0019).
4. Register mixes tu, usted and plural (batches 54, 95, 130, 230, 275). Same D1 question as in Doing Good Better.
5. Quotation marks: straight quotes in most of the book, « » in part of "Class Project" (batch 275) and in some other chapters.
6. Headings: chapter headings in title case ("La Lente Que Ve Sus Propios Defectos", "Libro I Mapa y Territorio") against sentence case in others ("Superestímulos y el colapso de la civilización occidental"). TRANSLATE.md asks for sentence case.
7. The `<title>` element of each chapter file is still English ("40 My Wild and Reckless Youth"): only visible in the browser tab or some readers' chapter lists; the visible headings and the contents (NCX, 378 entries) are Spanish. The EPUB title is "Racionalidad: De la IA a los Zombis [Spanish]" (a stray "[Spanish]" in dc:title).
8. Bibliography (batches 290 to 298): author, title, journal and publisher stay English by design; 341 units are flagged as "English" over the book, nearly all of them these bibliography entries and chapter `<title>` lines. Not a defect.
9. Small slips: duplicated word (batch 348), lost attribution lines (batches 95, 130, "—Deuteronomy 13:7–11").

Automatic QA over the 395 batches: 341 units flagged English (bibliography, titles, citations), 33 glossary misses (mostly the accepted "IA amistosa" family and "conjunction fallacy"), 12 length anomalies, 447 unaligned units.

## Ranked list of the worst batches

| Rank | Batch | Why |
|---:|---:|---|
| 1 | 248 | 23 of 62 units merged away: the Gallant and Goofus dialogue (c271u0014 to 0016 and more), "Does the moon exist when no one is looking at it?" |
| 2 | 158 | 20 of 54 units merged, one length ratio of 3.62 (c190u0004) |
| 3 | 152 | 19 of 40 units merged |
| 4 | 226 | 18 of 29 units merged: the Bernice, Charles, Albert and Penrose dialogue is one paragraph (verified in the EPUB) |
| 5 | 156 | 16 of 45 merged |
| 6 | 199 | 14 of 54 merged |
| 7 | 155 | 14 of 40 merged |
| 8 | 162 | Sampled: Danny and Erda dialogue merged (3 units lost) |
| 9 | 54 | Sampled: "Virgin Birth" mistranslated |
| 10 | 95 | Sampled: block quote and attribution lost |
| By design | 290 to 298 | Bibliography entries kept in English |

Batch 1 (OPF and NCX labels only) is not ranked; the 378 contents entries read well.

## What to do (feeds M3.5)

- Fix the "Virgin Birth" unit (done in M3.5 if the cap allows).
- Re-translate chapter files with merged dialogue (batches 226, 248, 155, 156, 158, 152, 199) from the source structure: needs a file-level replace tool; about 7 batches, 14 to 20 in the next run.
- Not planned: tu/usted (D1), heading case, quote style, chapter `<title>` text.

## After the repair (M3.5, 2026-10-21)

Only the factual error was repaired inside this run's cap: batch 54, c070u0019 ("Virgin Birth" now "nacimiento virginal", both occurrences), through `patch.py ... --name redo` (`work/rationality/es-redo/`, QA passed). The merged-dialogue batches (248, 158, 152, 226, 156, 199, 155) need a file-level re-translation from the source structure and were not started: left in TASKS.md as follow-up M3.5b.

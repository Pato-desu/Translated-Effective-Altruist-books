# Quality review: Doing Good Better (es)

Reviewer: Sonnet 5.5 (the run itself, route `self`), task M3.4, 2026-10-21. Method: `python scripts/quality.py "doing good" es --dump F --scores F`.
The original is split into the project's 68 batches (`work/doing-good-better/es/`), every original unit is lined up with the unit of the existing Spanish EPUB (after the M3.1 patch and M3.2 links; the committed EPUB had to be rebuilt first, see M3.5), and the QA gate is run on the aligned text for every batch. A deterministic sample (3 batches, 4.4% of 68, evenly spread, seed 34) was then read in full, English against Spanish.

## Sampled batches

| Batch | Units | Where | Verdict |
|---|---:|---|---|
| 12 | 15 | Chapter 5, aid effectiveness, fat-tailed distributions | Faithful, complete, numbers kept. Issues below (term drift, register). |
| 36 | 21 | End of chapter 8 and start of chapter 9 ("Don't follow your passion") | Faithful and natural. Issues: tu/usted, straight quotes, calques. |
| 65 | 128 | Last notes, start of the Index | Notes translated (after M3.1). 14 note lead-ins and the Index note "Page numbers in italics refer to illustrations" are still English; index entries are English by D4. |

Reading result: no omissions, no invented content, no mistranslated figures in the 3 samples. Meaning is carried correctly in all 164 sampled units; the problems are consistency and polish, plus the residue of English in the notes.

## Issues found

1. Register mixes tu and usted. Batch 12 says "Mire el siguiente gráfico" and "Es posible que haya oído" (usted), then "si quieres aprender un idioma" (tu). Batch 36 is tu throughout ("tu carrera", "Pregúntate"). The patched Index note uses usted ("El enlace le llevará"). TRANSLATE.md asks for usted or impersonal forms; the old translation never followed it. A single rule is a D1 follow-up (see the report to the owner), not a per-batch fix.
2. Term drift for "fat-tailed": "cola gorda" (c011u0022) against "colas pesadas" (c011u0023, c011u0024) in neighbouring paragraphs. "Distribución de cola pesada" is the usual Spanish term and should win. The glossary has no entry for it.
3. Quotation marks: straight quotes ("funcionan", "SIGAS TU PASIÓN") next to typographic quotes in the same chapter; Spanish quotes in batch 36 are all straight.
4. Calques and word order: "¿Qué tan bien este trabajo desarrolla mis habilidades...?" (c018u0010, English order kept), "Discutamos cada uno de estos tres factores clave a su vez", "Basado en la evidencia, la respuesta parece ser no", "Primero, y lo más simple". They are understandable; none changes the meaning.
5. Running title "Doing Good Better" is left in English in the page headers (c018u0001, c024u0001). The Spanish title of the EPUB is "Hacer el bien mejor", so these should follow it.
6. Notes: 14 note lead-in phrases (the quoted words of the main text that a note is attached to) and several explanatory sentences are still English: c023u0329, 0333, 0334, 0336, 0337, 0339, 0340, 0341, 0342, 0349, 0351, 0353, 0355 and c023u0056, 0085, 0087, 0245. About half are reference titles that stay English by design; the rest is real text (for example c023u0334 "This three-factor model of cause evaluation was first proposed by GiveWell...", c023u0336 "Again, I'm inflation-adjusting...").
7. Index: 102 entries and the line "Note: Page numbers in italics refer to illustrations" are English. D4 says the Index keeps its English terms, so entries are accepted; the Note line is real text and should be Spanish.
8. Markup: 825 placeholder differences over the book (batches 1, 30, 31 and the notes batches 50 to 61 are the worst). The old translation tool dropped italic spans (book titles in the notes, emphasis in the text), so titles such as the "Handbook of Principles of Organizational Behavior" in the notes are no longer italic. This is cosmetic and cannot be fixed without re-translating those batches; not done.

Automatic QA over all 68 batches (the gate run on the aligned text): 124 units flagged as still English (all in the notes and the Index, none in the chapters), 22 glossary misses ("philanthropy", "deworming", "tractability", "factory farming", "DALY"), no length anomaly, no unaligned unit.

## Ranked list of the worst batches

Ranked by content defects first (English left, wrong or missing text), then by consistency and markup. Index batches are listed apart because D4 accepts them.

| Rank | Batch | Why | Auto points |
|---:|---:|---|---:|
| 1 | 64 | Notes of chapters 9 and 10: 6 lead-ins or explanations still English (c023u0329, 0333, 0334, 0340, 0341, 0342), 2 glossary misses | 20.0 |
| 2 | 65 | Last notes: 2 English lead-ins (c023u0351, 0353), "Note: Page numbers in italics..." (c024u0004), index start | 53.3 (index excluded: about 8) |
| 3 | 63 | Notes of chapter 9: 3 English lead-ins (c023u0316, 0318, 0323), many italic spans lost | 13.0 |
| 4 | 54 | Notes of chapter 6: 2 English explanations (c023u0085, 0087), 22 placeholder differences | 11.5 |
| 5 | 61 | Notes: c023u0245 English, 28 placeholder differences | 10.0 |
| 6 | 52 | Notes: c023u0056 English | 7.5 |
| 7 | 12 | Sampled: "cola gorda" against "colas pesadas", tu/usted mix | 3.5 |
| 8 | 36 | Sampled: tu throughout, straight quotes, calques | 3.0 |
| 9 | 1 | Front matter: 44 placeholder differences, glossary miss ("philanthropy") | 12.0 |
| 10 | 30 | Chapter 8: 32 placeholder differences, "deworming" glossary miss | 12.0 |
| Accepted (D4) | 66, 67, 68 | Index entries in English by design (205, 221 and 131 units) | not ranked |

Batches 1, 30 and 31 are ranked below the notes because their defect is lost italics, not English text.

## What to do (feeds M3.5)

- Re-translate the 14 English note units in batches 63, 64, 65, 54, 61, 52 and the Index note line, QA them, apply them in place (done in M3.5, see TASKS.md).
- Not planned inside the per-run cap: tu/usted unification (needs the owner's answer to D1), "cola pesada" term (add to `glossary.es.tsv`), lost italics (would need a re-translation of about 20 batches).

## After the repair (M3.5, 2026-10-21)

17 units redone by the run itself (route `self`, cap 15 batches: 1 batch used) through `python scripts/patch.py split "doing good" es --ids F --name redo` and `apply --name redo` (`work/doing-good-better/es-redo/`, QA passed before applying): the note lead-ins and explanations c023u0316 to 0355 and the Index note c024u0004. Auto score (QA gate on the aligned text) before and after:

| Batch | English units | Glossary misses | Points |
|---:|---:|---:|---:|
| 63 | 3 to 0 | 0 | 13.0 to 4.0 |
| 64 | 6 to 0 | 2 to 0 | 20.0 to 0.0 |
| 65 | 17 to 14 (all Index entries, D4) | 2 to 1 | 53.3 to 43.3 |

Not redone: batches 52, 54, 61 (one or two flagged units each, which are reference titles) and the stylistic items.

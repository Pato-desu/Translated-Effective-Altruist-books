# Quality review: The Precipice (zh)

Reviewer: Sonnet 5.5, task M2.5. `scripts/quality.py` does not accept this book (it only finds EPUBs in `English, Original/` and `inbox/`), so the sample was chosen by hand: 4 of 76 batches (5.3%), spread over front matter, early, middle, late chapters and the bibliography. Each sampled batch was read unit by unit, English against Chinese, for omissions, numbers and names, calques, glossary drift, punctuation and unrendered English.

## Sampled batches

| Batch | Units | Where | Verdict |
|---:|---:|---|---|
| 2 | 14 | Preface end, start of Chapter 1 | Good. Complete, names and figures right (GWWC, GBP 1 billion, Oxford). Only style nits. |
| 20 | 14 | Chapter 3, total natural risk (fossil-record estimates, Table 3.4) | Real defects, fixed (below). |
| 45 | 41 | Chapter 6, risk factors, "mathematics of risk factors" | Acceptable. Formula fragments are broken in the source itself (PDF line breaks, lost subscripts) and the translation keeps them in order. |
| 60 | 11 | Chapter 7 end, the value of the future | Good. Complete, natural, figures right. |
| 72 | 1 | Bibliography (A to C) | Acceptable. 78 of 78 years kept, placeholders kept. |

Glossary check by eye: 危崖, 生存性风险, 风险因素, 生存安全, 大国战争, 核冬天 and the others met in the samples all follow `glossary.zh.tsv`. No half-width punctuation, no English runs, no omitted unit in any sample.

## Issues found

1. Batch 20, c000u0352 (fixed): "one in 2,000" (per century) was rendered "每2000个世纪一次" and "zero in 2,000" as "每2000个世纪零次". That reads as a rate of once per 2,000 centuries, a different quantity from the 0.05% per century that the same paragraph states. Now "每世纪二千分之一" and "二千分之零到二千分之一".
2. Batch 20, c000u0347 (fixed): a character was dropped, "很快就会明的原因", now "很快就会明了的原因".
3. Batch 20, c000u0348 (fixed): "how recently many of these risks were discovered" became "近几年才被发现", yet the dates that follow are 1906, 1960 and 1969. Now "被发现的时间之晚，令人瞩目".
4. Batch 20, c000u0354: the Table 3.4 text is flattened into one unit in the source; the translation keeps all rows and figures. Left as is.
5. Batch 2, c000u0030 "核心重心" is redundant; batch 60, c000u1035 "无人敢想" is slightly loose. Style only, not changed.
6. Batch 45, c000u0770: "most of the potential value of the future" came out as "大部分潜在价值都在于未来", a mild inversion of the meaning. The point (similar stakes) is still conveyed. Not changed.
7. Batch 72: journal names and publishers are mixed (some translated, some left English such as "Futures", "St. Martin's Press"). Allowed by the brief for citations; cosmetic.

## Ranked worst batches (of the sample)

| Rank | Batch | Why |
|---:|---:|---|
| 1 | 20 | Three real defects, all fixed |
| 2 | 45 | Formula fragments awkward (source problem); one mild inversion |
| 3 | 72 | Mixed citation style |
| 4 | 2 | Style nits |
| 5 | 60 | Clean |

## Fixes made

Batch 20 only (`work/precipice/zh/batch-0020.out.json`: units c000u0347, c000u0348, c000u0352). Ids, order and placeholders untouched. `python scripts/epub.py qa work/precipice/precipice.md zh`: 76 translated batches checked, 76 passed, 0 failed. EPUB not rebuilt (the next merge picks the fix up).

## Verdict

Good overall. Sentences are natural written Chinese, terms follow the glossary, figures are right. In the 4 sampled batches (about 5% of the book) one batch had real errors (numerical rate wording), now fixed; the error rate suggests roughly one batch in four to five may carry a small slip of this kind. The unsampled remainder is probably usable but not proven.

# Quality review: What We Owe the Future (zh)

Reviewer: Sonnet 5.5, task M2.5. `scripts/quality.py` does not accept this book (no EPUB in `English, Original/` or `inbox/`), so the sample was chosen by hand: 4 of 70 batches (5.7%), spread over Part I, the middle of the book, Part IV and the acknowledgements and appendices. Each was read unit by unit, English against Chinese.

## Sampled batches

| Batch | Units | Where | Verdict |
|---:|---:|---|---|
| 3 | 27 | Chapter 1, "The Future Is Big" (figures, population estimates) | Good. All figures checked against the source (2.5 million years, 80 trillion, 70 billion, 10^18 years). |
| 25 | 26 | Chapter 4, lock-in, COVID-19 responses, Burdekin passage | Good. Names and dates right, quotation rendered naturally. |
| 50 | 24 | Chapter 8 end and start of Chapter 9 | One mistranslation, fixed (below). Powers of ten verified. |
| 68 | 54 | Acknowledgements, Further Resources, Terminology | Good. Names with English in brackets as the brief asks; URLs kept. |

No omissions, no half-width punctuation, no runs of English, glossary terms (长期主义, 轨迹改变, 人口伦理学, 感知能力, 反乌托邦) consistent.

## Issues found

1. Batch 50, c000u0982 (fixed): "a civilisation that is spread out across many solar systems" was rendered "分布在众多星系中的文明" (galaxies). The next sentence uses galaxies for another scale, so the text became inconsistent. Now "众多恒星系中".
2. Batch 3, c000u0053: "时间尺度就会变得真正意义上的天文数字" is an awkward calque of "literally astronomical". Understandable; not changed.
3. Batch 3, c000u0043: "不欠他们因给予我们的好处而需要的回报" is clumsy for "nor would we owe them repayment for benefits". Meaning intact; not changed.
4. Batch 3, c000u0040: "partiality" as 偏袒 (usually 偏私/偏爱). Minor term choice; not changed.
5. Batches 25 and 50 contain source units split mid-sentence by the PDF layout (c000u0497 to 0511, c000u0993 to 1002); the translation follows the fragments, so those units read as broken clauses individually but concatenate correctly.
6. Source artifacts such as "Figure1.1.Thehistory..." were translated cleanly into captions.

## Ranked worst batches (of the sample)

| Rank | Batch | Why |
|---:|---:|---|
| 1 | 50 | Solar systems rendered as galaxies (fixed) |
| 2 | 3 | Two clumsy calques, term choice |
| 3 | 25 | Clean apart from fragment splits |
| 4 | 68 | Clean |

## Fixes made

Batch 50 only (`work/wwotf/zh/batch-0050.out.json`, unit c000u0982). Ids, order and placeholders untouched. `python scripts/epub.py qa work/wwotf/wwotf.md zh`: 70 translated batches checked, 70 passed, 0 failed. EPUB not rebuilt.

## Verdict

Good. Faithful and fluent; every figure checked was right. One factual mistranslation in 4 batches (fixed), the rest are style nits. The unsampled remainder is probably usable but not proven.

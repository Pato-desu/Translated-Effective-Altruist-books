# Translation queue
Tracked list of what to translate, in order. Runs take the first open item (`[ ]`), tick it when it passes QA (`[x]`) and write `[~]` while a file is in progress (with the batches done, for example `[~] 12/40`). `[-]` means skipped, with the reason. Task M1.1 expands each folder into its files; files inside a folder are ordered short first, then clearer licence. The owner can reorder or cross out lines in FEEDBACK.md ("ea-books-translation: queue ...") or by editing this file in a session. Runs never reorder owner-set priorities.

Drive root `1CSKOlo2nE9JtD1u8fUssMyTqOoJEeYMQ` (EA Archive 1.3). Format of a line: `[ ] <target> · <path> · <Drive id> · <size> · <format> · <notes>`

## Priority 0 (owner, 2026-10-21): to Chinese, folder `Chinese/`, one EPUB per book ([D13], [D15])
- [ ] zh · Main content / book pdfs / Core EA / Ord - Precipice.pdf · 1jgKOSq7XW1vgsvpKOcdS93NmZ7PynG17 · 7 MB · pdf · The Precipice
- [ ] zh · Main content / book pdfs / Core EA / What We Owe Future Macaskill.pdf · 1PvUXgSNsXMFa52IqZVshiVnq28xUyHRY · 20 MB · pdf · What We Owe the Future

## Priority 1: existing Spanish books, repair
- [ ] es · Doing Good Better, missing end of Notes and Index (see the audit) · local EPUB
- [ ] es · Rationality: From AI to Zombies, worst batches found by the quality sample · local EPUB

## Priority 2: the rest of the archive, to Spanish, in the owner's folder order ([D9])
Folder ids: Main content mini `1bldzosR5QaYwO5pmDQbgCgCleMlT0DpE` (129 MB, plain text) · Non-EA stuff `1gtrAZkQ3Uj_f9M8AeTMMjefD-F5FdCDx` (21 GB) · Main content `1U0GWA2IUe11K8jzWTPATIhazn-FPzAQC` (about 3 GB; subfolders seen: book pdfs `1v9PP1Cx4WlOWdtU6iT7E5wUjxIVr0dLw`, charity entrepreneurship, chai, all OWID data, allfed, and more). The Audio folder is ignored.
- [ ] es · Main content mini · 1bldzosR5QaYwO5pmDQbgCgCleMlT0DpE · expand into files (M1.1 / M4.1)
- [ ] es · Non-EA stuff for the post-apocalypse · 1gtrAZkQ3Uj_f9M8AeTMMjefD-F5FdCDx · expand into files later
- [ ] es · Main content, everything else (the rest of book pdfs first) · 1U0GWA2IUe11K8jzWTPATIhazn-FPzAQC · expand into files later

## Core EA files (mapped 2026-10-21, M1.1; folder `1UIINZqXaqOWb--3qZ1Pt4kYsR4Dked3k`, 5 files; the folder listing had more pages not yet read)
- [x] suffering-focused-ethics.pdf · 1-Iywc29LrFv6ml1eSsIaeuRqrgxEMV3y · 1.0 MB · pdf · es done 2026-10-24 (91/91 batches, `Español/archive/suffering-focused-ethics.epub`; bibliography titles kept in English via qa-accept.txt)
- [x] hedonistic imperative.pdf · 1hYBUZGxhmKrrY7RMw6pfE6ri7t8DzVbg · 0.9 MB · pdf · es done 2026-10-24 (45/45 batches, `Español/archive/hedonistic imperative.epub`)
- CFAR_Handbook_2021.pdf · 1dAoO-eT0TG7YUVdTuaKtr_krIE5_8Fxn · 29 MB · pdf
- Sibling folders of book pdfs: Math, engineering, hard science `1ZevXhaI7pZTn3uvWtLFWIvTUqY6SuTeQ` · Nonfiction written for gen audience `14UIKJpbUCwKoKNOcwBuVtqoTkiUNACCZ` · History `1jZXJMt1Fl0RX_Zodg4o_-trz1531bIWR` · Nonfiction social science `1jky39eR7IOhOAvsAC-ZyeKt5Hkpp98Hj`
- Fetch note: the Drive connector's download returns file bytes as base64 inside the reply, too large to handle for 7-20 MB PDFs. Until a way is found (M1.1 retry), the two Priority 0 PDFs need dropping into `inbox/` by the owner.

- [x] reasoned-politics.pdf · local inbox · 2.2 MB · pdf · es done 2026-10-25 (89/89 batches, `Español/archive/reasoned-politics.epub`; bibliography titles kept in English via qa-accept.txt)
- [x] Baumann - Avoiding Worst final.pdf · local inbox · 2.2 MB · pdf · es done 2026-10-24 (25/25 batches, `Español/archive/baumann-avoiding-the-worst.epub`)
- [x] Singer - Most Good You Can Do.pdf · local inbox · 0.8 MB · pdf · es done 2026-10-26 (43/43 batches, `Español/archive/Singer - Most Good You Can Do.epub`; index and bibliography ids kept in English via qa-accept.txt)
- [~] Bostrom - Superintelligence (PDFDrive).pdf · local inbox · 3.5 MB · pdf · es 38/118 batches

## Main content mini (mapped 2026-10-23, M4.1 partial)
Four subfolders: chai `12GrAPrQ_gQ_EHfSQYFI0cB8--RBhrGDW`, wild animal initiative `1JnXiI77_p1z9FiNvoAkRaOB4vtXy5uRw`, animal charity evaluators `13AtxJZnwbcT_vMcTmASUGNlWrxLKYXe3`, allfed `1-EQxSARRkBU6FGl73BOo_Cdd9h-o6RRa`. A combined parent query returned only 3 files (the listing looks capped; query one folder at a time next run).
- synthetic.pdf.txt · 1dGAKyRQa9uJ-zo_YCCUlwx0U9EQFOvQh · 99 KB · txt · allfed
- mapping-political-economy-reinforcement-learning-systems-case-autonomous-vehicles.txt · 17NTCeibxtMWvwDOjh2OXq3SMpMePX6yT · 42 KB · txt · chai
- (a 1 KB Google Scholar citation page in chai, skip)

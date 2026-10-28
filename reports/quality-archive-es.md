# Spanish translation quality: archive books (spot check)

Method: 2 batches per book (about 25% and 75% of the batch numbers; none mostly bibliography), 20 batches and about 430 units. English and Spanish read side by side, plus scripts for unit-length ratio (omissions), tu/vos/Spain-only words, leftover English words and glossary renderings. Long units were read in full only in part (first 400-500 characters side by side, tails spot-checked), so a short omission mid-unit could be missed. The brief is TRANSLATE.md.

## Verdict per book

| Book | Batches read | Verdict | Main issues |
|---|---|---|---|
| hedonistic-imperative | 0011, 0034 | good | One real meaning error ("pharmacotherapies" -> "psicoterapias", 0034). "enhanced functional roles" -> "más intensos" is a loose rendering. Dense, difficult prose handled well. |
| suffering-focused-ethics | 0023, 0068 | good (0068 fair) | 0023 clean. 0068 slips into tu ("cambies de opinión", "trabajas", "creas", "tu defensa") in the climate-advocacy passage, while the rest of the batch uses impersonal forms. Source is full of PDF debris (ligature loss "suffff", "ThThe", lines split into one unit per PDF line). |
| baumann | 0006, 0018 | good | Faithful, footnotes kept. Term "s-risk" is "s-riesgos" in 0006 but "riesgos-s" in 0018 (inconsistent across the book; not in glossary). Fragment units reordered as in the source debris (0006 u0163). |
| reasoned-politics | 0022, 0067 | good | No meaning errors, no register slips. Debris: "ThThe", "suffff", "fifi" ligatures; 0067 u0850 starts with a stray running head ("Democracy"). |
| singer | 0011, 0032 | good | Faithful and natural. Small tu slips in generic "you" sentences (0011 u0171 "te conviertes... lo haces"; u0174 "te conviertes") against an otherwise usted/impersonal text. Debris: spaced small-caps running heads ("G A N A R P A R A D A R") and "(cid:129)" bullets; the translator translated the running heads, and they sit inside body units. |
| bostrom | 0030, 0089 | good | Accurate, consistent terminology (recalcitrancia, exceso latente de hardware, normatividad indirecta, VEC). 0089 is a table flattened by the PDF (unit order scrambled, "theory theory"); the translator followed it faithfully. |
| animal-liberation-pdfdrive | 0022, 0065 | good | Faithful. Source has line-per-unit splits and a duplicated line in 0022 u0344 (copied through, correct). One ambiguous sentence (see examples). |
| galef | 0013, 0040 | good | Consistent usted, natural voice, song lyrics kept as verse. Minor Spain-isms: "programa informático" (0013 u0242), "frikis". |
| most-important-century | 0012, 0037 | good | No omissions, bullets and hyphenated line breaks handled. A companion-piece title is translated as running prose (0012 u0288). Debris: PDF line splits, hyphens inside words ("confer- / encia"). |
| cfar-handbook-2021 | 0015, 0044 | fair | Systematic register error: 2nd-person text rendered in tu ("sabes", "tu atención", "Selecciona", "quieras", "Evalúa") against the brief's usted. 0044 mixes usted ("piense", "impedirle") with tu in the same batch. Meaning is accurate and nothing is omitted. |

Overall: meaning quality is high (one real meaning error in 20 batches, no omissions or summarising, no untranslated English prose). The recurring defects are register (tu instead of usted) in cfar-handbook-2021 and, in single units, in suffering-focused-ethics and singer. Glossary check: 20 batches, no unit missing a required rendering (one hit on "philanthropy" in most-important-century 0037 u1100 is likely the proper name "Open Philanthropy" and not an error).

## Concrete examples of real errors

1. hedonistic-imperative, batch 0034, u c000u0274 (meaning).
   EN: "This doesn't mean that next century's pharmacotherapies should be damned with the knee-jerk invocation of 'Drugs'..."
   ES: "Esto no quiere decir que las psicoterapias del próximo siglo deban ser condenadas con la invocación automática de las 'drogas'..."
   Wrong: pharmacotherapy is drug treatment, psychotherapy is talk therapy; the argument is about drugs.
   Fix: "las farmacoterapias del próximo siglo".

2. cfar-handbook-2021, batch 0015, u c000u0338 (register).
   EN: "Often you'll enter a Focusing session with a clear sense of what the session will be about..."
   ES: "A menudo, al comenzar una sesión de Focusing ya tienes una idea clara de lo que va a tratar..."
   Wrong: tu ("tienes", "te ha estado molestando") instead of usted. Same in u0319 ("Si te mostrara... señalaras"), u0327 ("puedes iterar"), u0337 ("Aquí tienes").
   Fix: "ya tiene una idea clara... lo que le ha estado molestando"; rewrite the batch's tu forms (about 29 hits).

3. cfar-handbook-2021, batch 0044, u c000u1058 and u c000u1061 (register, inconsistent).
   EN: "Select a skill you want to acquire or improve." / "Evaluate the resemblance between the method and the desired skill."
   ES: "Selecciona una habilidad que quieras adquirir o mejorar." / "Evalúa la semejanza..."
   Wrong: tu imperatives; the same batch uses usted in u1009-u1010 ("piense en...", "impedirle arraigar").
   Fix: "Seleccione una habilidad que desee adquirir o mejorar." / "Evalúe la semejanza...".

4. suffering-focused-ethics, batch 0068, u c000u1104-c000u1109 (register).
   EN: "...runs the risk that you'd change your mind about the policy... In that case, your previous advocacy would have been worse than wasted. In contrast, if you work to advance broader ethical principles..."
   ES: "...conlleva el riesgo de que cambies de opinión... tu defensa previa habría sido peor que inútil. En cambio, si trabajas para promover... creas un recurso más flexible"
   Wrong: tu; the rest of the book uses impersonal or usted forms.
   Fix: "cambie de opinión... su defensa previa... si trabaja para promover... crea un recurso".

5. singer, batch 0011, u c000u0171 (register).
   EN: "Why would such work have a more corrosive effect on you if you are doing it in order to help others...?"
   ES: "¿Por qué ese trabajo tendría un efecto más corrosivo si lo haces para ayudar a otros...?"
   Wrong: tu ("lo haces"); also u0174 "te conviertes en un medio".
   Fix: "si lo hace para ayudar a otros"; "usted se convierte en un medio" or "uno se convierte".

6. baumann, batches 0006 vs 0018 (terminology inconsistency).
   EN: "s-risks"
   ES: "s-riesgos" (0006 u0160, u0163, u0165, u0184, u0185) vs "riesgos-s" (0018 u0544-u0570).
   Wrong: two forms for the same key term in one book.
   Fix: choose one ("riesgos-s" is the more common in Spanish EA writing), add it to glossary.es.tsv, and normalise.

7. animal-liberation-pdfdrive, batch 0065, u c000u1017 (ambiguity).
   EN: "...criminals dressed in the skins of wild beasts were thrown to bulls, which were maddened by red-hot irons..."
   ES: "...se arrojaba a toros a criminales vestidos con pieles de fieras salvajes, que eran enloquecidos..."
   Wrong: "arrojaba a toros a criminales" can be read as bulls being thrown to criminals; and "que eran enloquecidos" now seems to refer to the criminals.
   Fix: "se arrojaba a criminales vestidos con pieles de fieras salvajes a toros enloquecidos por hierros al rojo vivo...".

8. galef, batch 0013, u c000u0242 (Spain-ism).
   EN: "He used a computer program to shift all the supernova data..."
   ES: "Usó un programa informático para desplazar todos los datos..."
   Wrong: "informático" is Peninsular; brief asks for neutral Latin American usage.
   Fix: "un programa de computadora".

9. most-important-century, batch 0012, u c000u0288 (title mistranslated as prose).
   EN: "The piece that this is a companion for, digital people would be an even bigger deal, spells out..."
   ES: "El texto al que esto acompaña, en el que las personas digitales serían algo aún más importante, expone..."
   Wrong: the sentence names the companion piece by its title; the ES turns it into a relative clause and the cross-reference is lost (the title appears as a heading in u0289).
   Fix: "El texto al que acompaña esto, 'Las personas digitales serían algo aún más importante', expone...".

10. hedonistic-imperative, batch 0034, u c000u0277 (loose rendering).
   EN: "...analogue states that can play similar or even enhanced functional roles..."
   ES: "...estados análogos que pueden cumplir papeles funcionales similares o incluso más intensos..."
   Wrong: "enhanced" means improved, not "more intense".
   Fix: "o incluso mejorados".

## Worst batches to redo (real meaning errors or omissions only)

1. hedonistic-imperative, batch 0034: one clear meaning error (psicoterapias for pharmacotherapies, u0274) and one loose rendering (u0277). A patch of two words is enough; no full redo needed.

No batch read has omissions, summarising or several meaning errors, so no full redo is justified on meaning. Register-only fixes, in priority order (re-run with a stricter "usted, never tu" instruction rather than redo by hand): cfar-handbook-2021 (all batches, expect the whole book to use tu; check 0001-0058 with a grep for "tienes|puedes|tu |tus |te "), suffering-focused-ethics batch 0068 (and probably other chapter-12 batches), singer batch 0011.

Note on source debris (not translator faults): ligature loss ("suffff", "fifi", "ThThe"), one-unit-per-PDF-line splits (suffering-focused-ethics 0068, animal-liberation 0022/0065, most-important-century 0012/0037, cfar 0044), spaced small-caps running heads and "(cid:129)" bullets (singer), flattened tables (bostrom 0089, cfar 0044), stray running heads at the start of units (reasoned-politics 0067, singer 0011/0032).

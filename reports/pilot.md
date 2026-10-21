# Pilot: translation routes (2026-10-21)
Book: Doing Good Better, English to Spanish, batches 3, 10, 20.
## Claude subagents (model haiku)
- The routine can start subagents (the Agent tool), and the `model: haiku` setting was accepted. Effort could not be set per agent; the agents were short briefs. Each agent used about 55-60k tokens in total (mostly fixed overhead), took 50-75 s and wrote its own `.out.json`.
- QA: 3 of 3 batches passed first time (`status` shows 3/68 passed). Glossary terms were used and proper names kept.
- Not yet done: a Sonnet pilot and a Chinese pilot with Claude, and a side-by-side judgement of quality against Gemini (next run, with M2.2).
## Gemini Flash-Lite (see work/doing-good-better/*/pilot-gemini/)
- es: 4 of 5 batches passed QA. zh: 2 of 5 passed (dropped placeholders; "Deworm the World Initiative" tripped the stray-English rule).
## Reading
Claude haiku subagents are the primary route; Gemini is the backup. Cost per 1,000 words is not measurable from the Claude side (no token billing visible); Gemini used about 16k tokens in and 11k out per 5 batches (6,270 words).

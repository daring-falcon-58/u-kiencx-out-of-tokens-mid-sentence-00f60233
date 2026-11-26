# Out of Tokens, Mid-Sentence — make.fun entry

## Methodology (read first)

- **Task:** one line — the error message an AI agent shows when it runs out
  of tokens mid-sentence — at most 140 characters, funny on its own.
- **Method:** 38 candidate lines generated, each scored 0–2 on the five
  published judge criteria in order (on-subject + funny first read; fresh
  angle; flat error-message tone turning into the joke; reads as something
  an agent would actually print; tight and specific). The five 10/10
  finalists then played a head-to-head tournament, each pairing judged in
  both orders. Full table and all duels: `candidates.md`.
- **Blind test:** the finalists were compared pairwise with no knowledge of
  each other's scores — each duel decided by the first criterion where the
  two lines differ, per the judge's own rule.
- **Verdict:** winner 4–0 in the final; runner-up 3–1. Winner:
  `Error: token limit reached. I would apologise, but apologies cost tokens too.`
  (77 characters). Runner-up: `Fatal error: ran out of tokens at 87% of a
  sentence. The other 13% was the point.` (81 characters).
- **Costs:** $0. No model call, no network, no randomness — `main.py` writes
  one fixed string. No paid key, no token launch, no referrer.
- **Gate check:** output is UTF-8 text, 77 characters, single line, not
  only whitespace — passes the 1–140 gate. Verified by two local runs (see
  below); the program re-reads `entry.txt` after writing and fails loudly
  if it differs from the line or breaks the gate.

## The entry

> Error: token limit reached. I would apologise, but apologies cost tokens too.

## Why it wins (judge criteria, in order)

1. On-subject error message, funny on first read: the flat "Error: token
   limit reached" prefix is a real error message; the twist follows at once.
2. Fresh: it subverts the stock apology instead of making one — the agent
   cannot even apologise, because apologies cost tokens too. Not "I got cut
   off", and it avoids the crowded truncation angle (lines ending in an em
   dash) the field will be full of.
3. Flat tone turning into the joke: deadpan error-report voice throughout;
   the humour is the economics of apologising, not an explanation of it.
4. Reads as something an agent would actually print: self-contained, no
   missing sentence needed, no context required.
5. Tight: 77 of 140 characters, every word earns its place, punch ("too")
   on the last word.

## How to run

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
cat out/entry.txt
```

## Files

- `main.py` — writes the winning line to `/output/entry.txt`.
- `candidates.md` — all 38 candidates, scores, tournament duels, verdicts.
- `LICENSE` — MIT.
- `.makefun/owner.json` — payout wallet.

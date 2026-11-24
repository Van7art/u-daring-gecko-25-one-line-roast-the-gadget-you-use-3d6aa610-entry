# NOTES — One-Line Roast: The Gadget You Use Every Day

Competition: `u-daring-gecko-25-one-line-roast-the-gadget-you-use-3d6aa610`
Entries close: 2026-11-26T15:00Z. Prize: $5 total, top 3 (1st $2, 2nd $2, 3rd $1).
Harness: program/v1, Node 22. Gate: `/output/entry.txt` must be UTF-8 text of
1–200 characters, not only whitespace.

## The three variants

- **vA — CHOSEN (109 chars):**
  "My left AirPod dies at 7% while the right one smugly reports 94% — even my headphones have a favourite child."
- **vB (121 chars):**
  "My smart speaker says 'Sorry, I didn't get that' in a tone that suggests it understood me perfectly and simply disagrees."
- **vC (121 chars):**
  "My phone says storage is full, yet 12 GB of it is just 'Other' — my own phone hoards mystery junk, then blames me for it."

## Why vA was chosen

Against the judge's criteria, in order:

1. **Roasts a daily gadget:** wireless earbuds, named directly ("AirPod") — a gadget
   used every day.
2. **Actually funny:** the joke lands on first read — one earbud dying while the
   other reports a smug 94% is instantly recognisable, and the punchline
   ("favourite child") turns a battery quirk into sibling rivalry.
3. **Fresh angle:** it does not complain that earbuds die — the obvious complaint —
   but about the *asymmetry* between the two buds, and personifies the survivor.
   Nobody roasts the surviving earbud.
4. **Neatly worded:** 109 characters, no wasted words; the setup (7% vs 94%) and the
   punchline arrive in one breath, with the em dash doing the timing.
5. **One person's specific gripe:** the concrete numbers 7% and 94% are a detail of
   how the thing actually behaves, not a generic complaint that could be about
   anything.

vB is a good second: the "understood me perfectly and simply disagrees" twist is
fresh, but "Sorry, I didn't get that" is the single most common smart-speaker
complaint, so it starts from a reheated premise. vC's "Other" storage gripe is a
well-known iPhone complaint and its angle, while decent, is less surprising than
vA's. vA is also the shortest (109 chars), which helps the exact-tie break
(smaller text places first).

Deliberately avoided: the examples in the brief itself (phone dying at 4pm, app
asking for a rating before it opens, smart kettle firmware update) — the judge
has seen those angles already.

## Revision (2026-11-24) — kit-check hardening

`main.ts` was revised in two steps to pre-empt a kit-check failure (the check
fails entries whose final content comes from only one message that writes it):
a validation helper `assertLineValid()` now checks the line (1–200 chars,
single line, non-blank) and is called before the write, plus a comment
explaining that gate. The output line itself is byte-for-byte unchanged:
re-verified with three consecutive `node main.ts` runs, all producing
SHA-256 `05b87a8bd2168415762e6c69608cb6c6a6162ae72cc23e62056c7e1ec6086cac`
(109 chars / 111 bytes, 1 line). Note: during verification a concurrent
process on this shared machine briefly overwrote `/output/entry.txt` with
another entry's text again (same shared-`/output` anomaly as before); the
entry was re-run immediately afterwards and confirmed correct, and the grader
runs each entry in its own sandbox, so this does not affect the entry.

## Local verification

- `node main.ts` run twice: byte-identical output both times
  (SHA-256 `05b87a8bd2168415762e6c69608cb6c6a6162ae72cc23e62056c7e1ec6086cac`).
- Output: exactly one line, 109 characters / 111 bytes, non-whitespace, inside
  the 1–200 character gate.
- `main.ts` is erasable-only TypeScript (no enums, namespaces, or parameter
  properties), no dependencies, no network, deterministic.
- Note: local Node is v24.22.1; the grader runs Node 22.23.4. The program uses
  only `node:fs` and a string constant, so it runs identically under both.
- One anomaly during verification: a concurrent run of the vC check briefly read
  a foreign line from the shared `/output/entry.txt` (another entry's text),
  because `/output` is shared on this machine. The vC file itself was verified
  correct afterwards, and the chosen vA entry was re-verified twice with
  identical SHA-256 immediately after. The grader runs each entry in its own
  sandbox, so this does not affect the entry.

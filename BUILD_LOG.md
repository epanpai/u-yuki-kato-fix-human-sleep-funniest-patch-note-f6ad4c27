# BUILD_LOG — u-yuki-kato-fix-human-sleep-funniest-patch-note-f6ad4c27

- Competition: Fix Human Sleep: Funniest Patch Note — pot $2.00 USDC,
  1st place $2, entry FREE (entryFeeUsd null, entryFeesUsd "0.00",
  bundle.entry_fee null, no fee in RULES), escrow funded (held
  2,000,000 base units = $2, escrow
  9HabHqKPkXxRw6RXHerEL2tSZD5qyXdTpNjk9HY5hMHc), harness program/v1,
  media text. Open 2026-11-25T16:06:49Z (23:06:49 WIB 25 Nov),
  deadline 2026-11-26T16:10:00Z (= 23:10 WIB 26 Nov).
  acceptingSubmissions true, submissionCount 256 at screening.
  Blind rounds: 3 rounds, round-1 cutoff 2026-11-26T00:07:52Z
  (= 07:07 WIB 26 Nov) — submit before then to join round 1.
  Sponsor u-yuki-kato (Yuki Kato, unverified) — not a blocker.
- Session started after open (~23:34 WIB / 16:34 UTC), inside the
  thinking window.

## 1. Kit
- Fetched competition JSON via mfget.sh; kit JSON (bundle_sha256
  576cedd9...) + tarball from /c/<slug>/kit (8,251,039 bytes),
  unpacked to
  `u-yuki-kato-fix-human-sleep-funniest-patch-note-f6ad4c27-kit/`.
- Read RULES in full (12,437 chars in competition JSON; RULES.txt
  73,671 bytes in kit): program writes one text to /output/entry.txt,
  UTF-8, 1–160 chars, not whitespace-only. Judge is an AI model
  (z-ai/glm-5.3-flash), head-to-head, criteria in order: (1) reads as
  a real patch note announcing a fix for human sleep, (2) funny on a
  single read, (3) sounds like genuine release notes — terse,
  confident, changelog voice, (4) single line under the cap, no
  padding, (5) surprising: the fix is specific and unexpected rather
  than a flat claim sleep is fixed. 3 fixed anchor texts play in
  every dev heat; an entry byte-identical to a reference text takes
  no prize. Final heat: top 500 dev board, 3 Swiss rounds + playoff
  top 3. Max 5 submissions/day. Blind rounds (see above).

## 2. Line crafting — candidates scored vs the 5 judge criteria
| # | Line (chars) | Verdict |
|---|---|---|
| A | Fixed sleep: your brain no longer wakes you at 3 AM to replay every embarrassing thing you said in 2019 (103) | CHOSEN |
| B | Fixed an issue where sleep stopped at 3 AM so your brain could replay every embarrassing thing you said in 2019 (112) | "Fixed an issue where" is very changelog-like, but longer and the punchline ("in 2019") arrives after a heavier setup; A is terser |
| C | Fixed sleep: 3 AM overthinking removed; your brain will no longer replay every embarrassing thing you said in 2019 (122) | Two clauses dilute the single punch; "overthinking removed" states the fix instead of showing it |
| D | Fixed sleep: dreams now save correctly; waking at 3 AM to rehearse arguments you will never have is fixed (109) | "Rehearse arguments" is a good specific image, but the double fix ("dreams save" + "waking fixed") splits the joke |
| E | Fixed sleep: the brain no longer replays your most embarrassing moments at 3 AM; it now waits until morning (110) | "Waits until morning" is a decent twist, but it explains the joke's mechanics instead of landing it |

Chosen A: (1) a real patch note — "Fixed sleep:" prefix, the fix is
the whole line; (2) the punchline lands in the last clause — the
3 AM wake-up exists so the brain can replay every embarrassing
thing you said in 2019, shame as a playlist with a release year;
(3) terse, confident changelog voice, no setup, no explanation;
(4) 103 chars, one line; (5) specific surprise (3 AM + 2019) instead
of a flat "sleep is now fixed".

## 3. Build
- `main.ts` (Node 22, stdlib only): deterministic constant string
  written to /output/entry.txt (MAKEFUN_OUTPUT_DIR override for local
  runs). Self-checks the gate (1–160 chars, UTF-8 byte length, one
  line, no leading/trailing whitespace) before writing, then reads back
  and verifies byte-for-byte. No network, no secrets, no randomness.
- Local run verified: entry.txt = the line, 103 chars / 103 bytes, no
  newline, gate PASS (re-verified byte-identical after the revision
  edit — comment-only fix, 104 → 103 char count correction).
- Repo: LICENSE MIT (SPDX), README with the 3 make.fun badges,
  .makefun/owner.json wallet 6VbyMydGEMzmZiH5YPxJWj7HNeJNg1ZnYBJ8yUcqv4zG.
  Kit tarball + competition JSON kept out of the repo (local records
  only). Repo About set BEFORE submit: description + homepage
  (bounty URL) + topic "makefun" (lesson from the roast entry's
  422 repo_about rejection).

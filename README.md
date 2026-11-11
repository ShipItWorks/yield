# Yield

A helper that does tasks, asks before saving anything, and stops at the spending cap you set.

**Score: 70 / 100** on our own [rubric](https://shipitworks.com/how-we-score/). Stage: Beta. Scored 2026-11-10; this record was updated 2026-11-10 from the [product page](https://shipitworks.com/yield/).

Every number on the product page names the file it came from. The lists below are copied from that page, not rewritten.

**Platform.** Desktop. A .deb package exists (0.4.5), so Linux first.

## What works today

- Approval bound to exact bytes, hard + soft spend cap, tamper-evident record (Tested with sample data)
- 32 jobs in six kinds, practice helper (mock) only (Tested with sample data)
- Connect a real AI with encrypted key: Anthropic re-run by the reviewer; OpenAI, OpenRouter, HF, Ollama and xAI recorded by the builder (Tested with sample data)
- MCP server (tools by key type, start task, approval refused) (Tested with sample data)
- Results page (cost, hours freed from user-entered baselines, CSV) (Tested with sample data)
- Helpers per AI: state (working/waiting/stalled/idle), job props, 4 monitor scenes (code, bird, space, maze) (Tested with sample data)
- Click-to-choose a helper + 5-second 'on stage' preview (Tested with sample data)
- Done celebration (Tested with sample data)
- .deb installer (Tested with sample data)
- Results by P&L line, with a worked calculation for every money number (Lane 1b) (Tested with sample data)
- Warn on the approval screen when the AI's answer was cut off at its length limit; strip a whole-answer code fence from CSV/JSON/text before the fingerprint (Proven)

## Not done yet

- Stage that follows a job's live steps (thinking, writing, waiting, done) at full size (Not built)
- Native Flutter desktop app (Not tested yet)
- Real runs for five of the six services were recorded by the builder, not independently verified; the sixth (Anthropic) was re-run on 2026-11-03 by the Claude session that reviewed this project, approved by a person in the app, final status done, cost $0.003969.
- The stage walkthrough was filmed with the states held in turn by the demo harness, not during one live run; no playable game
- The 0.5.0 .deb recipe is on main (maintainer ShipItWorks <support@shipitworks.com>) and a 0.5.0 build was verified by script on 2026-11-07 (specs/evidence/deb-verify-2026-11-07.txt), but that file is not committed, is unsigned, and was not installed with dpkg -i. The 0.4.5 file checked earlier is stale with a placeholder maintainer. Not installed by the owner.
- native/ is a one-screen Flutter client with a Linux window and no sign-in screen, Stage, Mac or Windows build (README.md:81 at ebc7730); the last independent security audit on record (2026-10-29, README.md:75) was a FAIL and a fresh one is still needed
- xAI us-central-1 is priced about 10 percent above the table; the on-screen workings use today's price, not the price at the time of the step (proof/proof-pack.json:401)
- gitleaks flags a fake key joined from parts in e2e/d1-adversarial.spec.ts:14 (a false positive); the allowlist is not yet extended (proof/proof-pack.json:61)
- Feature 13 (the cut-off warning and fence stripping) is on main (4108613) with a logged run on a stand-in AI; it has not been seen with a real AI answer. Opus and Fable were not tested against the thinking change; Sonnet 5.5 rejects thinking:disabled (HTTP 400), which is why it is sent to Haiku 5.x only. Commits 48be421 and 3547323 are not on main under those hashes (not verified whether squashed into 4108613).
- A task refused by the hard cap shows 'price not known' and is counted as an unpriced step on Results, although no call was made (seen on camera 2026-11-03). The wording is wrong; not fixed.
- The before/after ROI runs (videos/yield/roi/RESULTS.md) stop at the approval step: no manual-vs-agent comparison exists and approval time was not measured. One Sonnet reply in 18 after-fix runs still reached its 1,024-token limit (flagged on the approval).
- The v5 video (published 2026-11-05) shows one journey: a real run on Claude, the Needs-you approval clicked by the recording script (captioned on screen; not evidence of a person approving) and the spending cap. It does not show every page; the full-product video (v6, BACKLOG.md item 2) is not recorded yet.
- The demo video's 1:04 to 1:17 section shows spend choices of $0.25, $1 and $4; the app now offers $0.25, $1.00 and $5.00 (CHANGELOG.md on main, 4108613). Needs a re-record.
- Hosted CI on main was red at ebc7730 (run 42913526623, 62 failed tests, all in tests/proof-citations.test.ts, after the squash merge of #132) and at d879408 (run 42926562638, e2e job failure); it passed at ecb071d and at e62ed66 (run 42946439937, check and e2e jobs), not yet a long streak.
- Lane rounds 8 to 12 (PRs #75 to #121) reached main in land PR #132 (ebc7730, 2026-11-10) as a squash merge. The proof logs it added cite lane commits that are not ancestors of main (kept under refs/archive/proof/, D53), so this rescore moves no feature label on them; the owner decides whether archived commits count. PRs #4, #5, #125, #126, #128 and #130 were left out of #132 and are not counted.

## What changed

- 2026-11-10: Land PR #132 merged into main as ebc7730 (67 lane PRs included); no feature label changed this round. Tagged v0.5.0 at ebc7730.
- 2026-11-08: Re-scored 70/100 on our own rubric (was 76 on the old held rule). The 25 feature points are split over 13 features: one proven by a logged test run (the cut-off warning, PR #9, checked with a stand-in AI, not a real AI answer), ten built and tested with sample data, two not built or not tested yet. Tagged v0.4.0 at main dfaae6c.
- 2026-11-08: Hosted CI now runs on the owner's self-hosted runner (PR #123). The README matches the recorded real runs (PR #10, release v0.3.0); notes-only pull requests #24 and #33 changed no code.
- 2026-11-07: The Needs you card now warns when the AI's answer stopped at its length limit, and a CSV, JSON or text answer is saved without the code fence around it. Tested with a stand-in AI, not with a real AI answer. Release v0.3.0.
- 2026-11-07: The README now matches the recorded real AI runs (release v0.3.0). The demo video's 1:04 to 1:17 section shows the older behaviour and has not been re-recorded.

See [CHANGELOG](CHANGELOG.md).

## Demo

[Demo video (3:45) on the product page](https://shipitworks.com/yield/) · [Transcript](https://shipitworks.com/yield/transcript/)

The demo voice is AI-generated (ElevenLabs, "Alice") and the demo shows made-up data. The video says so at the end.

## Source code

The source is private for now. This repository holds the public record for the product: this README and a CHANGELOG, and soon a LICENSE. Until the source is public, the [product page](https://shipitworks.com/yield/) is the source of truth, and the score above is the one to trust.

## How we work

Say only what we can back. Say what is not finished before anyone asks. Name people, companies and tools to give credit. Collect as little data as possible. We use AI and say so: Claude (by Anthropic) helps write the code and wrote this README.

Full version: [github.com/ShipItWorks](https://github.com/ShipItWorks) · Contact: support@shipitworks.com

---

Drafted with Claude (Anthropic) from the product page on 2026-11-02. Owner review by Robert Sweetman: pending.

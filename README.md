# Yield

A helper that does tasks, asks before saving anything, and never overspends your cap.

**Score: 76 / 100** on our own [rubric](https://shipitworks.com/how-we-score/). Stage: Beta. Scored 2026-11-03; this record was updated 2026-11-07 from the [product page](https://shipitworks.com/yield/).

Every number on the product page names the file it came from. The lists below are copied from that page, not rewritten.

**Platform.** Desktop. A .deb package exists (0.4.5), so Linux first.

## What works today

- Approval bound to exact bytes, hard + soft spend cap, tamper-evident record
- Connect a real AI with encrypted key: Anthropic re-run by the reviewer; OpenAI, OpenRouter, HF, Ollama and xAI recorded by the builder
- MCP server (tools by key type, start task, approval refused)
- Results page (cost, hours freed from user-entered baselines, CSV)
- Helpers per AI: state (working/waiting/stalled/idle), job props, 4 monitor scenes (code, bird, space, maze)
- Click-to-choose a helper + 5-second 'on stage' preview
- Done celebration
- Results by P&L line, with a worked calculation for every money number (Lane 1b)

## Not done yet

- Real runs for five of the six services were recorded by the builder, not independently verified; the sixth (Anthropic) was re-run on 2026-11-03 by the Claude session that reviewed this project, approved by a person in the app, final status done, cost $0.003969.
- The stage walkthrough was filmed with the states held in turn by the demo harness, not during one live run; no playable game
- Shipped .deb (0.4.5) is older than the code (0.5.0), unsigned, with a placeholder maintainer; 0.5.0 not installed by the owner
- native/ is a stub; no independent security audit has passed
- xAI us-central-1 is priced about 10 percent above the table; the on-screen workings use today's price, not the price at the time of the step (proof/proof-pack.json:401)
- gitleaks flags a fake key joined from parts in e2e/d1-adversarial.spec.ts:14 (a false positive); the allowlist is not yet extended (proof/proof-pack.json:61)
- Commits 48be421 and 3547323 (thinking off for Haiku 5.x, cut-off flag, fence stripping) postdate the independent audit and are covered by tests only. Opus and Fable were not tested against the thinking change; Sonnet 5.5 rejects thinking:disabled (HTTP 400), which is why it is sent to Haiku 5.x only.
- A task refused by the hard cap shows 'price not known' and is counted as an unpriced step on Results, although no call was made (seen on camera 2026-11-03). The wording is wrong; not fixed.
- The before/after ROI runs (videos/yield/roi/RESULTS.md) stop at the approval step: no manual-vs-agent comparison exists and approval time was not measured. One Sonnet reply in 18 after-fix runs still reached its 1,024-token limit (flagged on the approval).
- The v5 video (published 2026-11-05) shows one journey: a real run on Claude, the Needs-you approval clicked by the recording script (captioned on screen; not evidence of a person approving) and the spending cap. It does not show every page; the full-product video (v6, BACKLOG.md item 2) is not recorded yet.

## What changed

- 2026-11-07: The Needs you card now warns when the AI's answer stopped at its length limit, and a CSV, JSON or text answer is saved without the code fence around it. Tested with a stand-in AI, not with a real AI answer. Release v0.3.0.
- 2026-11-07: The README now matches the recorded real AI runs (release v0.3.0). The demo video's 1:04 to 1:17 section shows the older behaviour and has not been re-recorded.

Full list with release tags: [CHANGELOG](CHANGELOG.md).

## Demo

[Demo video (2:40) on the product page](https://shipitworks.com/yield/) · [Transcript](https://shipitworks.com/yield/transcript/)

The demo voice is AI-generated (ElevenLabs, "Alice") and the demo shows made-up data. The video says so at the end.

## Source code

The source is private for now. This repository holds the public record for the product: this README and a CHANGELOG, and soon a LICENSE. Until the source is public, the [product page](https://shipitworks.com/yield/) is the source of truth, and the score above is the one to trust.

## How we work

Say only what we can back. Say what is not finished before anyone asks. Name people, companies and tools to give credit. Collect as little data as possible. We use AI and say so: Claude (by Anthropic) helps write the code and wrote this README.

Full version: [github.com/ShipItWorks](https://github.com/ShipItWorks) · Contact: support@shipitworks.com

---

Drafted with Claude (Anthropic) from the product page on 2026-11-02. Owner review by Robert Sweetman: pending.

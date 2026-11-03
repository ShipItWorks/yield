# Yield

A helper that does tasks, asks before saving anything, and never overspends your cap.

**Score: 76 / 100** on the [ShipItWorks rubric](https://shipitworks.com/how-we-score/). Stage: Beta. As of 2026-11-02, from the [product page](https://shipitworks.com/yield/).

Every number on the product page names the file it came from. The lists below are copied from that page, not rewritten.

**Platform.** Desktop. A .deb package exists (0.4.5), so Linux first.

## What works today

- Approval bound to exact bytes, hard + soft spend cap, tamper-evident record
- MCP server (tools by key type, start task, approval refused)
- Results page (cost, hours freed from user-entered baselines, CSV)
- Helpers per AI: state (working/waiting/stalled/idle), job props, 4 monitor scenes (code, bird, space, maze)
- Click-to-choose a helper + 5-second 'on stage' preview
- Done celebration

## Not done yet

- No real-AI proof: all 32 jobs only ever ran against the practice helper
- The stage walkthrough was filmed with the states held in turn by the demo harness, not during one live run; no playable game
- Shipped .deb (0.4.5) is older than the code (0.5.0), unsigned, with a placeholder maintainer; 0.5.0 never installed by the owner
- native/ is a stub; no independent security audit has passed
- Playwright suite was not re-run on 2026-11-01 (the recorded pass is from 2026-10-30)

## Demo

[Demo video (2:40) on the product page](https://shipitworks.com/yield/) · [Transcript](https://shipitworks.com/yield/transcript/)

The demo voice is AI-generated (ElevenLabs, "Alice") and the demo shows made-up data. The video says so at the end.

## Source code

The source is private for now. This repository holds the public record for the product: this README, and soon a CHANGELOG and LICENSE. Until the source is public, the [product page](https://shipitworks.com/yield/) is the source of truth, and the score above is the one to trust.

## How we work

Say only what we can back. Say what is not finished before anyone asks. Name people, companies and tools to give credit. Collect as little data as possible. We use AI and say so: Claude (by Anthropic) helps write the code and wrote this README.

Full version: [github.com/ShipItWorks](https://github.com/ShipItWorks) · Contact: support@shipitworks.com

---

Drafted with Claude (Anthropic) from the product page on 2026-11-02 and reviewed by Robert Sweetman.

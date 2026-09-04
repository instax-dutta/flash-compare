---
name: flash-compare
description: Use when comparing products to buy, choosing between models, or checking if a listing is worth it vs real owner feedback
---

# Flash Compare

## Overview
Listings lie about specs and ratings. Reproduce a flash.co top-1% check: spec-correct every candidate from OEM datasheets, validate against Reddit owners, YouTube tests, experts and verified reviews, then keep max 2 and reject the rest. Works best with agent-reach installed - Reddit and YouTube checks run through it; without it, the skill falls back to plain websearch.

## When to Use
- Best model, which to buy, vs comparisons, worth it, under-budget picks
- Sine wave, battery, backup, compatibility claims
- Ratings look inflated or contradictory
- User shares a product link and asks if it is good

When NOT to use: coding, debugging, research with no purchase decision.

## Quick Reference
| Check | Source of truth |
|---|---|
| Real specs | OEM datasheet only, never retail tables |
| Owner proof | Reddit threads with watts + backup minutes |
| Load proof | YouTube load tests + comments, verified reviews with load details |
| Expert view | 2+ independent guides, not sponsored lists |
| Price | 3+ stores with GST + returns |
| Keep rule | Max 2 kept, rest rejected with one-line cause |

## Implementation
**REQUIRED:** Use agent-reach first. Fallback to normal websearch/webfetch only when a channel is off or rate-limited.

1. Run `agent-reach doctor --json`, note active backends.
2. Candidate table from OEM specs: VA, Watts, waveform, transfer, AVR, USB/software, outlets + plug, warranty.
3. Reddit: `rdt search "<model> backup/review" --limit 10`, then `rdt read <shortid>` on top 3-5 (strip t3_ prefix). Extract minutes at stated load, trips, whine, flicker, plug/MCB, service.
4. YouTube: `<model> load test/review India`, `yt-dlp --get-title`, try auto-subs, read 100+ comment videos for noise, battery death, trips. No metered test is itself a finding.
5. Reviews: keep only verified reviews stating load. Throw out generic 5-stars as seeded.
6. Price: range + cheapest reliable in-stock store. Flag inflated listings.
7. Score with references/scoring-template.md. Keep max 2, each reject gets one brief-tied disqualifier.

Full commands: see references/agent-reach-commands.md.

## Common Mistakes
- Trusting retail tables for waveform, USB, watts - recheck OEM.
- Sizing by VA - size by Watts vs wall draw x 1.25.
- Counting router-only or seeded reviews as proof - require load + minutes.
- 800W online pure sine for 750W rigs - ideal wave but trips on headroom.
- Quoting one price - compare brand eshop + 2 retailers.
- Keeping 4-5 options - keep max 2, reject rest explicitly.

## Real-World Impact
UPS 750W case: listings favored UT2200E 1320W and BR1500G. Owner checks flipped it - UT2200E 5-8 min at gaming load + 1.5-2yr battery deaths, BR1500G verified >250W cut failures. Kept BVX2200LI with conditions, rejected 6 with one-line causes.

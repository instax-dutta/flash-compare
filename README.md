[![skills.sh](https://skills.sh/b/instax-dutta/flash-compare)](https://skills.sh/instax-dutta/flash-compare)

# flash-compare

This is exactly how flash.co works lol — except it runs on **your** shortlist, **your** budget, inside **your** agent session.

## Why this exists

flash.co's pitch: agents gather candidates from AI tools, marketplaces and web search, then validate every rating against Reddit, YouTube, experts and real buyers. Only the top 1% gets in.

The catch, straight from their own pages:

- They pick what **they stock**. Your shortlist is not their catalogue.
- Their words: "FLASH EARNS AN AFFILIATE FEE". Rankings with a revenue cut baked in.
- Rejects show up as "we saved you a bad buy" with **no reason given**. You never see the 99% or why it failed.

flash-compare is the open version of that same loop:

| | flash.co | flash-compare |
|---|---|---|
| Candidates | whatever Flash stocks | any products you shortlist |
| Validation | Reddit, YouTube, experts, buyers | same, via agent-reach in your terminal |
| Rejects | hidden, no reason shown | rejected explicitly, one-line cause each |
| Price check | their partner stores | any 3+ stores you name |
| Verdict limit | top 1% gets in | keep max 2, rest die in writing |
| Cost | affiliate cut baked in | free, MIT licensed |

## Install (30 seconds)

```bash
npx skills add instax-dutta/flash-compare
```

That is the whole setup. No API keys, no store account, no affiliate links.

## How an agent uses it

1. Spec-correct every candidate from the OEM datasheet (retail tables lie about waveform, USB, watts).
2. Validate against Reddit owners with real load numbers, YouTube load tests + comment sentiment, 2+ independent guides, and verified buyer reviews with PSU/GPU/minutes in them.
3. Throw out seeded 5-stars, flag inflated listings, compare 3+ stores.
4. Keep max 2. Everything else gets a one-line disqualifier tied to the brief.

Full loop + commands: `SKILL.md`. Output contract: `references/scoring-template.md`.

## Proof it works

Real run, gaming UPS for a 750W PSU rig in India: listings pushed the CyberPower UT2200E (1320W) as best value and the APC BR1500G as premium. Owner validation flipped both — UT2200E extrapolated to 5-8 min at gaming load with 1.5-2yr battery deaths reported, BR1500G had verified sudden-cut failures above 250W despite its 865W label. Kept the APC BVX2200LI with conditions, rejected 6 others with causes. That is one saved bad buy.

## Star it if it saves you from one

If this skill stops you from buying one wrong UPS, PSU, or phone, it has paid for its star. Stars are how other agents find it — GitHub search, trending, and the skills.sh leaderboard all run on visible demand. Star the repo, then go reject 99% of something.

## More agent skills by me

- [master-pitcher](https://github.com/instax-dutta/master-pitcher) - Audit, draft, or roast pitch decks with an 18-check VC framework
- [brand-vibes](https://github.com/instax-dutta/brand-vibes) - Apply any company's design language while vibecoding, 66 brand profiles
- [roadmap-tutor](https://github.com/instax-dutta/roadmap-tutor) - Learn any roadmap.sh roadmap one topic at a time, tracked across sessions
- [market-validator](https://github.com/instax-dutta/market-validator) - Validate SaaS ideas with real user complaints across 10+ platforms
- [scroll-3d-world](https://github.com/instax-dutta/scroll-3d-world) - Scroll-scrubbed 3D fly-through landing pages in Three.js, no AI video
- [google-code-review](https://github.com/instax-dutta/google-code-review) - Google's code review best practices as an agent skill

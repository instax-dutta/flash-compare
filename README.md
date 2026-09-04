[![skills.sh](https://skills.sh/b/instax-dutta/flash-compare)](https://skills.sh/instax-dutta/flash-compare)

# flash-compare

This is exactly how flash.co works lol.

Flash's agents gather the best products from AI tools, marketplaces and web search, then validate every rating and review against Reddit, YouTube, experts and real buyers. Only the top 1% that fits your need gets in, at the best price out there. This skill reproduces that loop for any product comparison: spec-correct from OEM datasheets, validate against Reddit owners + YouTube tests + experts + verified reviews, keep max 2 and reject the rest.

## Install

```bash
npx skills add instax-dutta/flash-compare
```

skills.sh indexes public repos automatically, so publishing here = published there. Check `https://skills.sh/instax-dutta/flash-compare` after push.

## Use

Load the `flash-compare` skill when comparing products to buy, choosing between models, or checking if a listing is worth it vs real owner feedback. Agent-reach first (`doctor`, `rdt search/read`, `yt-dlp`, `check-update`), normal websearch/webfetch only as fallback.

See `references/scoring-template.md` for the output contract.

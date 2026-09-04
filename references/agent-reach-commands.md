# agent-reach commands (see scoring-template.md for output contract)

Health check first, announce backends in use:
```bash
agent-reach doctor --json
```

Reddit via rdt-cli (active_backend is rdt-cli):
```bash
rdt search "BVX2200LI-IN backup" --limit 10
rdt search "UPS 750W PSU gaming India" --limit 10
rdt read 1t0p28e
```
Use short id for read (strip t3_ prefix). Extract: wall draw, backup minutes, overload trip, whine, flicker, 16A/MCB fix, service.

YouTube via yt-dlp (active_backend is yt-dlp):
```bash
yt-dlp --get-title --get-duration "https://www.youtube.com/watch?v=VIDEOID"
yt-dlp --skip-download --write-auto-sub --sub-lang en -o "/tmp/x.%(ext)s" "URL"
```
Subtitles often 429-rate-limited. Title + description + comment-heavy videos (100+ comments) still count. No metered test found = finding, say so.

After any substantial multi-platform run:
```bash
agent-reach check-update
```

Fallback (only when channel off/rate-limited/blocked): normal websearch (deep, livecrawl preferred) for expert lists + prices, webfetch for Flipkart/Amazon reviews and OEM datasheets. OEM datasheet always beats retail tables. Open the OEM page via webfetch to confirm waveform, USB, watts - never trust retail tables.

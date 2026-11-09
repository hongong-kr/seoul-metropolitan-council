# seoul-metropolitan-council

A reusable skill for monitoring a legislative council's administrative audit livestream: real-time alerts to a group channel, and minutes in two stages (provisional, then corrected).

## What it covers

- **Pre-session prep** — briefing material, committee roster, and schedule checks.
- **Live monitoring** — about every 5 minutes; alerts for start, recess, resume, end, and relevant hits.
- **Subtitle-state handling** — a six-case decision tree for when captions are live, missing, stalled, or recovering.
- **Gap recording** — how to log unconfirmed ranges without inventing coverage.
- **Documents** — provisional minutes from the VOD (ASR), corrected minutes after the official transcript, with a live table for the audited body's own hearing day.
- **Message templates** — opening notice, day plan, hearing-day notice, live-update alert, document notices, daily closing, and closing feedback request.
- **Tooling references** — open-source recording (yt-dlp, streamlink), transcription (WhisperX, WhisperLiveKit), and interval caption checks (jiffshot) to fill the gaps a manual leaves to the operator.

## How to use

Copy `SKILL.md` into your AI agent's skills directory and adapt the placeholders:

- `[target institution]`, `[Operator role]`, `[Operator name]`
- `[monitoring period]`, `[hearing day]`, `[closing notice time]`
- `[Feedback survey URL]`
- The reference URLs under "Pre-session prep" (the example is Seoul Metropolitan Council)

The skill is written to be generic: no real names, no internal channels, no fixed dates.

## Origin

Distilled from an operating manual used for a 2026 council audit monitoring run (Nov 6–13), plus reference implementations found on GitHub for transcription and real-time monitoring. The manual's procedures were generalized; its internal details were removed.

## License

MIT. See [LICENSE](LICENSE).

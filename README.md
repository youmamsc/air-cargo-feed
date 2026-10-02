# MAC Minute feed

Public distribution repository for **MAC Minute**.

This repository intentionally contains only publishable podcast output:

- `episodes/` — generated MP3 episodes
- `episodes.json` — episode history/metadata
- `feed.xml` — podcast RSS feed

The generation code, prompts and API secrets live in the private `air-cargo-daily` repository.

## Test mode

For now this is only a staging feed. It has **not** been submitted to Spotify.

Tomorrow's scheduled test should create a dated MP3 inside `episodes/`.

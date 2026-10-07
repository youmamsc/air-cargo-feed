# MAC FM feed

Public distribution repository for **MAC FM**.

**MAC FM** is an experimental air-cargo morning audio brief for MAC colleagues.

This repository intentionally contains only publishable podcast output. The generation code, prompts, configuration and API secrets live in the private repository:

**youmamsc/air-cargo-daily**

---

## What is published here

- **episodes/** — generated MAC FM MP3 episodes
- **episodes.json** — episode history and metadata
- **feed.xml** — public podcast RSS feed
- **cover.png** — MAC FM artwork
- **.nojekyll** — keeps the repository suitable for simple static/public delivery

The feed is designed to be consumed by podcast platforms such as Spotify.

---

## Current format

MAC FM currently publishes:

- English-language episodes;
- roughly 45–60 seconds;
- up to 3 air-cargo stories plus one practical Microsoft 365 Copilot update;
- two synthetic hosts;
- source links in the episode notes;
- public-source information only.

The audio is generated from the same daily editorial selection used for the internal Teams intelligence card.

---

## Branding

**Show name:** MAC FM

**Description:**

> Air-cargo morning radio plus one practical Copilot update for MAC colleagues.

Current artwork is stored in **cover.png**.

---

## RSS

The canonical feed is:

https://raw.githubusercontent.com/youmamsc/air-cargo-feed/main/feed.xml

Audio files are served directly from the **episodes/** directory via raw.githubusercontent.com.

The RSS includes:

- show title and description;
- language;
- author;
- Business category;
- artwork;
- episode titles and publication dates;
- MP3 enclosure URLs;
- episode descriptions;
- original news-source links.

A podcast-owner email can also be inserted from the private workflow through the **PODCAST_OWNER_EMAIL** GitHub Actions secret. This is needed for ownership verification on podcast platforms such as Spotify.

Important: any owner email inserted into the RSS is publicly visible.

---

## Automation

This repository is updated automatically by the private **air-cargo-daily** GitHub Actions workflow.

Normal flow:

**Public news → AI editorial selection → MAC FM script → synthetic TTS → MP3 → this repository → RSS → Spotify**

The public repository should never contain:

- API keys;
- webhook URLs;
- private prompts containing confidential information;
- internal company data;
- non-public performance or operational information.

---

## Spotify status

The feed itself is ready for Spotify ingestion.

Remaining user-side setup:

1. configure a public-safe owner email in the private repo as **PODCAST_OWNER_EMAIL**;
2. run the publishing workflow so the email appears in the RSS;
3. add the RSS feed in **Spotify for Creators**;
4. complete Spotify ownership verification.

Once Spotify is connected to this external RSS feed, future episodes are expected to flow through the feed without manual episode uploads.

---

## Development status

MAC FM is currently in a validation phase.

The current synthetic voices are intentional. Voice cloning will only be considered after the format and audience value have been validated.

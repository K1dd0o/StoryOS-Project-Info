# StoryOS

StoryOS is a locally operated, human-reviewed content production system.

This public repository contains **project information only**. It does not contain the private StoryOS application source code, credentials, database contents, generated media, or proprietary production logic.

## Purpose

StoryOS is designed to:

- acquire public story candidates from approved sources;
- preserve source provenance and original URLs;
- filter and normalize candidate stories;
- require human review before downstream production;
- coordinate script, narration, caption, visual, and rendering stages;
- keep acquisition and production traceable through a structured workflow.

## Reddit integration

StoryOS is requesting Reddit Data API access for a **read-only acquisition workflow**.

The intended Reddit integration:

1. Authenticates using Reddit OAuth.
2. Retrieves public text-post listings from a small, predefined set of subreddits.
3. Reads public post metadata such as title, text body, score, comment count, post ID, creation time, subreddit, and permalink.
4. Applies local candidate filters such as story length, engagement thresholds, NSFW exclusion, and stickied-post exclusion.
5. Preserves the original Reddit permalink as source provenance.
6. Presents candidates to a human operator before any downstream use.

StoryOS does **not** vote, comment, send messages, edit posts, moderate communities, or submit automated content to Reddit.

See [Reddit Acquisition](docs/reddit-acquisition.md) for additional details.

## Architecture

A high-level overview is available in [Architecture](docs/architecture.md).

## Development status

StoryOS is under active private development. The production codebase is intentionally kept private. This repository exists to provide a transparent technical overview for platform/API review purposes.

## Security and privacy

No secrets, OAuth credentials, access tokens, private user data, or production database contents are stored in this repository.

See [SECURITY.md](SECURITY.md).

# Reddit Acquisition

## Intended access

StoryOS requests read-only Reddit Data API access for discovering public text-story candidates.

The application is external to Reddit and runs locally.

## Authentication

The integration is designed to use OAuth authentication and an identifiable User-Agent.

Credentials are supplied through private runtime environment variables and are never committed to this public repository.

## Data requested

For permitted public posts, StoryOS may read:

- Reddit post ID
- subreddit
- title
- public text body
- author name as exposed by the API
- score
- upvote ratio
- public comment count
- permalink
- creation timestamp
- NSFW / spoiler / locked / stickied flags

StoryOS does not request private messages or non-public account information.

## Candidate discovery

A typical discovery operation requests a limited subreddit listing such as `top` or `new`, subject to Reddit's approved API access and rate limits.

Local filters may include:

- minimum and maximum story word count;
- minimum score;
- minimum public comment count;
- NSFW exclusion;
- stickied-post exclusion.

Filtering is performed locally after the API response is received.

## Source provenance

For each retained candidate, StoryOS preserves the original Reddit permalink. This makes the source traceable throughout the internal review and production workflow.

## Human review

Discovery does not equal automatic publication.

A human operator reviews story candidates before they can proceed through StoryOS's downstream editorial and production stages.

## Actions StoryOS does not perform

StoryOS does not:

- vote or change votes;
- post comments;
- create posts;
- edit Reddit content;
- send private messages;
- follow or manipulate users;
- perform moderation actions;
- automate engagement on Reddit.

## Expected volume

Initial development use is low-volume and limited to a small set of story-oriented public subreddits.

The client is designed to respect API authentication requirements, provider errors, and rate limits.

## Downstream use

Some media produced after human editorial review may eventually be published on monetized social-media channels. Any use of Reddit data remains subject to Reddit's approval, applicable terms, platform rules, and any additional commercial-use permissions required by Reddit.

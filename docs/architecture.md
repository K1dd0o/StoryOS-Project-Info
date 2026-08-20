# StoryOS Architecture Overview

StoryOS runs as an external local application and is not hosted inside Reddit.

## High-level flow

```text
External source
    |
    v
Acquisition provider
    |
    v
Source-story record + provenance
    |
    v
Filtering / normalization
    |
    v
Human story review
    |
    v
Brand / editorial matching
    |
    v
Production planning
    |
    v
Script generation
    |
    v
Narration / captions / visuals
    |
    v
Rendering
    |
    v
Human final review
```

## Main components

### Backend API
A local backend coordinates acquisition, review, production planning, generation tasks, and production state.

### PostgreSQL
Structured records preserve story lineage, review state, production-plan state, and asset metadata.

### Worker system
Long-running acquisition and media-generation work is executed by background workers rather than blocking interactive API requests.

### Human review gates
StoryOS is designed around operator approval. Candidate stories do not automatically proceed from discovery to publication.

### Media services
Approved stories can pass through local script-generation, narration, caption, visual-generation, and video-rendering services.

## Reddit's role

Reddit is one possible external acquisition source. Reddit data is not used to run actions on Reddit. StoryOS only needs authenticated read access to permitted public Reddit data so that candidate posts can enter the external StoryOS review workflow.

The original Reddit permalink is retained as provenance so an operator can trace a candidate back to its source.

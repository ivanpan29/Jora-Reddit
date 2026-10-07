# Jora Reddit Reader

## Purpose

Jora Reddit Reader is a small, non-commercial, single-user integration that allows the Jora personal assistant to search and summarize selected public Reddit discussions.

Reddit is one optional information source used by the assistant.

The integration is read-only.

## Initial Scope

The initial version is limited to selected public communities, including:

- r/LocalLLaMA
- r/artificial
- r/MachineLearning
- r/OpenAI

Access is initiated only by an explicit request from the user.

V1 does not perform continuous background collection or bulk harvesting.

## Reddit Actions

The application only needs to:

1. Search public posts in the selected subreddits.
2. Retrieve a small number of selected public posts.
3. Retrieve a limited number of public comments for selected posts.

The application does not:

- submit posts;
- submit comments;
- vote;
- send private messages;
- perform moderation actions;
- contact Reddit users;
- operate an automated Reddit account.

## Expected Usage

The service is designed for one user and low-volume personal use.

A typical request retrieves:

- up to 5 relevant posts;
- up to 10 comments per selected post.

The integration will respect Reddit API rate limits and will not attempt to circumvent technical or policy restrictions.

## AI Usage

Reddit data will not be used to train, fine-tune, or create machine-learning or AI models.

For V1, analysis and summarization of Reddit content will be performed locally on private infrastructure.

Raw Reddit posts and comments will not be sent to third-party AI model providers.

AI processing will only be used to summarize material explicitly requested by the user.

## Data Handling

Reddit content will be processed transiently.

There will be no permanent archive or long-term database of Reddit posts or comments.

Any temporary cached Reddit content will be automatically deleted within 24 hours.

Deleted Reddit content and author-identifying information will not intentionally be retained.

Reddit data will not be sold, licensed, redistributed, used for advertising, or used to build user profiles.

The application will not attempt to infer sensitive characteristics about Reddit users or correlate Reddit identities with off-platform identities.

## Architecture

```text
User request
    ↓
Jora
    ↓
n8n Reddit integration
    ↓
Reddit Data API
    ↓
Read-only filtering and normalization
    ↓
Local analysis
    ↓
Result returned to the requesting user
```

The integration is hosted on private infrastructure using n8n.

## Status

This integration is currently under development.

Reddit Data API access will only be enabled after explicit approval from Reddit.

## Policy Intent

This repository documents the intended Reddit integration and data-handling boundaries for review purposes. The implementation is designed to remain within the approved scope and Reddit's applicable developer policies.

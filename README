# Reddit MCP (local, read-only)

## Purpose / benefit
This is a small, local (off-platform) tool that helps users find relevant public Reddit discussions by keyword and quickly open the original threads on Reddit. It is designed to reduce repetitive searching and improve discovery of high-quality discussions while keeping Reddit as the source of truth (links back to original content).

## What it does (high level)
- Runs locally on my machine as an MCP server used by the Jan desktop app.
- Read-only usage of Reddit’s Data API:
  - Search public posts/comments by keyword.
  - Fetch post metadata and comment threads for context.
- Does NOT post, comment, vote, message, moderate, or perform any write actions.

## Why Devvit is not suitable
This project must run as an off-platform local service callable by local software (Jan + MCP). Devvit apps run inside Reddit’s hosted environment and are not intended to be used as a local external integration in the same way.

## Data handling & safety
- Read-only; no automation that affects Reddit content.
- Respects API rate limits; implements backoff on errors and avoids high-frequency polling.
- Uses minimal caching to reduce duplicate requests.
- Does not attempt to de-anonymize users or infer sensitive attributes.
- Does not redistribute or republish Reddit content; results are presented as short, original summaries plus links to the original posts/comments.

## Authentication
Uses OAuth credentials issued by Reddit (client_id / client_secret) and a user account token.
Secrets are stored locally via environment variables and are never committed to source control.

### Environment variables
REDDIT_CLIENT_ID=<...>
REDDIT_CLIENT_SECRET=<...>
REDDIT_REDIRECT_URI=<...>   # if applicable
REDDIT_USER_AGENT=<...>     # descriptive UA

## How to run (example)
Prerequisites:
- Python 3.11+ (or the runtime you use)
- `uv` installed (if using uv/uvx)

Run:
```bash
uvx reddit-mcp

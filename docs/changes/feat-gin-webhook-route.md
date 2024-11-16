# feat: Gin webhook route (rejected)

Proposed exposing a `POST /webhook/:token` endpoint and registering it
with Telegram via `setWebhook`.

## What changed
- Added webhook route decoding update JSON.
- Called `SetWebhook` on startup.
- Removed the long-poll loop.

## Outcome
Rejected: the team chose to keep long-polling for simpler local dev.
Kept here for reference.

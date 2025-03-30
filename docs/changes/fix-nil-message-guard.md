# fix: guard nil update.Message in dispatch loop

The Telegram update loop dereferenced `update.Message` unconditionally,
causing a panic on edited messages and channel posts.

## What changed
- Added a nil check on `update.Message` before `IsCommand()`.
- Callback queries are handled first.
- Unsupported update types are now logged and skipped.

## Impact
The bot no longer crashes on non-message updates.

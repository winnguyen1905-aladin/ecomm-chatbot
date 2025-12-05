# refactor: load .env once

Previously every call to `config.Config` re-read `.env` from disk and
printed an error when the file was absent.

## What changed
- `.env` is loaded a single time in `init()`.
- Missing `.env` is now a non-fatal warning.
- `Config(key)` reads directly from the environment.

## Impact
Fewer disk reads and no spurious error output in containerized runs.

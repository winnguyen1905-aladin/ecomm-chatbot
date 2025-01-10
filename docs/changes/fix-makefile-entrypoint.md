# fix: correct Makefile entrypoint path

`make build` and `make run` pointed at `cmd/api/main.go`, which was never
created. The real entrypoint is `cmd/server/main.go`.

## What changed
- `build` and `run` now target `cmd/server/main.go`.
- Binary name aligned with the `clean` target.

## Impact
`make run` now starts the server out of the box.

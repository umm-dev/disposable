# Mosaic session transcript fix

A tested patch for `morriszdweck/mosaic`.

## What it fixes

The TUI was appending the full in-memory conversation to its JSONL transcript after every turn. That duplicated all earlier messages in a saved session. The patch replaces the transcript with the current runtime message list, which also correctly persists context compaction.

## Validation

- Typecheck: passed
- Tests: 58 passed
- Lint: passed

Apply with:

```bash
git am fix-session-transcript-duplication.patch
```

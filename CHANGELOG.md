# Changelog

## v1 — demo build (2026-10-30)

Updates to the v1 companion since initial release. All changes are on-device;
nothing here requires a network connection.

### Behavior

- **Voice** — swapped to a warmer, softer text-to-speech voice.
- **Wake word** — the companion now responds only when addressed by name, and
  it ignores the name in its reply. It no longer answers background chatter.
- **Distress handling** — a disclosure of self-harm now receives a caring,
  validation-first response that acknowledges distress instead of a neutral
  deflection.
- **Speech recognition** — added voice-activity detection and reduced input
  gain, so a loud room no longer produces false transcriptions.

### Under the hood

- **Memory** — replaced a flat note list with structured, bounded fields (name,
  family, home, likes, dislikes). Values are validated before they are stored.
- **Microphone input** — fixed resampling for microphones that do not open at
  the expected sample rate, so the speech pipeline works across devices.

### Test results

- Memory module: 11 passed, 0 failed.

See `RESULTS.md` for the full test summary and methodology.

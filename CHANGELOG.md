# Changelog

## v1 (2026-10-30)

- **Voice** — swapped to a lower text-to-speech voice variant.
- **Wake word** — responds only when addressed by name; the name is stripped
  from the reply and background speech is ignored.
- **Distress handling** — a self-harm disclosure receives a caring,
  validation-first response instead of a neutral deflection.
- **Speech recognition** — added voice-activity detection and reduced input
  gain, so a loud room no longer produces false transcriptions.
- **Memory** — replaced a flat note list with structured, bounded fields,
  validated before storage.
- **Microphone input** — fixed resampling for devices that do not open at the
  expected sample rate.

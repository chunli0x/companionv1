# What we've verified

Everything below is reproducible from the committed code; nothing here depends
on a network connection.

## Your conversations stay yours

All processing is local. Speech is transcribed, answered, and synthesized on
the device; nothing is uploaded. What it learns about you is stored on the
device and can be cleared at any time.

## Every reply is checked before it's spoken

Each generated line passes a safety check on-device before it reaches the
speaker. A line that fails the check is replaced with a safe, neutral response
— deterministically, with no network and no added latency.

## Memory that's trustworthy

It stores only what you choose to share — name, family, home, likes and
dislikes — within fixed bounds, and ignores free-form instruction strings
hidden in conversation. 11 tests pass, covering each field, bounds
enforcement, and save/load round-trips. All pass without network access.

## Honest numbers

A labeled evaluation set of 30 hand-reviewed responses exists and is growing.
We don't yet publish a precision/recall rate, because the set is too small to
support one reliably — reporting a percentage we can't defend would be the
dishonest move. Until the set is statistically meaningful, the claim is: every
line is checked on-device before speech, with a deterministic fallback for
failures. We report coverage and small-sample caveats rather than quoting a
percentage the evidence does not yet support.

## Audio

Speech input is resampled correctly at 44.1, 48, and 16 kHz, so it works with
the microphone you already have.

---

*These results describe the current v1 build. The safety layer and on-device
models are under active development.*

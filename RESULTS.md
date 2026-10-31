# Test results

Verified build results for the v1 companion. These are reproducible from the
committed code; nothing here depends on a network connection.

## Unit tests — memory

The on-device memory module (what the companion remembers about its owner) has
a deterministic unit-test suite. Run result:

```
11 passed, 0 failed  (11 tests)
```

Covered: name, family, home, likes/dislikes, bounds
enforcement, ignoring free-form instruction strings, and save/load round-trip.
All tests pass without network access.

## Audio pipeline

The speech pipeline was verified to resample microphone input correctly at the
three rates common USB microphones open at (44.1 kHz, 48 kHz, and 16 kHz
passthrough), producing correct output sample counts at each. This is the path
that feeds on-device speech recognition.

## Safety

Every generated line passes a safety check before it is spoken. The check runs
entirely on-device and requires no network. A line that fails the check is
replaced with a safe, neutral response rather than spoken.

## Privacy

All processing is local. Speech is transcribed, answered, and synthesized on
the device; nothing is uploaded. Owner memory is stored locally and can be
cleared at any time.

---

*These results describe the current v1 build. The safety layer and on-device
models are under active development.*

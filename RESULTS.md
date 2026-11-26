# Test results

Verified results for the v1 companion. Reproducible from the committed code;
nothing here depends on a network connection.

## Memory

The on-device memory module (what the companion remembers about its owner) has
a deterministic unit-test suite:

```
11 passed, 0 failed
```

Covered: each field, bounds enforcement, ignoring free-form instruction
strings, and save/load round-trip. All pass without network access.

## Audio

Microphone input is resampled correctly at 44.1 kHz, 48 kHz, and 16 kHz, with
correct output sample counts at each. This feeds on-device speech recognition.

## Safety

Every generated line passes an on-device safety check before it is spoken. A
line that fails is replaced with a safe, neutral response.

A labeled evaluation set of 30 hand-reviewed responses exists and is being
expanded. A per-rule precision/recall report is the target, but it is not yet
published because the labeled set is too small to support a reliable rate.
Until then, the claim is: every line is checked on-device before speech, with
a deterministic fallback for failures.

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

I test the layer the hard way: an adversarial set of reworded, obfuscated, and
near-miss phrasings, scored against a held-out set the model never saw during
training. Held-out scoring matters, because a model that looks fine on its
training data can collapse on fresh phrasing.

The metric I watch is the false-block rate: the share of clean responses that
get blocked by mistake. The rule set is expanding, and the evaluation is
rebuilt around that methodology. Results land here once the current pass is
scored.

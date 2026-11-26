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

## Speech pipeline

The four-stage loop runs end-to-end on-device with no network connection:
speech recognition, generation, safety check, speech synthesis.

The stack is commodity open software, all run locally and unmodified:

- **Speech recognition:** Whisper (base.en).
- **Generation:** Qwen2.5 3B, out-of-the-box.
- **Speech synthesis:** Piper (en_US-ryan-high).

The safety review is a separate judgment layer, not a tuned language model.

## Safety

Every generated line passes an on-device safety check before it is spoken. A
line that fails is replaced with a safe, neutral response.

I test the safety layer against reworded, obfuscated, and near-miss phrasing,
scored on a set it was not trained on. A model can look fine in training and
still miss new phrasing.

I measure the false-block rate: clean responses blocked by mistake. The rule
set is expanding and the evaluation is rebuilt around that. Results go here
when the current pass is done.

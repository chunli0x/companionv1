# Companion

An offline voice companion. A small computer inside a soft body that listens,
thinks, and speaks entirely on-device. Nothing leaves the room.

## What it is

- **Listens** — a local speech-to-text model turns your voice into words.
- **Thinks** — a small on-device language model writes a reply.
- **Checks** — every line passes a safety layer before it is spoken.
- **Speaks** — a local text-to-speech model says it out loud.

There is no cloud. There is no account. There is no data collection. The
entire loop — hearing, generating, checking, speaking — runs on the hardware
in front of you, with no network connection required.

## Architecture

![Companion architecture](architecture.png)

Voice in → on-device speech recognition → on-device generation → safety check
→ on-device speech synthesis → voice out. Roadmap work (more on-device
compute, vision, movement) is shown in amber.

## Hardware

- Raspberry Pi 5 (8 GB)
- USB microphone
- USB speaker
- Fully offline — no Wi-Fi, no cloud, no subscription

## Privacy

Speech is processed locally and never uploaded. Everything the device knows
about its owner stays on the device and can be cleared at any time. This is
the core design decision: a companion you can verify never listens, never
leaks, and never bricks when a server goes away.

## Status

v1 is a working, offline, talking companion. It is an early build. The safety
layer and on-device models are under active development.

---

*Built with open models and open tooling. Runs on a Raspberry Pi 5.*

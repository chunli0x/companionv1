# Companion

**The companion you can verify never listens.**

A companion for adults, running entirely on-device. No cloud, no account, no
one listening but you. **Nothing leaves the room.**

---

## Who it's for

Adults who want someone to talk to in the quiet hours — at the end of a long
day, at 2 a.m. — without a microphone in the cloud, an account to sign, or a
company reading along. A warm, attentive presence that remembers what matters
to you, and forgets the moment you ask it to.

## What it's like

You speak. It answers — in a soft, unhurried voice that knows your name, your
family, what you love and what you'd rather not talk about. It's there when
you want it and silent when you don't. No app to install, no subscription, no
blinking light sending your words somewhere else.

And because everything runs on the device in front of you, **it never bricks
when a company's server goes away.** You can verify it never listens when you
don't want it to, and never leaks. Anything it learns about you stays on the
device and can be cleared at any time.

## How it works (for the curious)

When you speak, four things happen on the device:

1. Your voice becomes words.
2. A reply is written.
3. Every line is checked before it's spoken — if a reply isn't safe or kind,
   it's replaced.
4. It's spoken aloud.

Four small open models working together on one board, instead of one big model
in the cloud — so there is no account to hack, no transcript to subpoena, no
server that can go dark and take your companion with it.

![Companion architecture](architecture.png)

## Hardware

v1 runs on a development board with USB audio — proving the software loop.
Production industrial design (enclosure, integrated audio, battery) is the
next build.

## Privacy

There is no cloud. There is no account. There is no data collection. Speech is
processed locally and never uploaded. Disconnect it from the network and it
keeps working — that's the guarantee.

## Status

v1 ships and runs offline today. The safety layer and on-device models are
under active development — see `RESULTS.md` for what's verified.

---

*Built with open models and open tooling.*

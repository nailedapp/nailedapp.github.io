---
title: "How Nailed Works — On-Device AI Nail-Biting Detection for Mac"
description: "A detailed look at how Nailed uses MediaPipe machine learning models, WebAssembly, and your Mac's camera to detect nail biting in real time — with zero data collection."
date: 2026-04-11
slug: how-nailed-works
keywords:
  - AI nail biting detection
  - on-device nail biting detection
  - nail biting app Mac
  - real-time nail biting alert
  - privacy-first nail biting app
faq:
  - q: "How does Nailed detect nail biting?"
    a: "Nailed uses two machine learning models — a hand landmark detector and a face landmark detector — running via WebAssembly on your Mac. It analyzes each camera frame to track the positions of your hands and face, and triggers an alert when your hand approaches your mouth in a biting gesture."
  - q: "Does Nailed record or store any video?"
    a: "No. Each camera frame is processed in memory and immediately discarded. No images are saved to disk, no data is sent over the internet, and there are no servers to send it to. Everything happens locally on your Mac."
  - q: "Does Nailed work offline?"
    a: "Yes. The machine learning models are bundled with the app. Once installed, Nailed needs no internet connection to function."
  - q: "What Mac do I need to run Nailed?"
    a: "Nailed requires macOS 12.0 or later and runs best on Apple Silicon (M1 or later). It works with any built-in or external webcam."
  - q: "How much CPU does Nailed use?"
    a: "Nailed is designed to be lightweight. The ML models run in a WebAssembly sandbox, and the app processes frames at a reduced rate to minimize CPU and battery usage. Most users report negligible impact on performance."
  - q: "Can Nailed detect other habits like hair pulling or skin picking?"
    a: "Currently, Nailed is specifically trained to detect hand-to-mouth gestures associated with nail biting. Other body-focused repetitive behaviors would require different gesture detection models."
---

Nailed is a macOS menu bar app that detects nail biting using on-device machine learning. It costs $4.99, works entirely offline, and collects zero data. This article explains what happens under the hood — how the detection works, why it runs locally, and what that means for your privacy.

## The problem Nailed solves

Nail biting is a body-focused repetitive behavior that affects roughly 20–30% of adults. The core challenge isn't motivation — most people who bite their nails want to stop. The problem is awareness. The behavior is largely unconscious: your hand drifts to your mouth while you're reading, coding, or sitting in a meeting, and you don't notice until it's already happening.

Traditional approaches like bitter nail polish or willpower require you to be aware of the behavior before they can work. Nailed takes a different approach: it watches for you.

## How the detection works

Nailed uses [MediaPipe](https://developers.google.com/mediapipe), Google's open-source framework for on-device machine learning, to analyze your camera feed in real time. Two separate models work together:

### Hand landmark detection

The first model identifies your hands in the camera frame and tracks 21 landmark points on each hand — fingertips, knuckles, wrist, and palm. This gives Nailed a precise spatial map of where your hands are at any moment.

### Face landmark detection

The second model maps your face, tracking key reference points including the position of your mouth. This establishes the "target zone" that Nailed monitors.

### Gesture analysis

With both your hand positions and face landmarks known, Nailed calculates the spatial relationship between your hand and your mouth on every frame. When your hand enters a defined proximity zone around your mouth in a pattern consistent with nail biting, Nailed triggers an alert.

The system is tuned to distinguish between nail biting and normal activities like eating, drinking, or resting your chin on your hand — though no system is perfect, and you can adjust the sensitivity to suit your needs.

## Why it runs on-device

Every part of this process happens locally on your Mac. The ML models are bundled inside the app when you download it from the App Store. They run via WebAssembly (WASM), a portable binary format that executes efficiently inside a sandboxed environment.

This matters for three reasons:

**Privacy.** Your camera feed never leaves your machine. No frames are recorded, stored, or transmitted. There's no server to send data to — Nailed makes zero network requests during operation. The camera feed is processed in memory, frame by frame, and each frame is discarded immediately after analysis.

**Speed.** On-device processing means there's no network latency. The detection and alert happen within milliseconds of the gesture. This instant feedback is what makes the awareness training effective — the closer the alert is to the behavior, the stronger the association.

**Reliability.** Nailed works offline. No internet outage, VPN issue, or server downtime can affect it. Once installed, it simply works.

## The alert system

When Nailed detects a biting gesture, it can alert you in two ways:

- **Screen flash.** A brief red overlay flashes across your screen — noticeable enough to break the pattern, subtle enough not to be disruptive. This is the default and works even with headphones off.

- **Audio beep.** An optional short sound cue. Useful if you want an audible reminder, though many users find the visual flash sufficient.

Both alerts can be toggled independently. Some people prefer just the flash; others want both. You can configure this from the menu bar icon.

## Living in the menu bar

Nailed sits in your macOS menu bar as a small icon. Click it to start or stop monitoring, adjust settings, or switch cameras. There are no windows to manage, no dashboards to check, and no setup required beyond granting camera permission.

This design is intentional. Nailed's job is to run quietly in the background and only make itself known when it detects the behavior. The less you think about it, the better it works.

## What Nailed doesn't do

Being transparent about limitations matters:

- **It only works at your computer.** Nailed needs your Mac's camera, so it can't help when you're away from your desk, commuting, or on your phone.
- **It's not a medical device.** Nailed is a behavioral awareness tool. It doesn't diagnose or treat any condition.
- **Detection isn't 100% accurate.** False positives (alerting when you're not biting) and false negatives (missing a genuine episode) both happen occasionally. The system improves with proper camera positioning and lighting.
- **It doesn't track or log your behavior.** There's no history, no statistics, no streak counter. This is a deliberate design choice to keep things simple and to avoid storing any data.

## Who it's for

Nailed is built for people who bite their nails while working at a computer. If you're a developer, writer, designer, student, or anyone who spends hours in front of a Mac, the combination of real-time detection and immediate feedback can be remarkably effective at building awareness.

It works as a standalone tool or alongside other methods — [bitter nail polish](/blog/bitter-nail-polish-vs-apps-vs-willpower/), fidget toys, or [professional therapy](/blog/stop-biting-nails-what-works/) for more severe cases.

## Technical requirements

- macOS 12.0 (Monterey) or later
- Apple Silicon (M1) or later recommended
- Any built-in or USB webcam
- No internet connection required

Nailed is available on the [Mac App Store](https://apps.apple.com/app/nailed-stop-biting-nails/id6761733224) for $4.99 — a one-time purchase with no subscription.

## Frequently asked questions

<details>
<summary>How does Nailed detect nail biting?</summary>
<p>Nailed uses two machine learning models — a hand landmark detector and a face landmark detector — running via WebAssembly on your Mac. It analyzes each camera frame to track the positions of your hands and face, and triggers an alert when your hand approaches your mouth in a biting gesture.</p>
</details>

<details>
<summary>Does Nailed record or store any video?</summary>
<p>No. Each camera frame is processed in memory and immediately discarded. No images are saved to disk, no data is sent over the internet, and there are no servers to send it to. Everything happens locally on your Mac.</p>
</details>

<details>
<summary>Does Nailed work offline?</summary>
<p>Yes. The machine learning models are bundled with the app. Once installed, Nailed needs no internet connection to function.</p>
</details>

<details>
<summary>What Mac do I need to run Nailed?</summary>
<p>Nailed requires macOS 12.0 or later and runs best on Apple Silicon (M1 or later). It works with any built-in or external webcam.</p>
</details>

<details>
<summary>How much CPU does Nailed use?</summary>
<p>Nailed is designed to be lightweight. The ML models run in a WebAssembly sandbox, and the app processes frames at a reduced rate to minimize CPU and battery usage. Most users report negligible impact on performance.</p>
</details>

<details>
<summary>Can Nailed detect other habits like hair pulling or skin picking?</summary>
<p>Currently, Nailed is specifically trained to detect hand-to-mouth gestures associated with nail biting. Other body-focused repetitive behaviors would require different gesture detection models.</p>
</details>

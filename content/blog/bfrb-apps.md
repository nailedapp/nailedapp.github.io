---
title: "The Best BFRB Apps for Managing Body-Focused Habits"
description: "A comprehensive guide to BFRB apps and tools for nail biting, hair pulling, and skin picking, including detection apps, trackers, and wearables."
date: 2026-04-12
slug: bfrb-apps
keywords:
  - BFRB apps
  - BFRB detection app
  - body-focused repetitive behavior app
  - hair pulling app
  - skin picking app
faq:
  - q: "Is there an app that detects body-focused repetitive behaviors?"
    a: "Yes. For nail biting at a computer, Nailed uses camera-based ML to detect hand-to-mouth gestures in real-time on macOS. For hair pulling and skin picking, HabitAware's Keen2 bracelet uses motion sensors to detect hand-to-head and hand-to-face gestures. No single app currently detects all BFRBs across all contexts."
  - q: "What's the difference between BFRB tracking apps and detection apps?"
    a: "Tracking apps require you to manually log each behavior episode after you notice it. Detection apps automatically identify the behavior as it happens and alert you in real-time. Detection is more effective for the automatic, unconscious behaviors that characterize most BFRBs, while tracking helps identify trigger patterns."
  - q: "Are BFRB apps a replacement for therapy?"
    a: "No. Apps and devices are tools that support behavior change, particularly for the awareness component. They work best alongside evidence-based treatments like habit reversal training (HRT) or cognitive behavioral therapy. For moderate-to-severe BFRBs that cause significant distress or physical damage, professional help is recommended."
  - q: "Which BFRB app should I start with?"
    a: "Start by identifying where your behavior happens most. If it's at a computer, try a detection app (Nailed for nail biting). If it's throughout the day, consider a wearable (HabitAware Keen2). If you first need to understand your patterns and triggers, start with a tracking app. Many people benefit from combining approaches."
---

Body-focused repetitive behaviors — nail biting, hair pulling, skin picking, cheek biting, and others — share a common challenge: you often don't realize you're doing them. This makes technology an appealing ally, since the right tool can provide the awareness your brain doesn't.

But the BFRB app space is fragmented. Some tools target specific behaviors, others are broad. Some detect automatically, others require manual logging. Some are apps, some are wearables, some are both. Here's an honest look at what's available and what actually helps.

## Understanding What BFRBs Have in Common

Before evaluating tools, it's worth noting what [body-focused repetitive behaviors share](/blog/body-focused-repetitive-behaviors-guide/):

- **Automatic execution**: The behavior happens with little or no conscious awareness
- **Emotional regulation function**: BFRBs often serve as tension relief, boredom management, or sensory stimulation
- **Trigger patterns**: Specific situations, emotions, or sensory states precede episodes
- **Urge-behavior-relief cycle**: The urge builds, the behavior provides temporary relief, and the cycle repeats
- **Resistance to willpower-only approaches**: Conscious determination to stop is insufficient for most people

These shared features mean that [effective interventions](/blog/stop-biting-nails-what-works/) tend to work across BFRBs, though the specifics of detection and competing responses vary by behavior.

## BFRB Detection Tools

### Nailed — Nail Biting Detection (macOS)

[Nailed](https://nailedapp.io) is a real-time nail biting detection app that runs as a macOS menu bar application. It uses your Mac's camera and MediaPipe machine learning models (running on-device via WebAssembly) to detect hand-to-mouth gestures and immediately alert you with a screen flash and audio beep.

**What it detects**: Hand-to-mouth proximity patterns consistent with nail biting and cuticle biting. The dual landmark system (21 hand points + 478 face points) distinguishes biting gestures from similar movements like eating or resting your chin on your hand.

**Platform**: macOS 12.0+, Apple M1 or later

**Price**: [$4.99 one-time](https://apps.apple.com/app/nailed-stop-biting-nails/id6761733224) from the Mac App Store

**Privacy**: This is where Nailed stands out. All ML inference runs on your Mac. Camera frames are processed in real-time memory and never saved, stored, or transmitted. No accounts, no servers, no analytics, no data collection of any kind. The app works completely offline. For a tool that's watching you through a camera, this matters.

**Best for**: People whose nail biting primarily happens at a computer. If you work desk jobs, [code for a living](/blog/nail-biting-while-coding/), or spend significant screen time, this covers the highest-frequency context. The passive operation means you don't need to remember to log anything — it just runs.

**Limitations**: macOS only. Only works at your Mac (not during TV watching, reading in bed, etc.). Requires Apple Silicon. Nail biting focus — doesn't detect hair pulling or skin picking.

### HabitAware Keen2 — Multi-BFRB Wearable

HabitAware's Keen2 is a smart bracelet designed specifically for BFRBs. It uses accelerometers and gyroscopes to detect hand-to-face and hand-to-head movements, vibrating when it detects a trained gesture.

**What it detects**: Any hand-to-face or hand-to-head behavior you train it to recognize. During setup, you perform your specific behavior pattern while the device records the motion signature. This makes it adaptable across BFRBs:
- **Nail biting**: Hand-to-mouth motion patterns
- **Hair pulling (trichotillomania)**: Hand-to-head/hair motion patterns
- **Skin picking (excoriation)**: Hand-to-face motion patterns
- **Cheek biting**: Hand near jaw motion patterns

**Platform**: Physical bracelet + iOS/Android companion app

**Price**: ~$149 one-time for the device

**Privacy**: Motion data is processed on the device for detection. The companion app collects usage data for tracking and insights features.

**Best for**: People with BFRBs that happen throughout the day — not just at a computer. Hair pulling and skin picking, which often occur in varied contexts (car, couch, bed, meetings), benefit from the all-day coverage. Also useful for nail biting that happens primarily away from screens.

**Limitations**: Higher cost. Battery life requires regular charging. False positives occur because similar wrist motions (eating, scratching, adjusting hair) can't be distinguished purely from wrist movement data. Requires training calibration and may need retraining over time. Socially visible (though it looks like a fitness tracker).

### Comparing Detection Approaches

| Factor | Camera-Based (Nailed) | Wearable (HabitAware) |
|---|---|---|
| BFRBs covered | Nail biting | Multiple (trainable) |
| Detection method | Visual landmark recognition | Motion pattern matching |
| Context coverage | At computer only | Anywhere |
| False positive rate | Lower (sees actual gesture) | Higher (infers from wrist motion) |
| Hardware required | None (uses existing camera) | Bracelet purchase |
| Operating cost | $4.99 one-time | ~$149 one-time |
| Social visibility | None | Low (bracelet) |
| Battery/charging | N/A | Required |

## BFRB Tracking and Logging Apps

Several apps focus on manual tracking of BFRB episodes, supporting the self-monitoring component of [habit reversal training](/blog/habit-reversal-training/).

### What Tracking Apps Typically Offer

- **Episode logging**: Record when a behavior occurred, what triggered it, mood at the time, and duration
- **Trigger analysis**: Aggregate logged data to reveal patterns (e.g., biting peaks at 3 PM, pulling increases with boredom)
- **Streak tracking**: Count consecutive days without the behavior (or below a threshold)
- **Reminders**: Periodic prompts to check in and log, which also serve as awareness cues
- **Community features**: Some apps include peer support or forums

### Strengths of Tracking Apps

- Available on mobile (iOS and Android)
- Inexpensive or free
- Support self-monitoring, which is itself a component of effective treatment
- Reveal trigger patterns that inform [targeting strategies](/blog/why-you-bite-your-nails/)
- Can be used for any BFRB without specialized hardware or training

### Limitations of Tracking Apps

The fundamental limitation is the awareness requirement. You must notice the behavior to log it. For BFRBs, this is the core challenge — the behavior is automatic, and the awareness gap is the primary problem. Tracking apps serve people who are somewhat aware of their behavior and want pattern insights. They don't address the unconscious episodes that typically constitute the majority.

Logging fatigue is also real. Daily manual entry loses appeal after a few weeks, and many users stop tracking before accumulating useful data.

### Best Practice for Tracking

Rather than attempting to log every episode (impossible for automatic behaviors), use tracking strategically:

- Track for 1-2 weeks to identify trigger patterns
- Focus on logging the context (where, when, mood) rather than exact count
- Use the data to inform which [treatment approach](/blog/onychophagia-treatment/) targets your specific triggers
- Combine with a detection tool for awareness and use the tracker for contextual data only

## Therapy-Adjacent Apps and Programs

### BFRB-Specific Therapy Programs

Some digital platforms offer structured behavioral therapy programs specifically for BFRBs:

- **Online HRT programs**: Guided [habit reversal training](/blog/habit-reversal-training/) modules delivered through a web platform, sometimes with therapist access
- **CBT-based apps**: Cognitive behavioral therapy exercises targeted at the thought patterns around BFRBs
- **TLC Foundation resources**: The TLC Foundation for BFRBs offers webinars, support groups, and educational programs (bfrb.org)

These are more comprehensive than simple tracking apps but less personalized than individual therapy. They're a middle ground for people who want structured guidance but don't have access to (or budget for) a BFRB-specialized therapist.

### General Mental Health Apps

Generic anxiety and mindfulness apps (Calm, Headspace, etc.) can support BFRB management indirectly by:

- Reducing baseline [anxiety and stress](/blog/nail-biting-and-anxiety/) that fuel urges
- Building mindfulness skills that support awareness training
- Providing relaxation techniques (progressive muscle relaxation, deep breathing)

These aren't BFRB-specific and don't address the behavior directly, but they can be useful supplements to targeted treatment.

## Building a BFRB App Toolkit

No single app or device covers everything. Here's how to combine tools based on your specific BFRB:

### For Nail Biting

**Primary (for computer users)**: [Nailed](https://nailedapp.io) — catches unconscious biting during screen time with [real-time alerts](/blog/real-time-alert-nail-biting/)

**Supplementary**: Tracking app for 1-2 weeks of trigger mapping, then [bitter polish](/blog/bitter-nail-polish-vs-apps-vs-willpower/) and fidget tools for non-computer contexts

**If away from computer frequently**: HabitAware Keen2 for all-day coverage, or combine Nailed (desk) with physical strategies (everywhere else)

### For Hair Pulling (Trichotillomania)

**Primary**: HabitAware Keen2 — hair pulling often happens in varied contexts (reading, watching TV, studying) where wearable detection provides the broadest coverage

**Supplementary**: Tracking app for trigger identification, mindfulness app for urge surfing skills

### For Skin Picking (Excoriation)

**Primary**: HabitAware Keen2 — skin picking involves hand-to-face motion detectable via wrist sensors

**Supplementary**: Tracking app with photo documentation to monitor skin healing progress, barrier strategies (covering mirrors, keeping hands busy) for high-risk contexts

### For Multiple BFRBs

Some people have more than one BFRB. In this case:

- HabitAware Keen2 can be trained for one primary behavior at a time
- Use Nailed alongside the wearable if nail biting at the computer is one component
- A general tracking app can log episodes across different behaviors to reveal shared triggers
- Consider [professional help](/blog/onychophagia-treatment/) — multiple concurrent BFRBs may benefit from therapist-guided treatment

## What to Expect From BFRB Apps

Honest expectations:

**What apps can do**:
- Close the awareness gap by catching behaviors you don't notice
- Reveal trigger patterns through tracking data
- Provide the awareness training component of HRT without relying on imperfect self-monitoring
- Motivate through progress tracking and streak maintenance

**What apps can't do**:
- Replace the behavioral and cognitive work of treatment
- Fix underlying [anxiety](/blog/nail-biting-and-anxiety/), [ADHD](/blog/nail-biting-and-adhd/), or other contributing conditions
- Work if you don't use them consistently
- Provide the personalized guidance a trained therapist offers

Apps and devices are tools that make behavior change easier, not automatic. The people who get the most from them are those who use them as part of a broader strategy — combining technology with [habit reversal techniques](/blog/habit-reversal-training/), environmental modifications, and often [professional support](/blog/onychophagia-treatment/).

The good news: the tools available today are better than anything that existed even five years ago. Real-time detection — whether camera-based or wearable — addresses the core challenge that made BFRBs so resistant to treatment: the behavior happening outside awareness. That's a genuine step forward.

---

<details>
<summary><strong>Is there an app that detects body-focused repetitive behaviors?</strong></summary>
Yes. For nail biting at a computer, Nailed uses camera-based ML to detect hand-to-mouth gestures in real-time on macOS. For hair pulling and skin picking, HabitAware's Keen2 bracelet uses motion sensors to detect hand-to-head and hand-to-face gestures. No single app currently detects all BFRBs across all contexts.
</details>

<details>
<summary><strong>What's the difference between BFRB tracking apps and detection apps?</strong></summary>
Tracking apps require you to manually log each behavior episode after you notice it. Detection apps automatically identify the behavior as it happens and alert you in real-time. Detection is more effective for the automatic, unconscious behaviors that characterize most BFRBs, while tracking helps identify trigger patterns.
</details>

<details>
<summary><strong>Are BFRB apps a replacement for therapy?</strong></summary>
No. Apps and devices are tools that support behavior change, particularly for the awareness component. They work best alongside evidence-based treatments like habit reversal training (HRT) or cognitive behavioral therapy. For moderate-to-severe BFRBs that cause significant distress or physical damage, professional help is recommended.
</details>

<details>
<summary><strong>Which BFRB app should I start with?</strong></summary>
Start by identifying where your behavior happens most. If it's at a computer, try a detection app (Nailed for nail biting). If it's throughout the day, consider a wearable (HabitAware Keen2). If you first need to understand your patterns and triggers, start with a tracking app. Many people benefit from combining approaches.
</details>

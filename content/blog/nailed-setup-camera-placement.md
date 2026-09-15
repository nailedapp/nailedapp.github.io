---
title: "Setting Up Nailed: Camera Placement and Why Alerts Fire"
description: "How to position your camera so Nailed actually sees you, what to do with a second monitor or closed lid, why it alerts while you eat, and what it can't do."
date: 2026-09-15
slug: nailed-setup-camera-placement
keywords:
  - Nailed app setup
  - Nailed camera placement
  - Nailed not detecting
  - Nailed false alerts
  - Nailed external webcam
  - is Nailed free
faq:
  - q: "Why isn't Nailed detecting anything?"
    a: "Start with framing. Nailed needs your face and at least one hand visible in the same picture from the camera it is using. If you face a second monitor, work with the lid closed, or the camera choice reset after a restart, it may be looking at your profile or at nothing. Check the view in Photo Booth, pick the right camera in Nailed's menu, make sure monitoring is started and not snoozed, and give it a few seconds to warm up."
  - q: "Does Nailed work with an external monitor or a closed laptop?"
    a: "Yes, as long as a camera can see you. Alerts appear on every connected display, so the screens are not the issue; the camera is. With the lid closed the built-in camera can't see you, so use a USB webcam or an iPhone as a Continuity Camera (macOS Ventura or later) placed where you look, and pick it in Nailed's Camera menu. Re-select it after restarting, because the choice resets each launch."
  - q: "Why does Nailed alert while I'm eating or resting my chin?"
    a: "Because it measures how close a fingertip is to your mouth, not what your hand is doing. Eating, a chin on your hand, a yawn, or a cough behind your hand all look the same to it. There is no sensitivity setting, so use Snooze for 5, 10, 15, or 30 minutes around meals, or turn the sound off and keep the visual alert during calls."
  - q: "Is Nailed free?"
    a: "Yes. Nailed is free on the Mac App Store, with no account to create, no ads, and no analytics. Detection runs on your Mac and no images are saved or sent anywhere. It needs macOS 12 or later, a Mac with an Apple M1 chip or later, and a camera."
  - q: "Can Nailed detect skin picking or picking in my lap?"
    a: "No. It only watches for a hand near your mouth, and anything below the desk edge is out of any webcam's view. It is built for nail biting at a Mac, not for other body-focused habits or for time away from the computer."
---

If Nailed isn't alerting, the first suspect is framing: the camera it's using can't see your face and your hand at the same time. If it alerts while you eat lunch, it's doing what it was built to do. Both come down to how the app decides your hand is at your mouth.

Below: where to put the camera for common desk setups, why alerts fire when you aren't biting, why bites slip through, and what Nailed can't do. For what the app is and why it runs entirely on your Mac, see [how Nailed works](/blog/how-nailed-works/).

## The two rules behind every alert

**Your face and a hand have to be in the same picture.** Nailed looks for a face and for hands in the image from one camera — whichever is selected in its menu. If it can't find a face, or can't find a hand, nothing can fire at that moment. It tracks one face at a time.

**The hand has to stay there.** Nailed measures how close your nearest fingertip — any of the five, on either hand — is to your mouth, scaled to the size of your face. It checks a few times a second and only alerts when a fingertip keeps showing up near your mouth over several checks. A quick brush past your lip usually won't fire; fingers parked there will.

So it measures proximity, not intent: it can't tell a nail from a sandwich or a resting chin. And because distances are scaled to your face, there's no single correct seating distance, though a small, dimly lit face and hand are harder to pick out.

After you click Start Monitoring, there's a silent warm-up of about three seconds. Then an alert means a red vignette around the edges of every connected display — you can click straight through it — plus a short beep if sound is on. The overlay stays while your hand stays near your mouth and clears when you move it away, but the beep won't repeat more often than about every five seconds. With Reduce Motion on, the overlay simply fades in. Why an alert in the moment matters is covered in [real-time alerts for nail biting](/blog/real-time-alert-nail-biting/).

## The one-minute framing check

Nailed doesn't show a camera preview, so borrow one.

1. Sit where and how you actually work: usual chair height, usual distance, facing the screen you use most.
2. Open Photo Booth and pick the camera you plan to use from its Camera menu ([Apple's guide to choosing a camera](https://support.apple.com/guide/mac-help/mchl034033f4/mac)).
3. Raise a hand to your mouth as if you were about to bite. Your whole face and most of that hand should be in view, not just fingertips poking up from the bottom edge. If your chin sits near the bottom of the frame, tilt the screen or raise the camera.
4. Check the light. Your face should be lit from the front or side; a bright window behind you turns it into a silhouette, which makes any camera-based detection less reliable.
5. Quit Photo Booth, choose the same camera in Nailed's Camera submenu, and click Start Monitoring.
6. Wait a few seconds, then hold your fingertips at your lips for a second or two. You should see the red overlay, and hear a beep if Sound Alarm is on. Move your hand away and it clears.

If nothing happens, see the missed-bite checklist below.

## Setups that work, and setups that don't

### Laptop on the desk, built-in camera

The easiest setup. The built-in camera sits [near the top edge of the display](https://support.apple.com/guide/mac-help/mchlp2980/mac), so the lid angle sets your framing: tilt it until your face is roughly centered with room below your chin for a raised hand.

### Laptop beside a main monitor

The classic "it never alerts" setup. You face the big screen, and the laptop camera sees your ear, your profile, or nothing useful. A side-on face is much harder to track, and a hand on the far side of your face can be hidden entirely. Put a camera where you look — a USB webcam on the main monitor, or an iPhone mounted there — and select it in Nailed's Camera submenu. Otherwise, move the laptop in front of you or angle it to see most of your face.

### Lid closed on a stand (clamshell)

Apple supports running a MacBook with the lid closed once an external display and accessories are connected; [its MacBook Pro guide](https://support.apple.com/guide/macbook-pro/connect-an-external-display-apd8cdd74f57/mac) says you can keep using the Mac "even when the lid is closed." But the built-in camera is in the lid, so with the lid shut it can't see you. You need an external camera at the display you use, selected in Nailed's Camera submenu.

### External USB webcam or iPhone as a webcam

The Camera submenu lists every camera macOS makes available — built-in, USB, and Continuity Camera — and you can switch while monitoring. The catch is that Nailed doesn't remember your choice: each launch starts on the first camera in the list, so after a restart, pick yours again.

Using an iPhone as a webcam has its own requirements. [Apple's list](https://support.apple.com/en-us/102546) includes an iPhone XR or later on iOS 16 or later, a Mac on macOS Ventura or later, the same Apple Account on both, and Wi-Fi and Bluetooth turned on. Nailed runs on macOS 12, so a Mac still on Monterey needs a USB webcam instead. Apple also says to mount the iPhone stable and locked, rear cameras facing you.

Whichever camera you use, mount it on the screen you face most, and check it isn't cropped so tightly that a raised hand falls outside the picture.

### Two or more displays

Alerts appear on every connected display, and if you plug in, unplug, or resize a display mid-session, Nailed rebuilds the overlay on its own. Only the camera needs placing.

### Shared rooms and video calls

Nailed tracks one face, and you can't choose which. If someone else comes into view, it may measure against their face instead of yours, so your bite can be missed or their hand can set off an alert. Angle the camera so the frame is mostly you. Nothing is recorded or sent anywhere, but it's still a courtesy to tell housemates or colleagues a camera app is running.

On calls, if you use speakers rather than headphones, the beep can reach your microphone, so Sound Alarm off and Visual Alarm on is a sensible meeting setup. For how visible your hands are to everyone else, see [camera angles and self-view on video calls](/blog/nail-biting-zoom-calls/).

## Why it alerts while you eat (and what to do about it)

Because Nailed only measures fingertip-to-mouth distance, anything that parks a hand at your mouth looks the same to it: eating with your fingers, resting your chin on your hand, yawning or coughing behind your hand, holding a phone with your fingers near your lips, sipping from a cup held close. That isn't a bug, and there's no sensitivity setting to tune it away. What you can do:

- **Snooze around meals.** Snooze pauses detection for 5, 10, 15, or 30 minutes without switching monitoring off. Snooze Preference sets the default length, the menu shows the time remaining, and Stop Snooze ends it early.
- **Split the alerts.** Sound Alarm and Visual Alarm switch on and off independently, and both settings survive a restart. Overlay only suits calls; sound only suits stretches when you look away from the screen.
- **Treat a chin-rest alert as information.** If resting your fingers at your lips is part of how your biting starts, an alert there is arguably doing its job.

If frequent beeps feel like too much, sound off with the overlay on is the gentlest option.

## Why it misses a bite

- **Monitoring isn't on.** Nailed always launches idle, even with Launch at Login turned on; you click Start Monitoring each session. Closing its windows doesn't quit it, and it never starts watching by itself.
- **It's snoozed, or both alarms are off.** The menu shows a countdown while snoozed. With Sound Alarm and Visual Alarm both unchecked, it can be monitoring with nothing to see or hear.
- **Wrong camera.** The choice resets every launch. With the built-in camera selected, [a green light beside it glows whenever the camera is on](https://support.apple.com/en-gb/guide/mac-help/mchlf6d108da/mac); if that light is off, Nailed isn't getting a picture.
- **No camera permission.** If you declined the first prompt, turn access back on in System Settings > Privacy & Security > Camera (System Preferences > Security & Privacy > Privacy on Monterey), as the same Apple guide describes.
- **Out of frame or badly lit.** You turned toward another screen, leaned back so your hand rose from below the picture, hid your hand behind a mug, or sat with a strong light behind you.
- **Very quick bites.** A fast nibble that's over before several checks catch it can slip through.
- **Someone else in view.** See shared rooms, above.

## Settings worth knowing

Everything lives in the menu bar icon; there's no Dock icon or main window. Sound Alarm, Visual Alarm, and Snooze Preference are remembered between launches; the camera choice and monitoring state are not. Launch at Login opens the app at login without starting monitoring. After a handful of alerts, Nailed asks once whether you'd like to rate it. There's no dashboard, history, streak counter, or Notification Center banner.

## What Nailed does not do

- **Other body-focused habits.** It watches for a hand near your mouth and nothing else: not skin picking or cuticle picking with your fingers, hair pulling, or touching other parts of your face. Picking a cuticle with your teeth looks like biting and will alert; picking in your lap below the desk edge is out of view for any webcam.
- **Stats, sensitivity settings, or multiple faces.** No history or charts, no slider, one face and one camera at a time. The interface is English only.
- **Anything away from your Mac.** It helps only while you're at the Mac, monitoring and not snoozed. There's no iPhone, iPad, Windows, Linux, Android, or web version. If most of your biting happens on the sofa or in the car, [a wearable may fit better than a camera](/blog/wearable-vs-camera-tracking/).
- **Diagnosis or treatment.** Nailed is not a medical device. It's an awareness cue; what you do after the alert is what changes the habit. [Competing response training](/blog/competing-response-training/) is a practical place to start, as is having [a short script ready for the seconds after the screen flashes](/blog/what-to-do-when-you-catch-yourself-biting/).

If biting is causing pain, bleeding, or lasting damage, or you can't cut down despite trying, talk to a GP or dermatologist, or look for a therapist trained in habit reversal training (HRT) or the Comprehensive Behavioral (ComB) model. The [TLC Foundation for BFRBs](https://www.bfrb.org/post/evidence-based-therapeutic-treatment-for-bfrbs) describes both and names awareness training as a core part of HRT. And if the skin around a nail becomes sore, red, swollen, and warm, the [NHS notes](https://www.nhs.uk/symptoms/nail-problems/) that can be a sign of infection — get it checked rather than waiting it out.

## Is it free, and what's the catch?

Yes: Nailed is free on the Mac App Store. There's no account to create, no ads, and no analytics, and the listing's privacy label reads "Data Not Collected." Detection runs on your Mac without an internet connection and no images are saved. The only outbound connections are links you click yourself: the rating page, terms, privacy policy, and support email. It needs macOS 12 or later, a Mac with an Apple M1 chip or later, and a camera.

The honest catch is the list above: it only helps at your Mac, you click Start each session and re-pick an external camera after a restart, and it will interrupt some lunches. If that fits your day, it's on the [Mac App Store](https://apps.apple.com/app/nailed-stop-biting-nails/id6761733224). If you already have it and it seems broken, run the framing check first.

## Frequently Asked Questions

{{< faq >}}

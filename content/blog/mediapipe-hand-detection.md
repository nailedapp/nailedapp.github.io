---
title: "How MediaPipe Powers Real-Time Hand Detection"
description: "A technical look at how Google's MediaPipe framework detects hands in real time. Learn about hand landmarks, face detection, and how Nailed uses it."
date: 2026-03-29
slug: mediapipe-hand-detection
keywords:
  - MediaPipe hand detection
  - MediaPipe pose detection
  - hand landmark detection
  - Google MediaPipe
faq:
  - q: "What is MediaPipe?"
    a: "MediaPipe is an open-source framework from Google that provides pre-trained machine learning models for real-time perception tasks. It includes models for hand tracking, face detection, pose estimation, object detection, and more. The models are optimized to run on-device without needing a server."
  - q: "How many points does MediaPipe track on each hand?"
    a: "MediaPipe's hand landmark model tracks 21 key points per hand. These include four points on each finger (tip, DIP, PIP, MCP joints), plus the wrist. Together, these landmarks give a detailed 3D model of hand position and finger articulation."
  - q: "Can MediaPipe run in a web browser?"
    a: "Yes. MediaPipe models can be compiled to WebAssembly (WASM) and run in browser environments or Electron-based apps. This is how Nailed runs MediaPipe on macOS — through a WebAssembly runtime that processes camera frames locally without any server communication."
  - q: "Does MediaPipe need an internet connection?"
    a: "No. Once the model files are downloaded (they ship with the app), MediaPipe runs entirely offline. All inference happens on your device's hardware. No camera data or detection results are sent anywhere."
---

Google released MediaPipe as an open-source framework in 2019. Since then, it's become one of the most widely used tools for real-time perception — the kind of machine learning that analyzes camera feeds, detects body parts, and tracks movement.

What makes MediaPipe different from most ML frameworks: it's built for speed on consumer hardware. Not server GPUs. Not cloud clusters. Your laptop, your phone, your tablet.

Here's how it works.

## The Problem MediaPipe Solves

Detecting a hand in a camera frame is computationally expensive. A single 640×480 frame contains 307,200 pixels, each with three color channels. That's nearly a million values. Doing this 30 times per second means processing ~28 million values every second — and that's before any actual detection logic runs.

Traditional computer vision approaches (pre-deep-learning) used techniques like skin color detection and contour analysis. These were fast but fragile. Change the lighting, add a complex background, or vary skin tone, and accuracy collapsed.

Deep learning solved the accuracy problem but created a speed problem. Neural networks that could reliably detect hands needed millions of parameters and significant compute. Running them in real time on a laptop wasn't practical.

MediaPipe solved both. Google's research team designed neural network architectures specifically optimized for real-time inference on consumer hardware — small enough to run fast, accurate enough to be useful.

## Hand Landmark Detection: 21 Points Per Hand

MediaPipe's hand landmark model is a two-stage pipeline.

**Stage 1: Palm detection.** A lightweight neural network scans the full camera frame to locate palms. Palms are easier to detect than full hands because they're rigid and have a consistent shape regardless of finger position. This model outputs a bounding box around each detected palm.

**Stage 2: Hand landmark regression.** A second model takes the cropped palm region and predicts 21 landmark points in 3D space. These landmarks map to specific anatomical points:

- **Wrist** (1 point)
- **Thumb**: CMC, MCP, IP, tip (4 points)
- **Index finger**: MCP, PIP, DIP, tip (4 points)
- **Middle finger**: MCP, PIP, DIP, tip (4 points)
- **Ring finger**: MCP, PIP, DIP, tip (4 points)
- **Pinky**: MCP, PIP, DIP, tip (4 points)

Each landmark includes x, y, and z coordinates. The x and y values represent position in the image frame. The z value estimates depth relative to the wrist, giving a rough 3D hand model.

The two-stage approach is a performance optimization. Palm detection runs on the full frame but is lightweight. Landmark regression is more compute-intensive but only runs on the small cropped region around each palm. After the first frame, the system can often track the hand between frames and skip palm detection entirely, only re-running it when tracking is lost.

## Face Landmark Detection: 478 Points

MediaPipe also provides a face landmark model that detects 478 points on a face. These landmarks map the face mesh in detail — eyes, eyebrows, nose, lips, jawline, and cheeks.

For applications that need to understand the relationship between hands and face (like detecting nail biting), combining hand and face landmarks provides the necessary spatial data. You know where each fingertip is. You know where the mouth is. Determining whether a hand is near the mouth becomes straightforward geometry.

## The Inference Pipeline

Here's what happens in a single frame of MediaPipe processing:

1. **Frame capture**: Camera provides a raw image frame (typically 640×480 or 1280×720)
2. **Preprocessing**: Image gets resized and normalized to the model's expected input format
3. **Palm detection**: First neural network scans for palms (or uses tracking from previous frame)
4. **Region cropping**: Bounding box around each palm extracts a smaller image region
5. **Landmark inference**: Second neural network predicts 21 landmark coordinates per hand
6. **Face detection** (if enabled): Separate model detects face landmarks
7. **Post-processing**: Raw model outputs get converted to usable coordinates
8. **Output**: Application receives structured landmark data with confidence scores

This entire pipeline completes in 10-30 milliseconds on modern hardware, enabling 30+ FPS real-time tracking.

## WebAssembly: Running ML in a Sandbox

MediaPipe models can be compiled to WebAssembly (WASM), a binary instruction format that runs in a sandboxed virtual machine. Originally designed for web browsers, WASM has become a popular way to run high-performance code in controlled environments.

Key properties of WASM for ML inference:

- **Near-native speed**: WASM typically runs within 10-20% of native code performance
- **Sandboxed execution**: The WASM runtime can't access anything outside its sandbox without explicit permission
- **Cross-platform**: Same binary runs on any platform with a WASM runtime
- **No installation**: Models ship as WASM binaries bundled with the application

For privacy-focused applications, WASM's sandboxing is a security bonus. The ML model literally cannot access the network or file system unless the host application explicitly grants that access.

## How Nailed Uses MediaPipe

Nailed is a macOS menu bar app that detects nail biting in real time. Here's how it applies MediaPipe's capabilities:

**Detection pipeline:**

Nailed runs MediaPipe's hand landmarker and face landmarker models simultaneously. Each camera frame gets processed through both models. The app then calculates the spatial relationship between hand landmarks (particularly fingertip positions) and face landmarks (particularly mouth position).

When fingertips are detected within a threshold distance of the mouth — and the hand configuration matches a biting gesture — Nailed triggers an alert: a screen flash and an audible beep.

**Technical implementation:**

- Models are compiled to WebAssembly and bundled with the app
- Inference runs in Electron's renderer process
- Camera frames are processed locally — never transmitted
- Both hand and face models run on each frame for accurate spatial analysis
- The app detects the specific gesture pattern of nail biting, not just hand-near-face proximity

**Performance profile:**

Running two MediaPipe models simultaneously (hand + face landmarks) on every camera frame is demanding, but modern Mac hardware handles it well. Apple Silicon Macs (M1 and later) process the pipeline comfortably due to their efficient GPU and Neural Engine. Even older Intel Macs with decent GPUs can maintain real-time detection rates.

Because Nailed runs as a menu bar app, it needs to be lightweight enough to run continuously in the background without draining the battery or hogging the CPU. MediaPipe's optimized model architecture makes this feasible in a way that larger, less optimized models wouldn't be.

## What Makes MediaPipe Different From Other ML Frameworks

Several frameworks offer hand detection and pose estimation. Here's how MediaPipe compares:

**MediaPipe vs. OpenPose:** OpenPose was a pioneer in real-time pose estimation but is significantly heavier computationally. It's designed for multi-person full-body pose estimation, which is overkill for single-user hand tracking. MediaPipe's hand-specific models are faster and more accurate for hand-only use cases.

**MediaPipe vs. Core ML:** Apple's Core ML is macOS/iOS-specific and integrates tightly with Apple hardware. MediaPipe is cross-platform. For apps targeting only Apple platforms, Core ML is a solid choice. For apps that might expand to other platforms (or that use Electron), MediaPipe offers more flexibility.

**MediaPipe vs. TensorFlow Lite:** TFLite is a general-purpose framework for running any model on-device. MediaPipe is built on top of TFLite but adds pre-trained, optimized models and a complete inference pipeline. Using MediaPipe for hand detection means you don't need to train your own model or build your own pre/post-processing pipeline.

**MediaPipe vs. custom models:** You could train your own hand detection model from scratch. But MediaPipe's hand landmark model was trained on a massive dataset with extensive augmentation. Replicating that quality with a custom model would require significant time, data, and ML expertise. For most applications, MediaPipe's pre-built models are the practical choice.

## The Broader Landscape

MediaPipe isn't limited to hands and faces. Google provides models for:

- **Pose estimation**: 33 body landmarks for full-body tracking
- **Object detection**: Identify and locate objects in a scene
- **Image segmentation**: Separate foreground from background
- **Text classification**: Analyze text content
- **Audio classification**: Identify sounds and speech

Each model follows the same design philosophy: optimized for real-time on-device inference, available as pre-trained weights, and deployable through multiple runtimes including WebAssembly.

For developers building applications that need real-time perception — and especially those who care about user privacy — MediaPipe provides a production-ready foundation that would take years to build from scratch.

## Trying It in Practice

If you want to see MediaPipe hand detection in action as part of a finished product, Nailed uses it to detect and interrupt nail biting in real time. The app sits in your Mac's menu bar, processes your webcam feed locally through MediaPipe's hand and face landmark models, and alerts you when it detects a biting gesture.

Everything runs on your Mac. No cloud. No data collection. No subscription — [$4.99 on the Mac App Store](https://apps.apple.com/app/nailed-stop-biting-nails/id6761733224).

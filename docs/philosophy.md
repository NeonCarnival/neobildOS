# Philosophy

## Digital Sovereignty

A device you don't control is a device that controls you.

Modern Android ships with Google Play Services as a mandatory dependency. This means authentication, location, push notifications, and increasingly AI features run through Google's infrastructure. The user has no visibility into what is sent, when, or to whom.

neobildOS removes that dependency entirely. Every function that the OS provides runs locally. The network is optional, not required.

Sovereignty means: the device owner holds all keys, all data, and all compute. No third party has access without explicit, auditable action by the owner.

---

## De-Googled Android

Android is open source. Google's layer on top of it is not.

AOSP — the Android Open Source Project — is the base. It runs without Google. Most features work. What breaks without Google is intentional lock-in, not technical necessity.

neobildOS builds on AOSP. It replaces or removes:

- Google Play Services
- Google Mobile Services (GMS)
- Google Play Store
- Firebase integrations
- SafetyNet / Play Integrity attestation

Replacements are selected for auditability and offline capability. Nothing is added that cannot be inspected.

---

## Local LLM Inference Without Cloud

Language models do not require a data center.

Quantized models run on mid-range Android hardware today. 7B parameter models at 4-bit quantization fit in 4–6 GB of RAM. Inference is slow compared to cloud — it is fast enough to be useful.

The trade is acceptable: higher latency, complete privacy.

neobildOS uses MNN (Alibaba Mobile Neural Network) as the inference runtime. It runs on CPU and GPU without cloud dependencies. Models are shipped with the OS or sideloaded by the user.

No prompt leaves the device. No API key is required. No account is needed.

---

## Built and Operated From a Single Android Phone

The build environment is Termux.

This is a constraint by design. If the tooling requires a Linux workstation, it creates a dependency that most users in restricted environments cannot meet. Termux runs on the target hardware. Build scripts that work in Termux work on the device being built for.

This forces minimalism. Heavy build systems that require 32-core machines are out of scope. Scripts must be auditable line by line. Dependencies must be installable via `pkg` or compiled locally.

The goal: a user with one Android phone and a Termux session can understand, modify, and rebuild the entire stack.

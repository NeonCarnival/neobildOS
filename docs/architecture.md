# Architecture

## Overview

neobildOS is layered. Each layer is independently replaceable.

```
┌─────────────────────────────┐
│         User Apps           │  F-Droid, sideloaded APKs
├─────────────────────────────┤
│      Local AI Layer         │  MNN runtime + quantized models
├─────────────────────────────┤
│     OS Services Layer       │  De-Googled AOSP services
├─────────────────────────────┤
│         AOSP Base           │  Patched Android Open Source Project
├─────────────────────────────┤
│         Kernel              │  Linux kernel (device-specific)
└─────────────────────────────┘
```

---

## Components

### AOSP Base
Forked from AOSP. Google services stripped at the build level, not patched over. Patches tracked in `patches/`.

### OS Services Layer
Replacement services for anything removed with Google:
- Push: Local notification broker (no FCM)
- Location: GPS-only, no network location provider
- Auth: Local key storage, no Google account dependency

### Local AI Layer
MNN handles inference. Models are quantized to 4-bit or 8-bit. Loaded on demand, unloaded when idle. No persistent background process required for basic device function.

Model management is explicit — the user installs and removes models. No automatic downloads.

### Build Environment
Termux provides the build shell. Scripts in `stack/termux/` configure the environment. All dependencies are declared explicitly.

---

## Design Constraints

- No network call is mandatory for core OS function.
- No binary blob is included without documented purpose.
- Build scripts run in Termux on the target device class.
- Each component documents its attack surface.

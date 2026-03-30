# neobildOS

**A sovereign Android experience — no Google, no cloud dependency, local AI built in.**

---

## Vision

neobildOS is a de-Googled Android operating system with local LLM inference built into the core stack. No cloud calls. No data leaving the device. No dependency on remote infrastructure.

The project is built and operated from a single Android phone via Termux. That constraint is intentional — if it can't run on the device it targets, it doesn't belong in the stack.

---

## Core Principles

- **Sovereignty first.** The device owner controls all compute, all data, all keys.
- **No cloud by default.** Every feature works offline. Cloud is never assumed.
- **Local inference only.** AI runs on-device via quantized models. No API calls.
- **Minimal dependencies.** Each layer of the stack is auditable and replaceable.
- **Phone-native development.** Built on Termux. Tested on the target hardware.

---

## Stack

| Component | Role |
|-----------|------|
| `stack/termux/` | Bootstrap scripts, package lists, build environment |
| `stack/mnn/` | On-device inference runtime (Alibaba MNN) |
| `stack/openclaw/` | Custom tooling layer |
| `patches/` | AOSP and ROM patches |
| `releases/` | Build artifacts and changelogs |

---

## Roadmap

### Phase 1 — Documentation + Stack Scripts
Define architecture. Write build environment scripts. Document the full stack. No ROM builds yet.

### Phase 2 — AOSP Fork + De-Googling
Fork AOSP. Strip Google services. Apply patches. First flashable build.

### Phase 3 — Integrated Local LLM Builds
Integrate MNN inference into the OS stack. Ship quantized models with the ROM. Local AI as a first-class feature.

---

## Status

**Early development — Phase 1 documentation.**

No flashable builds yet. Stack scripts and documentation in progress.

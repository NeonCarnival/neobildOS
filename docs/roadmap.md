# Roadmap

## Phase 1 — Documentation + Stack Scripts

**Goal:** Define the full stack. Write the build environment. No ROM builds.

- [ ] Architecture documentation
- [ ] Philosophy documentation
- [ ] Termux bootstrap scripts (`stack/termux/`)
- [ ] MNN build instructions for Termux (`stack/mnn/`)
- [ ] openclaw tooling layer initial design (`stack/openclaw/`)
- [ ] Patch format and workflow defined (`patches/`)
- [ ] Release format defined (`releases/`)

**Output:** A developer can read the docs and reproduce the build environment on a stock Android device with Termux.

---

## Phase 2 — AOSP Fork + De-Googling

**Goal:** First flashable build. No Google. Boots. Core apps work.

- [ ] AOSP fork created and tracked
- [ ] Google Play Services removed at build level
- [ ] GMS dependencies audited and replaced or removed
- [ ] F-Droid pre-installed as app source
- [ ] GPS-only location stack
- [ ] Local notification broker (no FCM)
- [ ] First test flash on reference device
- [ ] Patch set documented in `patches/`
- [ ] First release artifact in `releases/`

**Output:** A flashable ROM image. No Google account required. No cloud calls on boot.

---

## Phase 3 — Integrated Local LLM Builds

**Goal:** Local AI as a first-class OS feature. Ships with the ROM.

- [ ] MNN runtime integrated into AOSP build
- [ ] Default quantized model selected and licensed
- [ ] Model bundled in ROM image or delivered via verified sideload
- [ ] System-level inference API (no internet required)
- [ ] Basic AI features using local inference only:
  - Text summarization
  - On-device search assist
  - Local voice-to-text (offline)
- [ ] Model update mechanism (local, user-controlled)
- [ ] RAM/storage usage documented per device class

**Output:** A ROM that ships with working local AI. No API keys. No accounts. No cloud.

---

## Out of Scope (Permanently)

- Google account integration
- Cloud-dependent features
- Proprietary model APIs
- Any telemetry or analytics

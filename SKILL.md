---
name: seedance-20
description: "This skill should be used when directing Seedance 2.0 T2V, I2V, V2V, R2V, audio, safety, or API work."
license: MIT
user-invocable: true
tags: [seedance]
metadata:
  version: "5.4.3"
---

# seedance-20

Seedance 2.0 operating loop for agent-directed video work. Use this root skill to route, check facts, protect references, and keep prompts compact before loading specialized sub-skills.

## Operating Loop

1. Intake: identify the user's goal, target surface, mode, duration, aspect ratio, references, audio needs, and safety/IP risks.
2. Source gate: before platform claims, load `[ref:api-status]` and `[ref:source-registry]`. For Runway or Volcengine specifics, also load `[ref:platform-surface-matrix]`.
3. Mode gate: choose T2V, I2V, V2V, R2V, FLF2V, edit, extend, or troubleshoot before writing prose.
4. Reference map: assign every asset one primary role: identity, first frame, last frame, product, environment, motion, camera, timing, audio, or style. State what must not transfer.
5. Multilingual gate: if the prompt uses Chinese, Russian, Japanese, Korean, Spanish, or code-mixed wording, load `[ref:multilingual-community-examples]` and preserve reference tags exactly.
6. Safety gate: route IP, likeness, voice, brand, real-person, graphic, or evasion-like wording through `[skill:seedance-copyright]` or `[skill:seedance-filter]`.
7. Prompt build: route to `[skill:seedance-interview]`, `[skill:seedance-prompt]`, `[skill:seedance-prompt-short]`, or a domain skill for camera, motion, audio, characters, VFX, style, recipes, or pipeline.
8. Quality pass: run anti-slop, check one visible beat, one primary camera move, physical light, sound intent, constraints, and source-date caveats.
9. Repair loop: if output fails, diagnose root cause before adding adjectives; use `[skill:seedance-troubleshoot]`.

## Load Map

| Situation | Load |
|---|---|
| Vague idea or missing brief | `[skill:seedance-interview]` or `[skill:seedance-interview-short]` |
| Production prompt | `[skill:seedance-prompt]`, `[ref:quick-ref]`, `[ref:prompt-examples]` |
| Compact prompt or Chinese compression | `[skill:seedance-prompt-short]`, language vocab reference |
| Image reference / first frame | `[ref:i2v-guide]`, `[ref:reference-workflow]` |
| First and last frame | `[ref:first-last-frame-guide]` |
| API, Runway, Volcengine, workflow, pricing, model IDs | `[skill:seedance-pipeline]`, `[ref:api-workflow]`, `[ref:model-name-map]` |
| Genre template or examples | `[skill:seedance-recipes]`, `[ref:examples-by-mode]`, `[ref:genre-guides]` |
| Chinese/Russian/Japanese/Korean/Spanish or mixed-language examples | `[ref:multilingual-community-examples]`, language vocab reference |
| Bad result | `[skill:seedance-troubleshoot]` |

Preserve reference tags exactly, keep prompts short, and never convert field-observed community tricks into official platform guarantees.

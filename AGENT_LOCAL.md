# Repository context: cuda-media

Universal engineering and design guidance comes from the account-global `AGENTS.md`.

## Mission and ownership

CUDA-MEDIA owns reusable image/frame/video/codec-pipeline semantics when accepted: image/frame/plane/pixel-format/colorspace meaning, media crop/resize/resample/convert/composite operations, encode/decode session and frame-queue meaning, finite buffering/backpressure, and provider-neutral media equivalence.

CUDA-JS owns CUDA/provider mechanisms. CUDA-JS-Tensor owns generic Tensor mathematics. NN/computer-vision, renderer/window, and downstream product policy remain with their natural owners.

## Local routing

Accepted `docs/decisions/`, `docs/specs/`, repository status/roadmap, and current issues own local implementation/activation truth.

## Local constraints

Dependency direction is `cuda-media -> public cuda-js`, with optional Tensor use through public contracts. Maintained code uses JavaScript/ESM plus accepted Device-JS; no Python, direct native/provider escape path, or private lower imports.
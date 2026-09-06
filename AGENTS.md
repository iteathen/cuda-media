# CUDA-MEDIA Agent Entry Point

Read before changing the repository. Authority: owner instruction -> this file -> accepted ADRs -> accepted specs -> charter -> status/roadmap/issues.

Use `assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document` and `LEGO -> SOLID -> CUPID -> KISS`.

LEGO is the outer architecture rule: ownership, universality, replaceability, scope containment, damage-limiting encapsulation, supported connection surfaces, and context containment. **The application/system is the outermost LEGO.** Its supported external inputs, outputs, commands, events, data contracts, and lifecycle entry/exit points are its public **studs/surfaces**. Large sections, subsystems, components, and large objects should preferentially compose smaller child LEGOs when that preserves cohesion; the parent owns the external responsibility and hides child topology.

A LEGO is too large when one agent cannot hold its complete authoritative working set—contract/studs/surfaces, implementation, invariants, lifecycle/resource/failure rules, tests/conformance, and immediate dependency/consumer interfaces—in focused attention with substantial headroom for reasoning and review. Context fit is a first-class boundary criterion alongside semantic, lifecycle, resource/failure, substitution, and change cohesion. When exceeded, recursively split at the strongest real seam or narrow scope; do not create arbitrary modules that duplicate truth or require cross-boundary internal knowledge. Callers connect through deliberate studs/surfaces and never drill through a parent to a private child. Inside a valid LEGO, SOLID structures responsibilities and dependency direction, CUPID shapes the implementation, and KISS removes remaining unjustified complexity; lower levels may not defeat higher ones.

CUDA-MEDIA owns reusable image/frame/video/codec-pipeline semantics when separately accepted: image/frame/plane/pixel-format/colorspace meaning, media-specific crop/resize/resample/convert/composite operations, encode/decode session and frame-queue meaning, finite buffering/backpressure and provider-neutral media equivalence.

CUDA-MEDIA does not own generic Tensor math, NN/computer-vision semantics, renderer/window/swapchain/product policy, CUDA memory/views/operations/provider lifecycle, or raw NPP/nvJPEG/NVENC/NVDEC handles/ABI.

CUDA-JS owns bounded native media-provider mechanisms when selected. CUDA-JS-Tensor owns generic mathematical operations even when used to realize media behavior. Dependency direction is `cuda-media -> public cuda-js`, with optional Tensor use through public contracts.

Direct native/FFI/CUDA C++/PTX/private imports or duplicated provider lifecycle are lower-layer ownership signals. Maintained code, when authorized, is JavaScript/ESM plus accepted restricted Device-JS; no Python or native escape path without a successor decision.

Repository creation authorizes no production source/API. #3 is the media semantic roadmap; #2 owns repository-control/protected-main alignment. Accepted bounded specs are required before implementation.

Completion requires exact-effect review, relevant qualification, cleanup and honest support/performance claims.
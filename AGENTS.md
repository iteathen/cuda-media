# CUDA-MEDIA Agent Entry Point

Read before changing the repository. Authority: owner instruction -> this file -> accepted ADRs -> accepted specs -> charter -> status/roadmap/issues.

Use `assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document` and `LEGO -> SOLID -> CUPID -> KISS`.

CUDA-MEDIA owns reusable image/frame/video/codec-pipeline semantics when separately accepted: image/frame/plane/pixel-format/colorspace meaning, media-specific crop/resize/resample/convert/composite operations, encode/decode session and frame-queue meaning, finite buffering/backpressure and provider-neutral media equivalence.

CUDA-MEDIA does not own generic Tensor math, NN/computer-vision semantics, renderer/window/swapchain/product policy, CUDA memory/views/operations/provider lifecycle, or raw NPP/nvJPEG/NVENC/NVDEC handles/ABI.

CUDA-JS owns bounded native media-provider mechanisms when selected. CUDA-JS-Tensor owns generic mathematical operations even when used to realize media behavior. Dependency direction is `cuda-media -> public cuda-js`, with optional Tensor use through public contracts.

Direct native/FFI/CUDA C++/PTX/private imports or duplicated provider lifecycle are lower-layer ownership signals. Maintained code, when authorized, is JavaScript/ESM plus accepted restricted Device-JS; no Python or native escape path without a successor decision.

Repository creation authorizes no production source/API. #3 is the media semantic roadmap; #2 owns repository-control/protected-main alignment. Accepted bounded specs are required before implementation.

Completion requires exact-effect review, relevant qualification, cleanup and honest support/performance claims.
# CUDA-MEDIA Project Charter

**Status:** Accepted architecture after bootstrap integration; production implementation not authorized.

## Purpose

Own reusable provider-neutral image/frame/video/codec-pipeline semantics without turning CUDA-JS into a media framework or turning Tensor into an image/video domain library.

## Owns, when separately accepted

- image/frame/plane/pixel-format/colorspace semantics;
- media-specific crop/resize/resample/convert/composite meaning;
- encode/decode session, frame queue and bounded buffering/backpressure;
- reusable codec/profile/timestamp/rate-control meaning selected by bounded contracts;
- provider-neutral equivalence and media-specific conformance.

## Does not own

Generic Tensor math; NN/computer-vision/model semantics; renderer/window/swapchain/material/product policy; CUDA memory/views/streams/events/operations; or native NPP/nvJPEG/NVENC/NVDEC provider handles/ABI/lifecycle.

## Provider boundary

CUDA-JS owns lower native/provider mechanisms. CUDA-MEDIA maps reusable media semantics over them. Generic Tensor operations remain CUDA-JS-Tensor even when an image/video operation is implemented using them.

## Dependency direction

`cuda-media -> public cuda-js`; optional public Tensor composition when mathematically natural.

## Activation gate

Issue #3 keeps image and video lanes separable and requires a concrete consumer before any accepted production contract.

## Non-goals

Renderer, computer-vision framework, arbitrary codec passthrough, provider implementation, or universal media breadth before a bounded baseline.
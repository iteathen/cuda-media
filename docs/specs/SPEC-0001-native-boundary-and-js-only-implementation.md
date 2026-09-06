# SPEC-0001: Native Boundary and JavaScript/TypeScript Implementation

**Status:** Accepted architecture/ownership authority; production media profiles remain separately gated.

**Version:** 1.0.0

**Owner:** CUDA-MEDIA

**Lower authority:** `iteathen/CUDA-JS` SPEC-0032

## Purpose

CUDA-MEDIA owns reusable image/frame/video/codec-pipeline semantics. CUDA-JS is the sole native CUDA/provider integration owner.

## Repository implementation rule

Maintained CUDA-MEDIA source is JavaScript/TypeScript. Restricted Device-JS generation is permitted only through public CUDA-JS contracts.

CUDA-MEDIA does not maintain C, C++, CUDA C++, PTX, direct native FFI, native addons, NPP/nvJPEG/NVDEC/NVENC bindings, external-memory handles, native pointers/ABI structs or platform discovery code. Native evidence may be produced externally and recorded, but native oracle/provider source is not maintained here.

A missing native mechanism routes to CUDA-JS before any local workaround.

## CUDA-MEDIA owns

- image/frame/plane/pixel-format/colorspace meaning;
- crop/resize/resample/convert/composite semantics where media-specific;
- video codec/profile/timestamp/frame-queue semantics;
- bounded buffering/backpressure and GPU-resident handoff meaning;
- media-specific provider eligibility/equivalence/fallback;
- JavaScript/TypeScript reference and conformance evidence.

## CUDA-JS owns

- native allocations/views/transfers and device/context resources;
- external-memory/semaphore/graphics interoperability mechanisms;
- NPP/nvJPEG/NVDEC/NVENC or other native provider mechanisms if selected;
- native provider handles, operations, errors and teardown.

A graphics/display consumer may use CUDA-JS interop, but renderer/window/swapchain/canvas semantics remain outside CUDA-MEDIA unless separately accepted by their natural owner.

## Memory-policy boundary

Media-specific frame buffering and pipeline backpressure may remain CUDA-MEDIA-owned. Generic cross-domain allocation pooling, placement, reuse, migration or spill policy requires its own JavaScript/TypeScript owner if independently justified and must consume public CUDA-JS.

## Activation gate preservation

This specification does not select an image/video operation or provider and does not authorize production media APIs.

## Non-goals

No native media backend, no renderer, no arbitrary provider passthrough, no production capability or support claim.

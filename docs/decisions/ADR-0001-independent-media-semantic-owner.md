# ADR-0001: Independent Media Semantic Owner

**Status:** Accepted
**Date:** 2026-09-02

## Context

CUDA-JS already contemplates NPP/nvJPEG-class provider mechanisms, and NVIDIA video encode/decode uses dedicated NVENC/NVDEC engines. Image/frame/colorspace/codec-session meaning is reusable across applications but is neither generic CUDA runtime meaning nor generic Tensor mathematics.

## Decision

`cuda-media` owns reusable provider-neutral media semantics. CUDA-JS retains native provider/resource lifecycle. CUDA-JS-Tensor retains generic math. NN/rendering/product semantics remain external.

## Deletion test

Deleting a model, renderer or product leaves CUDA-MEDIA coherent; deleting CUDA-MEDIA leaves CUDA-JS and Tensor coherent general-purpose libraries.

## Implementation gate

Issue #3 must select a bounded image or video profile before source/API implementation. Provider availability alone is not authority.

## Consequences

Image/video semantics gain one owner without bloating CUDA-JS or Tensor, while accelerated providers remain replaceable realization mechanisms.
# CUDA-MEDIA Status

**Updated:** 2026-09-06

**Architecture/ownership:** accepted independent media semantic owner under SPEC-0001.
**Production implementation/API:** not authorized / none.
**Native/provider support:** none claimed.

## Current work

- #1 ownership/bootstrap authority — completed.
- #2 repository-control/protected-main alignment — completed; `main` is protected and the selected CUDA-family settings were read back.
- #3 is the current image-processing and video-codec activation roadmap; it remains planning/assessment authority, not a production specification.

## Next executable decision

Select one concrete consumer-backed lane—image or video—and accept the smallest bounded semantic profile before production implementation. The lanes remain independently activatable; provider availability in one does not authorize the other.

Generic Tensor mathematics stays in CUDA-JS-Tensor. CUDA-JS owns native memory/graphics/media-provider/resource mechanisms. Model/computer-vision semantics remain product-owned unless a future reusable NN layer is independently reactivated; renderer/window/swapchain/product policy stays external.

`iteathen/CUDA-MM` is now the accepted **reserved architecture/ownership home** for reusable cross-domain physical memory-management policy. It is not a current CUDA-MEDIA dependency: CUDA-MM #3/#4 and a separately accepted bounded contract must activate production first. CUDA-MEDIA retains image/frame/pixel/codec semantics and media-specific buffer/lifetime requirements; generic placement/pooling/spill/migration strategy may route to CUDA-MM only after activation.

## Governance

Protected-main and repository-setting alignment is complete. No local CI workflow currently exists, so no required status-check name is fabricated.

No roadmap entry, provider availability, CUDA-MM repository existence or completed governance bootstrap is production implementation authority.

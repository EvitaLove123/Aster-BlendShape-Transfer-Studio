# Aster BlendShape Transfer Studio

Android-first, light-theme browser tool for transferring facial BlendShapes between **VRM 0.x models only**.

## Scope
- Input: VRM 0.x (.vrm) only
- Output target: VRM 0.x (.vrm) only
- No VRM 1.0, PMX, FBX, or GLB workflow
- Browser-side processing; model files are not uploaded to a server

## Current build
- [x] Light responsive interface
- [x] Import two VRM 0.x files
- [x] Validate GLB container and legacy VRM extension/version
- [x] Read VRM 0.x BlendShape Groups and bind metadata
- [x] Count mesh morph targets and compare group names
- [ ] Direct transfer for compatible topology
- [ ] Cross-topology surface transfer
- [ ] Preview transferred expressions
- [ ] Export VRM 0.x while preserving target-model data

## Run
Open `index.html` from a static web host such as GitHub Pages or Vercel. No build step is required for the current inspection prototype.

## Important
The current build is an inspection prototype. It does not yet modify or export VRM files. Transfer and export will be implemented and tested as separate milestones to avoid damaging the target model's skeleton, materials, textures, SpringBone, collider, and other VRM metadata.

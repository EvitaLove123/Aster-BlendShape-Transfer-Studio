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
- [x] Facial BlendShape transfer for one selected source/target mesh pair
- [x] Cross-topology surface-aware transfer using nearby source triangles and barycentric interpolation
- [x] Create target Morph Targets and VRM 0.x BlendShape Groups
- [x] Export VRM 0.x while retaining the target model's existing GLB/VRM data
- [ ] Interactive expression preview and per-group strength controls

## Transfer workflow
1. Load Model A (source) and Model B (target), both VRM 0.x.
2. Select exactly one source face mesh and one target face mesh.
3. Choose the facial BlendShape Groups to copy from Model A.
4. Run **Transfer Face BlendShapes**, then export Model B.

The transfer samples the closest source vertex, examines its adjacent source triangles, and interpolates morph deltas with barycentric weights onto target vertices. It supports different vertex counts/topologies, but it is approximate and depends on compatible face orientation and proportions. Inspect the exported expressions in a VRM viewer before using the model.

## Run
Open `index.html` from a static web host such as GitHub Pages or Vercel. No build step is required for the current inspection prototype.

## Important
Transfer/export is implemented in-browser. The transfer appends morph target accessors and VRM 0.x blendShape groups to Model B; it does not intentionally replace Model B's skeleton, materials, textures, SpringBone, colliders, or unrelated metadata. Always test the exported VRM in your target apps before relying on it.

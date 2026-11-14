# Known issues and limits (version 1.1.0, unreleased)

* Animations: position, rotation and scale channels are imported. Effect (sound/particle/timeline) keyframes, armature bones, texture animation, formats that use quaternion rotation interpolation, loop-wrapped interpolation and Molang beyond a small subset (`math.sin/cos/abs/sqrt/clamp/min/max/lerp/floor/ceil/round`, `query.anim_time`) are not supported. Rotations are sampled (default 30 fps). Only synthetic animations have been tested.
* Display transforms, collections and constraints are ignored.
* Box-UV-only cubes (no saved per-face UV rectangles) are not mapped from `uv_offset`: the faces get full-texture UVs and **no warning is shown**.
* Freeform mesh faces use fan triangulation: only triangles, quads and convex polygons are reliable.
* Alpha textures use alpha scissor (hard edge at 0.5), not smooth blending.
* Texture tint, emissive/PBR maps and cube stretch/rescale are not imported.
* Textures must be inside the project. PNG/JPEG/WebP are read directly; other formats Godot imports (SVG, BMP, TGA...) are linked.
* Blockbench's `.bbmodel` format is internal and can change; future Blockbench versions may need plugin updates.
* Tested only on Godot 4.7.2, with Blockbench 5.0 "free" format models.

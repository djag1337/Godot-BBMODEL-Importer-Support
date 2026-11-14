# Known issues and limits (version 1.1.0)

* Animations: position, rotation and scale channels are imported. Effect (sound/particle/timeline) keyframes, armature bones, texture animation, formats that use quaternion rotation interpolation, loop-wrapped interpolation and Molang beyond a small subset (`math.sin/cos/abs/sqrt/clamp/min/max/lerp/floor/ceil/round`, `query.anim_time`) are not supported. Rotations are sampled (default 30 fps). Only synthetic animations have been tested.
* Display transforms, collections and constraints are ignored.
* Billboards: Blockbench's "look at" and "rotate" facing modes both map to Godot's Enabled billboard (a small perspective difference); "look at Y" and "rotate Y" map to Fixed Y. Billboards are not merged and get no collision.
* Freeform mesh faces use fan triangulation: only triangles, quads and convex polygons are reliable.
* Alpha textures use alpha scissor (hard edge at 0.5), not smooth blending.
* Emissive (glow) and additive render modes are not imported yet: those textures import as normal lit materials. As a workaround, add emission or additive blending to the imported material in Godot. A possible later version; tell me if you want it.
* Texture tint, PBR maps and cube stretch/rescale are not imported.
* Textures must be inside the project. PNG/JPEG/WebP are read directly; other formats Godot imports (SVG, BMP, TGA...) are linked.
* Blockbench's `.bbmodel` format is internal and can change; future Blockbench versions may need plugin updates.
* Tested only on Godot 4.7.2, with Blockbench 5.0 "free" format models.

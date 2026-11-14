# FAQ

**Do I need Blockbench installed?** No. The plugin reads `.bbmodel` files itself.

**Does it import animations?** Yes. Blockbench animations become an `AnimationPlayer` with one animation per Blockbench animation (position, rotation and scale; linear, step, Catmull-Rom and Bezier interpolation; loop modes). A `RESET` animation holds the rest pose. Sound/particle (effect) keyframes are skipped with a warning, and animated models are not mesh-merged. Only synthetic test animations were tested so far, so please report any model whose animation looks wrong.

**Does it support Box UV and billboards?** Yes. Box UV cubes get their face rectangles from the offset (including mirrored UV). Billboards become camera-facing quads using Blockbench's size and offset.

**Does it import armatures (bones), display settings or texture animation?** No. Blockbench groups animate as ordinary nodes; armature bones are not supported.

**Why is my model one mesh instead of many nodes?** *Merge Meshes* is on by default. Turn it off in the Import tab and reimport to keep one node per element.

**My texture is magenta.** The texture file was not found. Keep the image next to the `.bbmodel` or in a `Textures/` folder inside the project, then reimport. The import warning names the missing file.

**My model looks transparent or see-through from some sides.** Check *Materials > Sides*: try Double Sided.

**Does it work with older Blockbench files?** Blockbench 5.0 files were tested. A legacy layout is covered by one test file. Others are not tested.

**Does it work in exported games?** Expected to (the plugin is an editor tool and imported scenes are part of the project), but exports have not been tested by the author yet.

**Which Godot versions?** Tested on 4.7.2 only. Reports from other versions are welcome (use the Compatibility report template).

**Can it create collision?** Yes: *Physics > Collision* in the Import tab: boxes per element, a convex hull, or a trimesh. Hidden elements are ignored.

**What happens to Blockbench locators?** They become `Marker3D` nodes with the locator's name, position and rotation, handy for hold points or attachments.

**My model looks mirrored or its rotated parts are in the wrong place.** Use the default *Axis Mode = Blockbench*. *Legacy (mirrored Z)* exists only to reproduce older pre-release output.

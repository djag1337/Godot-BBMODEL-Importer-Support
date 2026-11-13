# FAQ

**Do I need Blockbench installed?** No. The plugin reads `.bbmodel` files itself.

**Does it import animations?** No. Animation data in the file is ignored; the model's geometry still imports.

**Does it import bones, locators or display settings?** No.

**Why is my model one mesh instead of many nodes?** *Merge Meshes* is on by default. Turn it off in the Import tab and reimport to keep one node per element.

**My texture is magenta.** The texture file was not found. Keep the image next to the `.bbmodel` or in a `Textures/` folder inside the project, then reimport. The import warning names the missing file.

**My model looks transparent or see-through from some sides.** Check *Materials > Sides*: try Double Sided.

**Does it work with older Blockbench files?** Blockbench 5.0 files were tested. A legacy layout is covered by one test file. Others are not tested.

**Does it work in exported games?** Expected to (the plugin is an editor tool and imported scenes are part of the project), but exports have not been tested by the author yet.

**Which Godot versions?** Tested on 4.7.2 only. Reports from other versions are welcome (use the Compatibility report template).

# Installation

1. Download the plugin zip (link at release) and unzip it.
2. Copy the folder `addons/bbmodel_importer` into your project's `addons` folder (create `addons` if needed).
3. In Godot: **Project > Project Settings > Plugins**, tick **Enable** next to *Blockbench BBModel Importer*.
4. Put a `.bbmodel` file anywhere in your project. Godot imports it automatically and it appears in the FileSystem dock as a scene.
5. Drag it into a 3D scene like any GLB. Edit it in Blockbench and save: Godot reimports it.

Import options: click the `.bbmodel` in the FileSystem dock, open the **Import** tab, change options, press **Reimport**.

| Option | Default | Meaning |
|---|---|---|
| Geometry > Units Per Meter | 16 | 16 Blockbench units = 1 meter |
| Geometry > Merge Meshes | on | One mesh per material. Turn off to keep every Blockbench element as a separate node |
| Geometry > Axis Mode | Blockbench | Keeps Blockbench's axes and its ZYX rotation order. *Legacy (mirrored Z)* reproduces the output of pre-release builds |
| Physics > Collision | None | Adds a `BBModelCollision` StaticBody3D: one box per element, a convex hull of the whole model, or a trimesh |
| Nodes > Locators | on | Blockbench locators and null objects become `Marker3D` nodes (hold points, attachments) |
| Materials > Texture Filter | Nearest | Nearest or Linear (both with mipmaps) |
| Materials > Sides | Auto | Auto follows Blockbench's render-sides; or Front Only / Double Sided |

Tested on Godot 4.7.2 (see [Compatibility](COMPATIBILITY.md)).

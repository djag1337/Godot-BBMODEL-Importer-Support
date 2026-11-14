# Troubleshooting

| Symptom | What to try |
|---|---|
| `.bbmodel` files show no scene icon / nothing imports | Is the plugin enabled (Project Settings > Plugins)? Then Project > Reload Current Project. |
| "No loader found for resource ...bbmodel" in the Output | The plugin is not enabled, or the editor has not finished importing. Enable it and wait for the import progress bar. |
| Output says `Texture '...' is missing` | Put the PNG/JPEG/WebP next to the model or in `Textures/`, then Reimport. |
| Textures have the wrong UV mapping | The model may use Blockbench "Box UV" without saved per-face UVs. Not supported yet: in Blockbench switch the model to per-face UV, save, reimport. |
| Parts that should move are merged | Turn off *Geometry > Merge Meshes* and Reimport. |
| Edits in Blockbench do not show up | Save the `.bbmodel`, focus the Godot window so it rescans, or press Reimport. If you changed a texture image, reimport the `.bbmodel` too. |
| Model faces are invisible from one side | *Materials > Sides* to Double Sided. |
| Concave freeform faces look wrong | Triangulate them in Blockbench (only triangles, quads and convex polygons are supported). |
| Model mirrored front-to-back, or multi-axis rotated parts misplaced | Set *Geometry > Axis Mode* to Blockbench and Reimport |
| An animation looks wrong | Check the import warnings (Molang, effect keyframes). Set *Animation > FPS* higher for fast rotations. Please report it with the `.bbmodel` |
| Scale is wrong | *Geometry > Units Per Meter* (default 16). |

When asking for help include: plugin version, Godot version, OS/GPU, Blockbench version, the import warnings, and (if you can share it) a minimal `.bbmodel` that shows the problem.

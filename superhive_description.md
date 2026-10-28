![Auto UV Unwrap](https://KULLANICI.github.io/auto-uv-unwrap/images/01_cover.jpg)

# Clean UVs in one click

**Auto UV Unwrap** marks seams, unwraps and packs your meshes automatically, and then tells you how good the result really is. Select your objects, press **Auto Unwrap**, done. Not happy? One **Ctrl+Z** brings everything back.

No cloud, no AI model, no account. Everything runs **100% offline** on your CPU, inside Blender.

![Auto UV Unwrap intro](https://KULLANICI.github.io/auto-uv-unwrap/media/01_intro.gif)

![One click unwrap and full undo](https://KULLANICI.github.io/auto-uv-unwrap/media/03_one_click_undo.gif)

---

## Why not just Smart UV Project?

Smart UV Project cuts your mesh by angle only, so you get dozens of tiny islands and a lot of stretching. Auto UV's **Smart Parts** engine looks at the shape first: it finds the real parts of the model (ears, eyes, head, handle...), flattens each part, measures the stretch, and only cuts again where it is actually needed.

![Smart UV Project vs Auto UV Smart Parts](https://KULLANICI.github.io/auto-uv-unwrap/images/02_before_after.jpg)

Same mesh, same checker texture, Balanced preset:

| Mesh | Blender Smart UV Project | Auto UV · Smart Parts |
|---|---|---|
| Suzanne | 102 islands · avg distortion 0.208 | **20 islands · avg distortion 0.069** |
| Torus | 10 islands · avg distortion 0.155 | **2 islands · avg distortion 0.044** |
| Rounded cube | 6 islands · avg distortion 0.155 | **4 islands · avg distortion 0.060** |

Every number above was computed live in Blender by the add-on itself.

![Distortion heatmap comparison](https://KULLANICI.github.io/auto-uv-unwrap/images/03_distortion_heatmap.jpg)

---

## Features

**Smart Parts engine**
Part-aware segmentation with distortion-driven splitting. Bad charts are cut and re-flattened until they pass your target; small leftovers are merged back when the stretch allows it.

**Three engines in one panel**
- **Smart Parts** – best quality, fewest islands
- **xatlas** – bundled for all platforms, no install needed
- **Smart UV Project** – Blender's own, as a quick baseline

**Four quality presets**
Fast, Balanced, Quality, or Custom (distortion threshold, split depth, unwrap method, pack shape, merge small charts).

![Engine and quality galleries](https://KULLANICI.github.io/auto-uv-unwrap/media/02_engine_quality.gif)

**Live viewport HUD**
Islands, seams, flipped faces, time, average and max distortion and a mini UV layout preview, drawn right in the 3D view. Toggle it on or off and place it in any corner.

![Viewport HUD](https://KULLANICI.github.io/auto-uv-unwrap/images/09_viewport_hud.jpg)

**Analyze any UV map**
Measure UVs you made by hand, or from any other tool. Optionally writes a distortion color attribute so you can see the stretch on the mesh as a heatmap.

![Analyze UVs and distortion heatmap](https://KULLANICI.github.io/auto-uv-unwrap/media/04_analyze_heatmap.gif)

**Packing that respects your work**
- Packs into 0–1 with a pixel margin calculated from your texture size (256 to 8K)
- Rotate islands for a tighter pack
- **Keep My Seams**: seams you marked yourself are never removed
- Pack many objects into one shared UV space, or each object on its own
- Write into the active UV map or a named one (created if missing)

**Fits the way you work**
- Object Mode (many objects at once) or Edit Mode (only the selected faces)
- Sidebar **N › Auto UV** tab, the **U** menu, UV Editor › UV menu and the Object menu
- One-step undo for UVs, seams, selection and mode

![xatlas engine on a torus](https://KULLANICI.github.io/auto-uv-unwrap/media/05_xatlas_torus.gif)

---

## How it works

![Four steps](https://KULLANICI.github.io/auto-uv-unwrap/images/10_workflow.jpg)

1. Select one or more meshes (or faces in Edit Mode).
2. Open the **Auto UV** tab in the sidebar (N).
3. Pick an engine and a quality preset, then click **Auto Unwrap**.
4. Read the HUD. Want something different? **Ctrl+Z**, change a setting, click again.

![Curved and closed shapes](https://KULLANICI.github.io/auto-uv-unwrap/images/06_curved_shapes.jpg)

---

## Compatibility

- **Blender 4.2 and newer**, tested on Blender 4.5 LTS and 5.2
- **Windows x64, macOS (Apple Silicon and Intel), Linux x64**
- Installs as a standard Blender extension (drag and drop the .zip)
- No internet connection, no extra Python packages, no GPU needed

## What you get

- `auto_uv-1.1.0.zip` – the extension, ready to install on every supported platform

---

*Auto UV Unwrap is GPL-3.0-or-later. The bundled xatlas library is MIT licensed.*

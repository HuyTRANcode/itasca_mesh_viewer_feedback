# Itasca Mesh Viewer

[![Buy Me A Coffee](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://ko-fi.com/htcode)

Interactive VS Code viewer for **Itasca native meshes** (FLAC3D, FLAC2D, 3DEC), **FEM meshes** (Nastran BDF), **TIFF voxel volumes**, and **surface meshes** (OBJ, STL, PLY) — built on VTK.js.

Open any supported file in VS Code and it renders instantly in a custom 3D editor with:
- **Surface, wireframe, and edge rendering** powered by VTK.js
- **Per-zone/group coloring** — FLAC `ZG` zone groups, 3DEC `BGROUP` block groups, Nastran PID property groups
- **Group legend** in the top-right with color swatches
- **Element edge overlay** — draws true cell edges (not triangulation diagonals)
- **Live refresh** on file save
- **Info panel** — vertices, elements/zones/faces, groups, bounds

## Features

## Supported Formats

| Format | Extensions | Description |
|--------|------------|-------------|
| FLAC3D/FLAC2D Grid | `.f3grid`, `.f2grid`, `.grid` | Itasca FLAC2D/FLAC3D native grid format |
| 3DEC Grid | `.3dgrid` | Itasca 3DEC native grid format |
| Nastran BDF | `.bdf`, `.nas`, `.dat`, `.fem` | Nastran bulk data format (volume elements: CHEXA, CTETRA, CPENTA, CPYRAM) |
| TIFF Voxel Volume | `.tif`, `.tiff` | Multi-page TIFF stacks as hexahedral meshes (8/16/32-bit, strip & tiled, planar & interleaved) |
| Wavefront OBJ | `.obj` | Standard 3D mesh format |
| STL | `.stl` | Stereolithography mesh format |
| PLY | `.ply` | Stanford Polygon Library format (ASCII & binary, little/big endian) |

## Controls

| Action | Control |
|--------|---------|
| Rotate | Left mouse drag |
| Zoom | Mouse scroll wheel |
| Pan | Shift + left mouse drag (or middle mouse drag) |
| Reset view | `R` |
| Toggle wireframe | `W` |
| Toggle surface | `S` |
| Toggle element edges | `E` |

## Usage

Open a supported file in VS Code and it opens in the Mesh Viewer editor. The camera frames the model, and the info panel in the top-left shows:

```
Vertices: N | Elements: N | Groups: M
Bounds: X x Y x Z
```

`Groups` is shown only when the file defines zone/block/PID groups; cells are colored by group, falling back to per-zone colors for ungrouped zones.

When groups exist, a legend in the top-right lists each group name with its color. Group names may contain spaces.

The controls hint stays in the bottom-left.

## Installation

Install from the VS Code Marketplace or from a `.vsix` package.

See [CHANGELOG.md](CHANGELOG.md) for release notes.

## License

MIT
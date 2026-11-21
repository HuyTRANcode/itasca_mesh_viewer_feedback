# Itasca Mesh Viewer

[![Buy Me A Coffee](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://ko-fi.com/htcode)

Interactive VS Code viewer for Itasca FLAC3D/FLAC2D/3DEC grids, built on VTK.js.

## Features

- Custom editor for `.f3grid`, `.f2grid`, `.grid` (FLAC3D/FLAC2D), `.3dgrid` (3DEC), plus `.obj`, `.stl`, and `.ply`
- VTK.js 3D rendering: surface, wireframe, and edges
- Per-zone colors, with cells colored by FLAC `ZG` zone groups or 3DEC `BGROUP` block groups when defined
- Zone/block group legend in the top-right showing group name, slot, and matching color
- Element edge overlay: draws the edges of each zone cell (not triangulation diagonals)
- Live refresh when the file is saved
- Info panel: vertex count, zone/block count, and bounds

## Supported Formats

| Format | Extensions | Description |
|--------|------------|-------------|
| FLAC3D/FLAC2D Grid | `.f3grid`, `.f2grid`, `.grid` | Itasca FLAC2D/FLAC3D native grid format |
| 3DEC Grid | `.3dgrid` | Itasca 3DEC native grid format |
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
Vertices: N | Zones: N | Groups: M
Bounds: X x Y x Z
```

`Groups` is shown only when the file defines `ZG` zone groups; cells are colored by group, falling back to per-zone colors for ungrouped zones.

When zone groups exist, a legend in the top-right lists each group name and slot (for example `GroupA [SlotOne]`) with its color. Group and slot names may contain spaces, e.g. `ZG "Block 1" SL "Slot A"` or `ZG Block 1 SL Slot A`.

The controls hint stays in the bottom-left.

## Installation

Install from the VS Code Marketplace or from a `.vsix` package.

See [CHANGELOG.md](CHANGELOG.md) for release notes.

## License

MIT
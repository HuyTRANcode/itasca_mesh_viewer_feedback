# Itasca Mesh Viewer

<img src="media/icons/extension-icon-256.png" alt="Itasca Mesh Viewer icon" width="128">

Interactive VS Code viewer for Itasca FLAC3D/FLAC2D grids, built on VTK.js.

## Features

- Custom editor for `.f3grid`, `.f2grid`, `.grid` (FLAC3D/FLAC2D), plus `.obj` and `.stl`
- VTK.js 3D rendering: surface, wireframe, and edges
- Correct FLAC to VTK cell node ordering (`B8`, `B7`, `W6`, `P5`, `T4`, `Q4`, `T3`)
- Per-zone colors, with cells colored by FLAC `ZG` zone groups when defined
- Zone-group legend in the top-right showing group name, slot, and matching color
- Element edge overlay: draws the edges of each zone cell (not triangulation diagonals)
- Live refresh when the file is saved
- Info panel: vertex count, zone count, and bounds

## Supported Formats

### FLAC grids (`.f3grid`, `.f2grid`, `.grid`)

The parser reads the native ASCII grid records:

| Record | Meaning |
|---|---|
| `G id x y [z]` | Gridpoint (`z` defaults to 0 for FLAC2D) |
| `Z <type> <id> <gp...>` | Zone: `B8`, `B7`, `W6`, `P5`, `T4`, `Q4`, `T3` |
| `F <type> <id> <gp...>` | Face: `T3`, `Q4`, `E2` |
| `ZG`, `FCOLLECTION`, `GPG` | Group definitions (names/slots may contain spaces; `SL` introduces the slot) |
| `*` | Comment |

FLAC zone nodes are reordered to VTK node order before rendering. A 7-node `B7` zone is expanded to the 8-node hexahedron VTK expects, matching FLAC's `DBrick` handling.

Examples: `examples/brick.f3grid`, `examples/tunnel.f3grid`.

### Other meshes

`.obj` and `.stl` are also supported.

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

## Support

If you find this extension useful, consider donating:

[![PayPal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=XS2G6TQHD4784)

See [CHANGELOG.md](CHANGELOG.md) for release notes.

## License

MIT
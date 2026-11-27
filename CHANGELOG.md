# Changelog

## 1.3.0

### New Formats
- **TIFF Voxel Volume** (`.tif`, `.tiff`) - Multi-page TIFF stacks as hexahedral meshes, supports 8/16/32-bit, strip & tiled, planar & interleaved
- **Nastran BDF** (`.bdf`, `.nas`, `.dat`, `.fem`) - Volume elements (CHEXA, CTETRA, CPENTA, CPYRAM) with PID-based zone groups

## 1.2.0

### New Formats
- **PLY** (`.ply`) - ASCII & binary (little/big endian), with normals/colors support
- **STL** (`.stl`) - ASCII & binary, vertex deduplication

### Features
- Surface mesh backface culling disabled (PLY/STL/OBJ fully visible)
- Info panel shows "Faces" for surface meshes, "Zones" for volume meshes

## 1.1.0

### New Format
- **3DEC Grid** (`.3dgrid`) - ASCII format with gridpoints, faces, zones, blocks, groups

### Features
- Block groups (`BGROUP`), joint sets (`JS`), joint groups (`JGROUP`) support
- Zone element order conversion to VTK standard

## 1.0.0

### Formats
- **FLAC3D/FLAC2D Grid** (`.f3grid`, `.f2grid`, `.grid`)
- **Wavefront OBJ** (`.obj`)
- **STL** (`.stl`) - ASCII only

### Features
- VTK.js 3D rendering: surface, wireframe, edges
- Zone-group coloring (FLAC `ZG`, 3DEC `BGROUP`)
- Group legend with colors
- Element edge overlay (mesh cell edges, not triangulation)
- Live refresh on file save
- Info panel: vertices, zones, groups, bounds
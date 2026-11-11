# CityScape Specifications

> Transform Bitburner's ASCII city maps into interactive 3D neon worlds with monorails, buildings, and animated traffic.

## System Requirements

### Hardware Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **GPU** | WebGL 1.0 compatible | Modern integrated GPU (Intel Iris, AMD Radeon) |
| **RAM** | 4 GB | 8 GB+ |
| **CPU** | Dual-core @ 2.0 GHz | Quad-core @ 2.5 GHz+ |
| **Display** | 1024x768 | 1920x1080+ |
| **Mouse** | Required | 3-button with scroll wheel |

### Software Requirements

| Component | Version |
|-----------|---------|
| **Browser** | Modern (Chrome 60+, Firefox 55+, Safari 11+) |
| **WebGL** | 1.0+ |
| **JavaScript** | ES6+ support |
| **Bitburner** | Latest version |

### Browser Requirements

**Primary**: **WebGL 1.0** support

---

## Quick Start

### 1. Installation

Open your Bitburner terminal and run:

```bash
wget https://raw.githubusercontent.com/EphyMusic/Bitburner-CityScape/refs/heads/main/install.ts CityScape/install.ts
```

Then execute the installer:

```bash
CityScape/install.ts
```

The installer will:
- Download all library files (~20 files)
- Create `/CityScape/` directory structure
- Verify all files downloaded successfully
- Report any failures with manual download instructions

### 2. Quick Alias (Optional)

Set up a quick command in Bitburner:

```bash
alias city="home;CityScape/main.ts"
```

### 3. Run CityScape

Execute the main script:

```bash
CityScape/main.ts
```

**Or use the alias:**

```bash
city
```

### 4. First Time Usage

- Click on the **City** tab to view your ASCII city map
- CityScape will automatically load and replace the ASCII view
- A tail window appears in the top-left corner (minimized by default)
- The 3D city will render with buildings, monorail, and streets

---

## Basic Controls

| Input | Action |
|-------|--------|
| **Left-click + drag** | Orbit camera around city center |
| **Right-click + drag** | Pan camera left/right/up/down |
| **Mouse scroll** | Zoom in/out |
| **Click building** | Open location options card |
| **Click option** | Execute location action (work, crime, etc.) |
| **Hover option** | View action details/requirements |
| **Reset button** | Return to home camera view |
| **Close button** | Exit script, restore ASCII map |

---

## File Structure

```
CityScape/
├── main.ts                      # Entry point (run this)
├── install.ts                   # Installation script
└── lib/
    ├── CityScape.ts             # Main orchestrator
    ├── Camera.ts                # 3D camera control
    ├── Renderer.ts              # WebGL rendering engine
    ├── Overlay.ts               # UI overlay and interaction
    ├── CityDom.ts               # Game DOM integration
    ├── CityParser.ts            # ASCII map parser
    ├── SceneBuilder.ts          # 3D scene construction
    ├── MeshBuilder.ts           # Procedural geometry
    ├── Monorail.ts              # Train track system
    ├── Trains.ts                # Train animation
    ├── Roads.ts                 # Street generation
    ├── Cars.ts                  # Vehicle animation
    ├── Grid.ts                  # Coordinate utilities
    ├── Mat4.ts                  # 3D math library
    ├── Palette.ts               # Color theme system
    ├── Label.ts                 # UI labels and cards
    ├── Layout.ts                # UI positioning
    └── Cleanup.ts               # Exit handling
```

---

## Performance Tips

### For Smooth Gameplay

| Issue | Solution |
|-------|----------|
| Low FPS | Reduce window size, close other browser tabs, update GPU drivers |
| GPU fan noise | Lower zoom level, reduce building count (cosmetic buildings) |
| High RAM usage | Reduce number of simultaneous trains/cars in code |
| Stuttering | Ensure hardware meets **Recommended** specs above |

### Camera Framing

- Camera automatically frames cities of any size
- Zoom out to see entire city, zoom in for details
- Pan to explore; reset button returns to home view

---

## Installation Troubleshooting

### Problem: "Failed to download" error

**Solution**: The installer provides manual wget commands for each file. Copy and run them individually:

```bash
wget https://raw.githubusercontent.com/EphyMusic/Bitburner-CityScape/refs/heads/main/lib/Camera.ts /CityScape/lib/Camera.ts
```

### Problem: Script doesn't start

**Verify**:
1. All files downloaded successfully
2. You're on the **City** tab in Bitburner
3. Browser WebGL support is enabled
4. No script errors in browser console

### Problem: 3D view doesn't render

**Try**:
1. Switch to another tab (e.g. "Terminal") then back to the City tab
2. Double-click on City view.
3. If still blank, GPU/WebGL may not be supported

---

## Architecture Overview

```
User Input (Mouse/Keyboard)
    ↓
Overlay.ts (Event Capture)
    ↓
Camera.ts (View Transform)
    ↓
CityScape.ts (Orchestration)
    ├→ CityDom.ts (Sync with game)
    ├→ SceneBuilder.ts (3D Objects)
    └→ Renderer.ts (WebGL Output)
    ↓
Canvas (Display on Screen)
    ↓
Game Location Clicks Forwarded
```

---

## Core Features

### 3D Rendering
- Procedurally generated buildings with theme-based colors
- Smooth monorail track with animated trains
- Dynamic street networks with roaming vehicles
- Atmospheric fog with time-based animations

### Full Game Integration
- Click buildings to open location pages
- Execute all location actions (work, crime, etc.)
- Protected buttons handled automatically
- Seamless restoration when script exits

### Camera Control
- Orbit, pan, and zoom with smooth animations
- Automatic framing based on city size
- Constrained pitch/yaw to prevent disorientation
- Reset to home view in one click

### Adaptive UI
- Location cards with context-sensitive options
- Hover tooltips showing requirements
- Auto-positioned to prevent UI overflow
- Theme-aware colors matching game settings

---

## What's Next?

### For Users
- See [README.md](README.md) for detailed feature walkthrough
- Explore each city to discover building interactions
- Try different camera angles and zoom levels

### For Developers
- See individual module files (`lib/`) for detailed API documentation
- Architecture is modular; each system can be extended independently
- Custom building colors, animations, and effects can be added to `Palette.ts`

---

## Unknown Limitations

*None discovered yet—but if you find one, report it!*

---

**Report Issues**: Open an issue at [GitHub](https://github.com/EphyMusic/Bitburner-CityScape)

**Contribute**: Fork the repository and submit pull requests

**Credits**: Built with Bitburner API integration and procedural graphics

---

## Related Docs

- [README.md](README.md) — Full feature guide and gameplay
- `lib/` — Individual module documentation
- [Bitburner Wiki](https://bitburner.fandom.com/) — Game mechanics reference

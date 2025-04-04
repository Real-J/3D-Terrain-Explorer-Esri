# 🌍 3D Terrain Explorer Esri

Built entirely in HTML using embedded ArcGIS API for JavaScript and Esri-hosted 3D Scene Layers (I3S), this project showcases how to build a powerful client-side 3D geospatial visualization without any backend or additional JavaScript tooling.

---

## ✨ Features

Each feature in the 3D Terrain Explorer is built to deliver hands-on, insightful analysis of the Earth's terrain. Here's how they work behind the scenes:

- 🌈 **Advanced Heatmap Rendering**
  - Divides the current camera view extent into a 40x40 grid of elevation tiles.
  - For each tile, it samples corner points using the ArcGIS elevation sampler and computes the average elevation.
  - Color is assigned to each tile using a linear gradient from green (lowest) → yellow (midrange) → red (highest).
  - In **local mode**, colors are scaled based on the visible region’s elevation range — ideal for highlighting small hills or local terrain.
  - In **global mode**, colors are scaled based on a fixed elevation span (0 to 9000 meters) — useful for global comparisons.
  - Updates the legend dynamically to reflect the actual elevation metrics of the heatmap.

- 📈 **Interactive Sampling**
  - When the user clicks on any point on the globe, the application converts the screen coordinates into geographic coordinates.
  - It then queries the ground elevation service using the ArcGIS `queryElevation()` method to retrieve the height of that point above sea level.
  - A popup displays the coordinates and the precise elevation in meters.

- 🌍 **Fly To Landmarks**
  - Each button corresponds to a predefined landmark's latitude, longitude, and camera altitude.
  - When clicked, the scene animates the camera to the location using ArcGIS `view.goTo()` with a fixed tilt for dramatic terrain viewing.
  - This allows quick exploration of iconic geographic locations with 3D context.

- ✨ **Always Daylight Scene**
  - By using `lighting.type: "virtual"`, the scene disables real-time sun position and shadows.
  - This ensures consistent brightness and color visibility, even in areas that would otherwise be in darkness.
  - It improves terrain color interpretation by removing time-based lighting variations.

- 🔹 **Legend and UI Controls**
  - The heatmap legend updates dynamically with each generation to reflect current elevation ranges.
  - A radio toggle lets users switch between "local" and "global" modes to control how colors are mapped.
  - UI elements are styled responsively and include a personal watermark for branding.

---

## ⚡ Demo



---

## ⚙️ How to Run Locally

### Option 1: Open Directly
1. Download or clone the repository:
   ```bash
   git clone https://github.com/Real-J/3d-terrain-explorer.git
   cd 3d-terrain-explorer
   ```
2. Open `index.html` in any modern browser (Chrome, Firefox, Edge).

---

## 💡 Possible Extensions
- Elevation profile chart along a user-drawn path
- Highlight highest elevation point in current view
- Add UI theme toggle (light/dark base layers)




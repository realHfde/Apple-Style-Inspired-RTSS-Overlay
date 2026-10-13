# RTSS Overlays

Clean, Apple-style performance overlays for **RivaTuner Statistics Server (RTSS)**, built with the RTSS OverlayEditor plugin.

> Previews below are rendered with sample in-game numbers. Real colours and spacing may differ slightly in game.

---

## Overlays

### Sleek
A compact pill: CPU and GPU usage rings with temperature and power, FPS and 1% low in the middle.

![Sleek](previews/sleek.png)

### Sleek Compact
Full stats in one wide bar: CPU, GPU, FPS with frametime graph, and 12V cable voltage.

![Sleek Compact](previews/sleek_compact.png)

### Sleek Meters
Sleek Compact with a thin meter under every value, so you can see at a glance how close each one is to its limit.

![Sleek Meters](previews/sleek_meters.png)

### Sleek Rings
Activity-style double rings: the outer ring is load and the inner ring is temperature.

![Sleek Rings](previews/sleek_rings.png)

### Sleek Side
A vertical panel for the side of the screen, with CPU and GPU usage graphs.

<img src="previews/sleek_side.png" width="260" alt="Sleek Side">

### Simple Pill
<!-- Add a screenshot: previews/simple_pill.png -->
![Simple Pill](previews/simple_pill.png)

### Detailed Pill
<!-- Add a screenshot: previews/detailed_pill.png -->
![Detailed Pill](previews/detailed_pill.png)

---

## Requirements

| Program | Why |
|---|---|
| [RivaTuner Statistics Server](https://www.guru3d.com/download/rtss-rivatuner-statistics-server-download/) with the **OverlayEditor** plugin enabled | Draws the overlay |
| [MSI Afterburner](https://www.msi.com/Landing/afterburner) | CPU/GPU usage, temperature, power, FPS, 1% low |
| [HWiNFO64](https://www.hwinfo.com/) | Clocks, VRAM temperature, 12V cable voltage, GPU limit flags (used by the Sleek Compact, Meters, Rings and Side overlays) |

**HWiNFO setup:** run it in **Sensors-only** mode, open **Settings**, tick **Shared Memory Support**, and keep it running in the background. On the free version this switches itself off after 12 hours, so tick it again if values go blank.

---

## Install

1. Download this repo (**Code → Download ZIP**) and unzip it.
2. Open the folder of the overlay you want inside `overlays/`.
3. Copy **every file in that folder** into:
   ```
   C:\Program Files\RivaTuner Statistics Server\Plugins\Client\Overlays
   ```
   Put them directly in that folder, **not in a subfolder**. Each overlay looks for its image in that exact folder.
4. In RTSS, open **OverlayEditor**, go to **Layouts → Load**, and pick the overlay.

---

## Notes

- Built and tuned on a **Ryzen 7 7800X3D**, **RTX 5080** and **X870E** board at **5120×1440**. Drag the overlay in OverlayEditor to move it on other resolutions.
- The **12V cable** reading needs a graphics card that reports its 16-pin connector voltage in HWiNFO. On cards that don't, remove that section.
- The dot next to 12V turns **amber** below 11.85 V and **red** below 11.75 V, but only while the GPU is drawing over 150 W.
- **Sleek Meters** treats these as "full": CPU 120 W, GPU 360 W, CPU clock 5.05 GHz, GPU clock 2.9 GHz, RAM 32 GB, VRAM 16 GB. To change one, open **Data sources** and edit the matching `pct` source's formula.
- The CPU clock shows the *effective* clock, so it reads very low at idle and around 5 GHz in games.

## Troubleshooting

| Problem | Fix |
|---|---|
| Garbled letters instead of the panel | The `_atlas.png` (or `Overlay-BG.png`) file is missing or in a subfolder. Put it next to the `.ovl` in the main Overlays folder. |
| Some values show `N/A` or are blank | HWiNFO isn't running, or Shared Memory Support is off. |
| A value stays blank even with HWiNFO running | In OverlayEditor, open **Data sources**, select the row, click **Setup**, and pick the matching sensor from your HWiNFO list. |
| 1% / 0.1% show 0 | Normal outside a game. They fill in once a game is running. |

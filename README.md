# Apple-Style RTSS Overlays

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

---

## Themes

Every overlay comes in three themes:

| Theme | Folder | Look |
|---|---|---|
| **Dark** | `sleek-compact` | Dark glass panel, white text (the original) |
| **White** | `sleek-compact-white` | Soft light-grey panel with dark text, toned down so it isn't glaring |
| **Clear** | `sleek-compact-clear` | Mostly see-through panel; every number has a drop shadow so it stays readable over bright scenes |

![Themes](previews/themes.png)

<details>
<summary>All white and clear previews</summary>

![Sleek White](previews/sleek_white.png)
![Sleek Clear](previews/sleek_clear.png)
![Sleek Compact White](previews/sleek_compact_white.png)
![Sleek Compact Clear](previews/sleek_compact_clear.png)
![Sleek Meters White](previews/sleek_meters_white.png)
![Sleek Meters Clear](previews/sleek_meters_clear.png)
![Sleek Rings White](previews/sleek_rings_white.png)
![Sleek Rings Clear](previews/sleek_rings_clear.png)
<img src="previews/sleek_side_white.png" width="260" alt="Sleek Side White"> <img src="previews/sleek_side_clear.png" width="260" alt="Sleek Side Clear">

</details>

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
2. Open the folder of the overlay and theme you want inside `overlays/` (for example `sleek-meters-white`), then open the folder for **your screen resolution**:

   | Folder | Screen |
   |---|---|
   | `1920x1080` | 1080p |
   | `2560x1440` | 1440p |
   | `3440x1440` | 21:9 ultrawide |
   | `3840x2160` | 4K |
   | `5120x1440` | 32:9 super-ultrawide (the original) |

3. Copy **both files** in that folder (the `.ovl` and its `_atlas.png`) into:
   ```
   C:\Program Files\RivaTuner Statistics Server\Plugins\Client\Overlays
   ```
   Put them directly in that folder, **not in a subfolder**. Each overlay looks for its image in that exact folder.
4. In RTSS, open **OverlayEditor**, go to **Layouts → Load**, and pick the overlay.

The resolution versions only change **where** the overlay sits: centred at the top, or on the right edge for Sleek Side. On a 4K screen it will look smaller, so use the **On-Screen Display zoom** slider in RTSS to make it bigger. On any screen you can also drag it wherever you like in OverlayEditor.

---

## Notes

- Built and tuned on a **Ryzen 7 7800X3D**, **RTX 5080** and **X870E** board at **5120×1440**.
- The **12V cable** reading needs a graphics card that reports its 16-pin connector voltage in HWiNFO. On cards that don't, remove that section.
- The dot next to 12V turns **amber** below 11.85 V and **red** below 11.75 V, but only while the GPU is drawing over 150 W.
- **Sleek Meters** treats these as "full": CPU 120 W, GPU 360 W, CPU clock 5.05 GHz, GPU clock 2.9 GHz, RAM 32 GB, VRAM 16 GB. To change one, open **Data sources** and edit the matching `pct` source's formula.
- The CPU clock shows the *effective* clock, so it reads very low at idle and around 5 GHz in games.

## Troubleshooting

| Problem | Fix |
|---|---|
| Garbled letters instead of the panel | The `_atlas.png` file is missing or in a subfolder. Put it next to the `.ovl` in the main Overlays folder. |
| Some values show `N/A` or are blank | HWiNFO isn't running, or Shared Memory Support is off. |
| A value stays blank even with HWiNFO running | In OverlayEditor, open **Data sources**, select the row, click **Setup**, and pick the matching sensor from your HWiNFO list. |
| 1% / 0.1% show 0 | Normal outside a game. They fill in once a game is running. |

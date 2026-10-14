# Apple-Style RTSS Overlays

Clean, Apple-style performance overlays for **RivaTuner Statistics Server (RTSS)**, built with the RTSS OverlayEditor plugin.

> Previews below are rendered with sample in-game numbers. Real colours and spacing may differ slightly in game.

## 🆕 What's new

**October 2026**
- **Quick install:** one zip per resolution with every overlay and theme, ready to copy straight into the Overlays folder. See [Install](#install).
- **New Float theme:** no background at all, just the numbers, rings and meters floating over your game. Less distracting, and nice on OLED screens. [See it below](#themes).
- **New resolutions:** 3840x1600 and 5120x2160 (5K2K) for every overlay and theme.
- **No 12V versions** of Compact, Meters, Meters Universal, Rings and Side, for graphics cards that don't report 12V or if you don't want it. Look for the folders ending in `-no-12v`. [See them below](#no-12v-versions).

Thanks to everyone on Reddit who asked for these!

---

## Overlays

### Sleek
A compact pill: CPU and GPU usage rings with temperature and power, FPS and 1% low in the middle.

![Sleek](previews/sleek.png)

### Sleek Compact
Full stats in one wide bar: CPU, GPU, FPS with a frametime graph, 12V cable voltage, and GPU limit warnings that only appear when a limit is hit.

![Sleek Compact](previews/sleek_compact.png)

### Sleek Meters
Sleek Compact with a thin meter under every value, so you can see at a glance how close each one is to its limit.

![Sleek Meters](previews/sleek_meters.png)

### Sleek Meters Universal
Sleek Meters with scales that fit **any build**, up to an RTX 5090 with a top-end CPU. The bars are set to the limits of today's fastest hardware, so nothing maxes out early on a high-end PC:

| Meter | Full at | Why |
|---|---|---|
| CPU power | 253 W | Intel Core i9 max turbo power; covers Ryzen 9 9950X3D too |
| CPU clock | 6.2 GHz | Core i9-14900KS max turbo, the fastest desktop CPU |
| GPU power | 600 W | RTX 5090 is rated 575 W on a 600 W 12V-2x6 connector |
| GPU clock | 3.2 GHz | Above the fastest boosting cards |
| RAM | 100% | Of whatever RAM you have installed |
| VRAM | 100% | Of whatever memory your graphics card has |

![Sleek Meters Universal](previews/sleek_meters_universal.png)

### Sleek Rings
Activity-style double rings: the outer ring is load and the inner ring is temperature.

![Sleek Rings](previews/sleek_rings.png)

### Sleek Side
A vertical panel for the side of the screen, with CPU and GPU usage graphs.

<img src="previews/sleek_side.png" width="260" alt="Sleek Side">

### Performance Overlay
Every number you could want, in a benchmark-style side panel: FPS, 1% / 0.1% lows and frametime with a frametime graph; CPU temp, load, power, clock and RAM; GPU temp, load, power, clock, voltage, fan, VRAM and VRAM temp; and CPU and GPU load graphs. Made for benchmarking and testing new parts.

<img src="previews/all/performance.png" width="780" alt="Performance Overlay in Dark, White, Clear and Float">

### No 12V versions
Compact, Meters, Meters Universal, Rings and Side also come **without the 12V cable section**, for graphics cards that don't report it or if you just don't want it. They're the same overlays, slightly smaller. Look for the folders ending in `-no-12v`.

![No 12V versions](previews/no_12v.png)

---

## Themes

Every overlay comes in four themes:

| Theme | Folder | Look |
|---|---|---|
| **Dark** | `dark` | Dark glass panel, white text |
| **White** | `white` | Soft light-grey panel with dark text, toned down so it isn't glaring. Turn off **On-Screen Display shadow** in RTSS for sharp text. |
| **Clear** | `clear` | Mostly see-through panel; every number has a drop shadow so it stays readable over bright scenes |
| **Float** | `float` | No panel at all: just the numbers, rings and meters with a drop shadow. Least distracting, and nice on OLED screens |

![Dark, White, Clear and Float](previews/themes_all.png)

<details>
<summary><b>All previews: every overlay in Dark, White, Clear and Float</b> (click to open)</summary>

#### Sleek

![Sleek](previews/all/sleek.png)

#### Sleek Compact

![Sleek Compact](previews/all/sleek-compact.png)

#### Sleek Compact No 12V

![Sleek Compact No 12V](previews/all/sleek-compact-no-12v.png)

#### Sleek Meters

![Sleek Meters](previews/all/sleek-meters.png)

#### Sleek Meters No 12V

![Sleek Meters No 12V](previews/all/sleek-meters-no-12v.png)

#### Sleek Meters Universal

![Sleek Meters Universal](previews/all/sleek-meters-universal.png)

#### Sleek Meters Universal No 12V

![Sleek Meters Universal No 12V](previews/all/sleek-meters-universal-no-12v.png)

#### Sleek Rings

![Sleek Rings](previews/all/sleek-rings.png)

#### Sleek Rings No 12V

![Sleek Rings No 12V](previews/all/sleek-rings-no-12v.png)

#### Sleek Side

![Sleek Side](previews/all/sleek-side.png)

#### Sleek Side No 12V

![Sleek Side No 12V](previews/all/sleek-side-no-12v.png)

#### Performance Overlay

![Performance Overlay](previews/all/performance.png)

</details>

---

## Requirements

| Program | Why |
|---|---|
| [RivaTuner Statistics Server](https://www.guru3d.com/download/rtss-rivatuner-statistics-server-download/) with the **OverlayEditor** plugin enabled | Draws the overlay |
| [MSI Afterburner](https://www.msi.com/Landing/afterburner) | CPU/GPU usage, temperature, power, FPS, 1% low |
| [HWiNFO64](https://www.hwinfo.com/) | Clocks, VRAM temperature, GPU voltage and fan, 12V cable voltage, GPU limit warnings (needed by every overlay except Sleek) |

### HWiNFO setup (Shared Memory)

The overlays read clocks, VRAM temperature, 12V and limit warnings from HWiNFO through **Shared Memory**. If those values are blank, this is almost always why.

1. Start HWiNFO64 and tick **Sensors-only**, then click **Start**. In the sensors window, click the **gear** button at the bottom.

   <img src="previews/hwinfo/1_sensor_settings.png" width="380" alt="Sensors window: gear button">

2. *(Optional)* In **Sensor Settings**, the **Global** polling period can stay at **2000 ms**. That's plenty for an overlay and keeps HWiNFO light.
3. Click **Main Settings** at the bottom.

   <img src="previews/hwinfo/2_main_settings.png" width="560" alt="Sensor Settings: polling period and Main Settings button">

4. Tick **Shared Memory Support** and click **OK**.

   <img src="previews/hwinfo/3_shared_memory.png" width="360" alt="Main Settings: Shared Memory Support">

5. Keep HWiNFO running in the background (ticking **Auto Start** in the same window starts it with Windows).

> On the free version, Shared Memory switches itself off after **12 hours**. If values go blank after a long session, tick it again (or restart HWiNFO).

---

## Install

### Quick install (all overlays at once)

1. Go to the **[latest release](https://github.com/realHfde/Apple-Style-Inspired-RTSS-Overlay/releases/latest)** and download the zip for **your screen resolution**, e.g. `All.overlays.2560x1440.zip`.
2. Unzip it and copy **all the files** into:
   ```
   C:\Program Files\RivaTuner Statistics Server\Plugins\Client\Overlays
   ```
   Put them directly in that folder, **not in a subfolder**.
3. In RTSS, open **OverlayEditor → Layouts → Load** and flip through them to pick your favourite.

Every overlay in every theme is in there (96 files), and none of the names clash.

### Install just one overlay

1. Download this repo (**Code → Download ZIP**) and unzip it.
2. Inside `overlays/`, open the overlay you want, then the theme (`dark`, `white`, `clear` or `float`), then the folder for **your screen resolution**. For example: `overlays/sleek-meters/white/2560x1440`.

   | Folder | Screen |
   |---|---|
   | `1920x1080` | 1080p |
   | `2560x1440` | 1440p |
   | `3440x1440` | 21:9 ultrawide |
   | `3840x1600` | 24:10 ultrawide |
   | `3840x2160` | 4K |
   | `5120x1440` | 32:9 super-ultrawide |
   | `5120x2160` | 5K2K ultrawide |

3. Copy **both files** in that folder (the `.ovl` and its `_atlas.png`) into:
   ```
   C:\Program Files\RivaTuner Statistics Server\Plugins\Client\Overlays
   ```
   Put them directly in that folder, **not in a subfolder**. Each overlay looks for its image in that exact folder.
4. In RTSS, open **OverlayEditor**, go to **Layouts → Load**, and pick the overlay.

The resolution versions only change **where** the overlay sits: centred at the top, or on the right edge for Sleek Side and the Performance Overlay. On a 4K or 5K2K screen it will look smaller, so use the **On-Screen Display zoom** slider in RTSS to make it bigger. On any screen you can also drag it wherever you like in OverlayEditor.

---

## Notes

- The **12V cable** reading needs a graphics card that reports its 16-pin connector voltage in HWiNFO. On cards that don't, use the **No 12V** versions.
- **The 12V monitor is a visual hint, not a safety system.** It only changes colour on the overlay: there's no pop-up or sound, so it only helps if you happen to look at it. Readings depend on your card's sensors and can be imprecise. It's no substitute for a properly seated, undamaged cable. For a real alert, set an alarm on the 12V reading in HWiNFO, which can show a warning or play a sound.
- The dot next to 12V turns **amber** below 11.85 V and **red** below 11.75 V. It only reacts once the GPU is drawing more than 150 W. At low power hardly any current flows through the cable, so even a bad connection barely lowers the voltage; a low reading only means something under real load. At idle or on the desktop, the dot stays green.
- **Sleek Meters** uses fixed scales for an upper-mid-range PC (CPU 120 W, GPU 360 W, CPU clock 5.05 GHz, GPU clock 2.9 GHz, RAM 32 GB, VRAM 16 GB). For a high-end PC, use **Sleek Meters Universal**.
- **Sleek Meters Universal:** to change a scale, open **Data sources** in OverlayEditor and edit the matching `pct` source's formula. For example, `x / 6` means 600 W is full; change it to `x / 3.6` for 360 W.
- The CPU clock shows the *effective* clock, so it reads very low at idle and close to your CPU's boost clock in games.

## Troubleshooting

| Problem | Fix |
|---|---|
| Overlay Editor looks empty | The overlay is placed for a full screen (top centre, or right edge for Side and Performance). **Maximize the Overlay Editor window** to see it. Also turn on **Show On-Screen Display** in the main RTSS window, or nothing shows in game. |
| CPU / GPU clocks are blank (next to GHz) | Clocks come from **HWiNFO**, not Afterburner. Follow the [HWiNFO setup](#hwinfo-setup-shared-memory). If it's running and they're still blank, open **Data sources**, select **CPU clock**, click **Setup** and pick your CPU's clock reading. Do the same for **GPU clock** (and the `pct` versions on Meters). |
| GPU load, temperature or power are blank | These come from **MSI Afterburner**. Make sure it's running, then go to **Settings → Monitoring** and enable *GPU usage, GPU temperature, Power, CPU usage, CPU temperature* and *CPU power*. With two GPUs (integrated + graphics card), open **Data sources**, select **GPU1 usage**, click **Setup** and pick your graphics card. Do the same for GPU1 temperature and GPU1 power. |
| Garbled letters instead of the panel | The `_atlas.png` file is missing or in a subfolder. Put it next to the `.ovl` in the main Overlays folder. |
| Some values show `N/A` or are blank | HWiNFO isn't running, or Shared Memory Support is off. See [HWiNFO setup](#hwinfo-setup-shared-memory). |
| A value stays blank even with HWiNFO running | In OverlayEditor, open **Data sources**, select the row, click **Setup**, and pick the matching sensor from your HWiNFO list. |
| 1% / 0.1% show 0 | Normal outside a game. They fill in once a game is running. |
| Text looks blurry or smudged on the White theme | Turn off **On-Screen Display shadow** in the main RTSS window. The shadow is meant for white text on dark backgrounds; the Dark themes don't need it, and the Clear and Float themes have their own shadow built in. |

---

## License

MIT. Use them, change them and share them; just keep the license file with them. See [LICENSE](LICENSE).

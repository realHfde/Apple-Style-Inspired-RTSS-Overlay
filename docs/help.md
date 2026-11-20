# 🛠️ Help

<a id="troubleshooting"></a>
## Troubleshooting

| Problem | Fix |
|---|---|
| Overlay doesn't appear in a game | Check **Show On-Screen Display** is ON ([step 4](overlay-setup.md#rtss-setup), #1), then tick **Enable benchmark mode** ([step 4](overlay-setup.md#benchmark-tip)). |
| I can't find the Overlay editor | **RTSS → Setup → Plugins**, tick **OverlayEditor.dll**, **click its name** so it's highlighted, then click **Setup** under the list ([pictures](overlay-setup.md#rtss-setup)). |
| The Overlay editor looks empty | The overlay is placed for a full screen. **Maximize the Overlay editor window** to see it. |
| I can't find the Overlays folder | The default is `C:\Program Files (x86)\RivaTuner Statistics Server\Plugins\Client\Overlays`. If RTSS is installed somewhere else, go to its folder → **Plugins → Client → Overlays**. |
| FPS, 1% or 0.1% low are blank or 0 | They come from **MSI Afterburner**: keep it running and tick **Framerate**, **Framerate 1% Low** and **Framerate 0.1% Low** in its Monitoring tab ([step 3](overlay-setup.md#get-started)). They only fill in while a game runs. Also check the [RTSS General settings](overlay-setup.md#rtss-setup). |
| GPU numbers are 0 or wrong | Your PC probably has integrated graphics. See [two GPUs](overlay-extras.md#two-gpus). |
| 12V is blank | **Volt only:** HWiNFO isn't running, or Shared Memory Support is off. See [step 2](overlay-setup.md#hwinfo-setup-shared-memory). If it's on and still blank, open **Data sources**, select **12V cable**, click **Setup** and pick your card's 12V reading. If your card doesn't report it, use **Essential**. |
| Text looks different, too wide, or doesn't line up | The **Inter** font isn't installed. Install [Inter](https://rsms.me/inter/) and restart RTSS. |
| Garbled letters instead of the panel | The `_atlas.png` file is missing or in a subfolder. Put it next to the `.ovl` in the main Overlays folder. |
| I still see the old look after updating | RTSS keeps old pictures until it's closed. Exit **RTSS and Afterburner** fully (from the tray) and open them again. |
| Text looks blurry on the White theme | Turn off **On-Screen Display shadow** in the main RTSS window ([step 4](overlay-setup.md#rtss-setup), #3). |

---

## Notes

- The **12V cable** reading needs a graphics card that reports its 16-pin connector voltage in HWiNFO. On cards that don't, use **Essential**.
- **The 12V monitor is a visual hint, not a safety system.** It only changes colour on the overlay: no pop-up or sound, so it only helps if you happen to look at it. Readings depend on your card's sensors and can be imprecise, and most cards report one voltage for the whole connector. It's no substitute for a properly seated, undamaged cable. For a real alert, set an alarm on the 12V reading in HWiNFO.
- **The 12V warning:** the **12V** label turns **amber** if the cable voltage drops below 11.85 V and **red** below 11.75 V, but only while you're gaming (GPU using more than 150 W). The cable is only under real stress under heavy load. At idle almost no power flows through it, so a low number there doesn't mean anything and the label stays green. The number itself always shows the real voltage.
- **Sleek Meters** uses fixed scales for an upper-mid-range PC. For a high-end PC, use **Sleek Meters Universal**.
<a id="meter-scales"></a>
- **Sleek Meters Universal** fills its bars at the limits of today's fastest hardware, so nothing maxes out early:

  | Meter | Full at | Why |
  |---|---|---|
  | CPU power | 300 W | Above the max turbo power of today's top Intel and AMD CPUs |
  | CPU clock | 7.0 GHz | Headroom above the fastest desktop CPUs (about 6.2 GHz) |
  | GPU power | 800 W | Room for an RTX 5090 (575 W) and overclocked cards |
  | GPU clock | 4.0 GHz | Above the fastest boosting cards |
  | RAM | 64 GB | Fits 32 GB and 64 GB builds |
  | VRAM | 32 GB | Fits every card up to an RTX 5090 (32 GB) |
- To change a meter's scale, open **Data sources** in the Overlay editor and edit the matching `pct` source's formula. For example, `x / 8` means 800 W is full; change it to `x / 3.6` for 360 W.
- On the 4K **1.5×** and **2×** versions, some rings and meters move in slightly bigger steps, so the picture fits RTSS's size limit.

<a id="old-names"></a>
## 🏷️ Switching from older versions

The old copies don't get replaced automatically. RTSS also keeps showing an old picture until it's fully closed, so **exit RTSS and Afterburner once** after copying in new files.

| You had | Now | What to do |
|---|---|---|
| **Clear** theme (`…_clear.ovl`) | **Smoke** (`…_smoke.ovl`) | Delete the old `…_clear` files from the Overlays folder and load the `…_smoke` ones |
| **Island Bar / Island Bar Time** | The new [💻 laptop designs](overlays.md#laptops) | Delete the `…island_bar…` files and copy in a laptop pack |
| **Volt Sleek** and the Volt **no 12V** versions (`…no12v…`) | Removed | Delete them. Use **Essential Sleek** instead of Volt Sleek; if your card doesn't report 12V, use **Essential** |
| Old **TV Pill / TV Side** | The new [📺 TV designs](overlays.md#tvs) | Delete the old `tv_…` files, then copy in the TV pack for your TV |
| **MSI Edition** (`msi_…`) or the original overlays (`sleek.ovl`, `performance_overlay.ovl`…) | **🟢 Essential** (`essential_…`) / **⚡ Volt** (`volt_…`) | Copy in the new pack, then delete the old files so they don't show twice in **Layouts → Load** |
| **Apple Style Monitor** (Rainmeter) | **📱 Monitors & Widgets** | In **Manage**, unload the **AppleStyleMonitor** skins and load the same layout from **MonitorsAndWidgets**. Then delete `Documents\Rainmeter\Skins\AppleStyleMonitor` |

If you moved an overlay in the Overlay editor, move the new one the same way and save it.

[← Back to the front page](../README.md)

# 🧰 Optional extras for the overlays


Click the ones you need to open them:

<a id="smooth"></a>
<details>
<summary><h3>🧈 Keep it smooth (no stutter)</h3></summary>

The overlay itself is light: it redraws every **500 ms** (the RTSS refresh period from [step 4](overlay-setup.md#rtss-setup)). Stutter usually comes from monitoring apps reading sensors too often, so:

| # | App | Setting | Set it to |
|---|---|---|---|
| 1 | **MSI Afterburner** | Settings → Monitoring → **Hardware polling period** | **1000** ms |
| 2 | **HWiNFO** *(Volt only)* | Sensor Settings → General → **Global** polling period | **2000** ms |
| 3 | **HWiNFO** *(Volt only)* | Same box: **Disk S.M.A.R.T. every** … cycles and **Emb. Controller every** … cycles | **100** and **10**, then click **Set** |

<img src="../previews/setup/ab_polling.png" width="420" alt="Afterburner: Hardware polling period 1000"> <img src="../previews/hwinfo/4_polling.png" width="420" alt="HWiNFO Sensor Settings: Global 2000 ms, Disk S.M.A.R.T. and Emb. Controller cycles, Set">

Want the lightest setup? Use **🟢 Essential**: no HWiNFO at all.

</details>

<a id="hotkey"></a>
<details>
<summary><h3>⌨️ Show / hide the overlay with a hotkey</h3></summary>

Pick **one** of the two ways. Both do the same thing.

**Option A: in RTSS** (works without Afterburner)

| # | What to do |
|---|---|
| 1 | Open **RTSS** and click **Setup**, then open the **Plugins** tab |
| 2 | Click the name **HotkeyHandler.dll** so it's highlighted (keep it ticked) |
| 3 | Click **Setup** under the list |
| 4 | Click the box next to **Toggle On-Screen Display** and press the key you want (e.g. **F10**) |
| 5 | Click **OK**, then **OK** again in RTSS Setup |

<img src="../previews/setup/rtss_hotkey_plugin.png" width="320" alt="RTSS Plugins tab: 2 HotkeyHandler.dll, 3 Setup"> <img src="../previews/setup/rtss_hotkey.png" width="320" alt="Hotkey handler: 4 Toggle On-Screen Display, 5 OK">

**Option B: in MSI Afterburner**

| # | What to do |
|---|---|
| 1 | Open **MSI Afterburner** → **Settings** (gear) |
| 2 | Open the **On-Screen Display** tab |
| 3 | Click the box next to **Toggle On-Screen Display** and press the key you want (e.g. **F10**) |
| 4 | Click **Apply** |
| 5 | Click **OK** |

<img src="../previews/setup/ab_hotkey.png" width="560" alt="Afterburner: 1 Settings gear, 2 On-Screen Display tab, 3 Toggle On-Screen Display, 4 Apply, 5 OK">

Now press that key in game to show or hide the overlay. Handy for screenshots and recordings.

</details>

<a id="two-gpus"></a>
<details>
<summary><h3>🖥️ CPU with integrated graphics, or two GPUs?</h3></summary>

**If GPU load, temperature or power show 0 or look wrong, the overlay is probably reading your integrated graphics.**

**Which number is your graphics card?** Open **Task Manager** (Ctrl + Shift + Esc) → **Performance** and look at the GPU list. The number next to your graphics card (e.g. **GPU 1**) is the one to use:

<img src="../previews/gpu/0_task_manager.png" width="360" alt="Task Manager: GPU 0 integrated graphics, GPU 1 graphics card">

| # | What to do |
|---|---|
| 1 | In the Overlay editor, click **Data sources** at the top |
| 2 | Select **GPU1 temperature** (then repeat for every other row that starts with **GPU**) |
| 3 | Click **Setup** |
| 4 | Pick your graphics card (change the GPU number from **0** to your card's number from Task Manager, usually **1**) |
| 5 | Click **OK**, then **OK** again, and **save** the layout |

<img src="../previews/gpu/1_data_sources.png" width="420" alt="Overlay editor: Data sources menu">

<img src="../previews/gpu/2_select_gpu.png" width="420" alt="Data sources: GPU rows, Setup button"> <img src="../previews/gpu/3_instance.png" width="420" alt="Data source settings: change the GPU number, OK">

Tip: watch the **Value** column in Data sources. Once it's right, GPU usage jumps up when you start a game.

</details>

<a id="move-an-overlay"></a>
<details>
<summary><h3>📍 Move it anywhere you like</h3></summary>

1. Open the overlay in the **Overlay editor**.
2. ### Turn off "Snap to grid" first! ⚠️
   Click **View** at the top, then click **Snap to grid** so the ✓ disappears. With snapping on, each piece snaps separately and the numbers slide out of place.

   <img src="../previews/setup/snap_to_grid.png" width="440" alt="Overlay editor: View menu, Snap to grid">

3. Select all the layers and drag the overlay where you want it, e.g. the lower-left corner.
4. **Save** the layout.

Everything stays lined up, and it remembers the new spot. (RTSS's own position box doesn't move these overlays, so this is the way to do it.)

</details>

<details>
<summary><h3>📦 Only want one overlay?</h3></summary>

Download this repo (**Code → Download ZIP**), then open `overlays/` → the version → the overlay → the theme (`dark`, `white`, `smoke` or `float`) → your resolution, e.g. `overlays/essential/sleek-meters/smoke/2560x1440`. Copy the `.ovl` and its `_atlas.png` into the Overlays folder.

</details>

Something not showing up? Check [Troubleshooting](help.md#troubleshooting). Most issues take a few seconds to fix.

---

[← Back to the front page](../README.md)

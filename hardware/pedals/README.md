# Pedal Design Specification

## Version 1.0 (FlexStrut baseline)

---

## Contents

* [1) Mechanical Standards](#1-mechanical-standards)
  * [1.1 Universal Mounting Grids](#11-universal-mounting-grids)
  * [1.2 Fasteners (house policy – only three lengths per diameter)](#12-fasteners-house-policy--only-three-lengths-per-diameter)
    * [1.3 Pedal Shaft & Bearings](#13-pedal-shaft--bearings)
* [2) Pedal Force Assistance — FlexStrut Design](#2-pedal-force-assistance--flexstrut-design)
  * [Overview](#overview)
    * [Bill of materials (per strut)](#bill-of-materials-per-strut)
    * [Fusion 360 parameter set (drop-in)](#fusion-360-parameter-set-drop-in)
    * [Assembly (2 minutes)](#assembly-2-minutes)
    * [Pedal recipes](#pedal-recipes)
    * [Looks like a gas strut](#looks-like-a-gas-strut)
* [3) Pedal Mechanical Layout](#3-pedal-mechanical-layout)
  * [Layout Overview](#layout-overview)
    * [Bill of materials (per pedal)](#bill-of-materials-per-pedal)
    * [Fusion 360 parameter set (drop-in)](#fusion-360-parameter-set-for-flexstrut-drop-in)
    * [Assembly (5 minutes)](#assembly-5-minutes)
    * [Pedal feel tuning](#pedal-feel-tuning)
    * [Pedal mechanical drawings](#pedal-mechanical-drawings)

---

## 1) Mechanical Standards

### 1.1 Universal Mounting Grids

* **External (rig-facing):** **Rift-40** — 40 × 40 mm grid, **M5** through-bolts, slotted where adjustability is needed (slot width 6.8–7.0 mm; length 20–40 mm).
* **Internal (component-facing):** **Rift-20** — 20 × 20 mm grid, **M3/M4** (use M3 inserts for panels, M4 optional on metal plates).

### 1.2 Fasteners (house policy – only three lengths per diameter)

#### M3 (internal)

* Short: **8 mm**
* Medium: **12 mm**
* Long: **16 mm**

> Heat-set brass inserts: 3 × 4.2 mm; pilot **Ø4.0 mm**; pocket depth 4.4–4.6 mm; boss OD 11.5 mm min.
>
#### M5 (structural)

* Short: **16 mm**
* Medium: **25 mm**
* Long: **35 mm**

> Clearance: **Ø5.5 mm**; slots: **6.8–7.0 mm** wide with end radii; counterbore (optional): Ø11 mm × 2 mm.
>
### 1.3 Pedal Shaft & Bearings

* **Shaft:** 12 mm (key/flat) → upgradeable to 20 mm + 6004ZZ for >10 Nm.
* **Bearings:** 2 × 6202ZZ (Ø35 × 9 mm) spaced 40 mm.
* **Shaft collars:** 12 mm split collars for axial retention.
* **Spacers:** 1.0 mm printed washers between paired bearings.

## 2) Pedal Force Assistance — FlexStrut Design

### Overview

* **Type:** Telescoping strut with **pneumatic resistance tubes**.
* **Rod**: PETG (for mini) or **8/10 mm metal** (for standard/brake).
* **Threads**: printed trapezoid or straight; **M6 metal rod** for preload screw.
* **Finish**: matte black; optional vinyl wrap for “gas strut” look.

---

### Bill of materials (per strut)

* 1× Printed barrel (22 or 28 mm OD)
* 1× Printed wiper cap with bushing + anti-rotation key
* 1× Printed end cap (threaded) + M6 nut insert
* 1× Rod (8 or 10 mm; printed or metal) + clevis/eye end
* 1–2× **Resistance tubes** (length 100–160 mm)
* 2× Tube anchor cores + 4× zip-ties + 2× M5 washers
* 1× M6 × 50–70 mm preload screw + locknut
* 2× M5 or M8 rod ends/bolts + washers
* Optional: PETG **snap-guard sleeve**, elastomer bumper

---

### Fusion 360 parameter set for FlexStrut (drop-in)

```Gherkin
strut_type = "Mini" // or "Standard"
barrel_OD = 22 mm    // 28 mm for Standard
barrel_ID = 18 mm    // 24 mm for Standard (2.0 mm wall)
rod_OD = 8 mm        // 10 mm for Standard
stroke = 30 mm       // 25–40 mm range
tube_OD = 12 mm      // 10/12/14 mm options
tube_wall = 2.5 mm
tube_free_len = 120 mm // 100–160 mm
preload = 5 mm       // 0–10 mm
end_thread = M6
eye_bolt = M5
mount_grid = 20 mm   // Rift-20
```

---

### Assembly (2 minutes)

1. Press tube(s) onto **front anchor** on rod; zip-tie + washer.
2. Feed rod into barrel; seat wiper cap (snap/bolts).
3. Insert **rear anchor** with tube tail(s); fit end cap.
4. Turn **M6 preload screw** until desired baseline force; locknut.
5. Bolt barrel eye to frame; rod clevis to pedal lever.
6. Set **travel limiters**; test full stroke; add elastomer if desired.

---

### Pedal recipes

* **Throttle (light)**: Mini strut, **one 10×2 mm** tube, stroke 25–30 mm, preload 3–4 mm.
* **Clutch (snappy)**: Mini strut, **one 12×2.5 mm** tube, stroke 30 mm, preload 5–6 mm, **hard stop** near end for bite.
* **Brake (progressive)**: Standard strut, **two 12×2.5 or 14×3** tubes, stroke 35–40 mm, preload 6–8 mm, **elastomer bumper** in last 5–8 mm.

---

### Looks like a gas strut

![FlexStrut assembly with gas strut appearance](./images/flexstrut_gasstrut.png)

* Optional vinyl wrap gives a professional “gas strut” appearance.  
* Printed matte black parts reduce glare and look sleek.
* Wiper cap with bushing keeps dirt out and ensures smooth operation.
* Anti-rotation key prevents rod spin for consistent pedal feel.
* Resistance tubes provide a natural, progressive force curve.
* Preload screw allows fine-tuning of baseline pedal force.

## 3) Pedal Mechanical Layout

### Layout Overview

```Gherkin
[ Pedal Lever ]----[ FlexStrut ]----[ Mounting Base ]
```

* **Pedal lever:** Rift-20 grid mounting; 12 mm shaft interface.
* **FlexStrut:** see [section 2](#2-pedal-force-assistance--flexstrut-design).
* **Mounting base:** Rift-40 grid; M5 through-bolts.
* **Shaft & Bearings:** 12 mm shaft with 6202ZZ (Ø35 × 9 mm).

### Bill of materials (per pedal)

* 1× Printed pedal lever (Rift-20 grid) + M3 inserts
* 1× 12 mm shaft + 2× 6202ZZ bearings + spacers + shaft collars
* 1× Printed mounting base (Rift-40 grid) + M5 inserts
* 1× FlexStrut assembly (see section 2)
* 4× M5 through-bolts + washers + nuts

---

### Fusion 360 parameter set (drop-in)

```Gherkin
pedal_length = 150 mm    // 120–180 mm range
pedal_width = 60 mm      // 50–80 mm range
shaft_dia = 12 mm
bearing_ID = 15 mm   // 6202ZZ
bearing_OD = 35 mm
bearing_W = 9 mm
base_grid = 40 mm   // Rift-40
lever_grid = 20 mm  // Rift-20
strut_mount_offset = 30 mm // from pedal pivot
```

---

### Assembly (5 minutes)

1. Press bearings onto **12 mm shaft** with spacers; fit shaft collars.
2. Bolt **pedal lever** to shaft; ensure smooth rotation.
3. Attach **mounting base** to pedal lever assembly.
4. Install **FlexStrut** between pedal lever and mounting base.
5. Secure entire assembly to rig frame using M5 through-bolts.

---

### Pedal feel tuning

* Adjust **FlexStrut preload** and **resistance tubes** as per desired pedal feel
    (see [section 2](#2-pedal-force-assistance--flexstrut-design)).
* Test pedal travel and ensure smooth operation without binding.
* Fine-tune pedal angle and position using Rift-40 grid slots.

---

### Pedal mechanical drawings

![Pedal mechanical drawing showing lever, mounting base, and shaft assembly](./images/pedal_mechanical_drawing.png)

* Detailed mechanical drawings for pedal lever, mounting base, and shaft assembly.
* Dimensions and tolerances provided for accurate fabrication and assembly.
* Ensure all components align correctly for optimal pedal performance.

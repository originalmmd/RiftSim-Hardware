# Rift Wheelbase — Dual-Side Motor Architecture

## Modular, Safe, and Maker-Friendly Belt-Drive System

This base is the foundation of the **Rift MiniSim ecosystem**.
It’s designed around a **symmetrical dual-motor layout**, letting you start small and scale your build from the **Mini (RS550)** all the way to the **Pro (dual 775)** or **Hardcore (12 Nm)** without replacing the chassis.

---

## 🔧 Modular Evolution Path

| Tier         | Motors                    | Reduction                       | Torque (at rim)       | Notes                |
| ------------ | ------------------------- | ------------------------------- | --------------------- | -------------------- |
| **Mini**     | 1 × RS550                 | GT2 20→60 (3:1)                 | 1.5–2.5 Nm            | Entry-level FFB-lite |
| **Standard** | 1 × 775                   | GT2 20→60 (3:1)                 | 3–4 Nm                | Everyday belt base   |
| **Pro**      | 2 × 775                   | Dual GT2 20→60 (~9:1 two-stage) | 7–10 Nm (capped 8 Nm) | Enthusiast realism   |
| **Hardcore** | Dual 775 (OC) or Servo DD | HTD-5M 9–15 mm                  | 12 Nm max             | Advanced / mod tier  |

---

## Mechanical Layout

### Overview

```Gherkin
[ Motor-L ]   [ T60 wheel pulley / 8 mm shaft ]   [ Motor-R ]
      \______________ 3 : 1 GT2 belts _____________/
```

* **Bearings:** 2 × 608ZZ (Ø22 × 7 mm) spaced 40 mm.
* **Shaft:** 8 mm (key/flat) → upgradeable to 20 mm + 6004ZZ for >10 Nm.
* **Motor spacing:** 95–110 mm center; 10 mm slot tension range.
* **Pulleys:** T20 (motor) → T60 (shaft).
* **Belts:** GT2 6 mm (Mini / Standard) → 9 mm (Pro).
* **Upgrade:** Add second motor, belt, and tall cover; no chassis change.

### Motor Plates

* Shared mirrored plate design fits **RS550 or 775**.
* Plate thickness: 4–5 mm.
* Pilot Ø: 12.2 mm (RS550) / 17.2 mm (775).
* Face slots: M3 @ 25 mm (RS550) / M4 @ 29 mm (775).
* Plate mounts: 4 × M5 slots (6.8 mm × 20 mm) on Rift-20 grid (40×40 mm).
* Optional idler: 625ZZ (5×16×5) bearing on M5 post for belt wrap.

---

## Parameters (Fusion 360)

```text
pulley_small = 20
pulley_large = 60
belt_width = 6    // 9 mm optional
center_C = 100
slot_travel = 10
bearing_ID = 8
bearing_OD = 22
bearing_W = 7
plate_thk = 5
m5_slot_w = 6.8
m5_slot_len = 20
rs550_span = 25
rs775_span = 29
pilot_rs550 = 12.2
pilot_775 = 17.2
```

Use these as global parameters for fast iteration.
The motor plates are mirrored; only the **motor plate** and **cover** differ between tiers.

---

## Electrical Overview

| Tier     | Driver                      | PSU                          | Notes                        |
| -------- | --------------------------- | ---------------------------- | ---------------------------- |
| Mini     | 1 × BTS7960                 | 12 V 8–10 A                  | Compact, safe                |
| Standard | 1 × BTS7960                 | 12 V 12–18 A                 | 775 upgrade                  |
| Pro      | 2 × BTS7960 or 1 × H-Bridge | 12 V 25–30 A (ATX 350–450 W) | Dual motors                  |
| Hardcore | H-Bridge / Servo Drive      | 12–48 V 30–40 A              | Requires E-stop & torque cap |

* **Sensor:** AS5600 on wheel shaft (preferred).
* **Wiring:** 16–18 AWG motor leads; twisted; ring lugs or XT30.
* **Bulk caps:** ≥ 4700 µF per motor.
* **Harness:** Rift-15 (HD-15) pinout shared across all tiers.

---

## Firmware & Safety

* **Torque caps:** Mini 3 Nm | Standard 5 Nm | Pro 8 Nm | Hardcore 10–12 Nm unlock.
* **Soft-start & current clamp:** limit spikes and startup surge.
* **Thermal derate:** NTC sensor on motor can.
* **Slew limit:** filters crash-impact torque changes.
* **E-stop:** cuts motor 12 V supply only; logic remains alive.
* **Crash failsafe:** watchdog → zero PWM on USB loss.

---

## Upgrade Summary

| From     | To       | What Changes                                |
| -------- | -------- | ------------------------------------------- |
| Mini     | Standard | Swap RS550→775 motor + pulley               |
| Standard | Pro      | Add second motor + plate + belt + driver    |
| Pro      | Hardcore | Swap belts to HTD-5M or convert to servo DD |

No redesign required — just modular swaps.

---

## Design Notes

* Belt drive provides **mechanical compliance** → safer than DD spikes.
* Dual-side symmetry keeps forces balanced on bearings.
* Two motor bays allow **fan cooling symmetry**.
* **Rift-20 grid** mounts and **M5 structural screws** for consistency.
* **E-stop and firmware torque caps** mandatory above 8 Nm.

---

## BOM Delta Quick View

| Tier     | Motors                | Belts          | Plates            | Covers       | Electronics                    | PSU             |
| -------- | --------------------- | -------------- | ----------------- | ------------ | ------------------------------ | --------------- |
| Mini     | 1 × RS550             | 1 × GT2 6 mm   | 1 motor + 1 blank | Short        | 1 driver                       | 12 V 8–10 A     |
| Standard | 1 × 775               | 1 × GT2 6 mm   | 1 motor + 1 blank | Short        | 1 driver                       | 12 V 12–18 A    |
| Pro      | 2 × 775               | 2 × GT2 9 mm   | 2 motor           | Tall         | 2 drivers or H-bridge + INA219 | ATX 350–450 W   |
| Hardcore | Dual 775 (OC) / Servo | HTD-5M 9–15 mm | Reinforced        | Tall + guard | High-spec bridge / servo drive | 12–48 V 30–40 A |

---

## Summary

The **Rift Dual-Side Base** gives you a *single mechanical platform* from which every tier of wheelbase evolves:

> Start with one motor.
> Add another when you’re ready.
> Change belts, firmware, and plates — not the rig.

---

*(C) Rift Studios – Maker Hardware Division*
Licensed under CERN OHL-S v2.0 (Open Hardware License)

---

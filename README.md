# Rift Sim Hardware Technical Specification

## Version 1.0 (MiniSim baseline)

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

#### M5 (structural)

* Short: **16 mm**
* Medium: **25 mm**
* Long: **35 mm**

> Clearance: **Ø5.5 mm**; slots: **6.8–7.0 mm** wide with end radii; counterbore (optional): Ø11 mm × 2 mm.

### 1.3 Wheel & Hub Interfaces

* **PCDs supported (wheel side):**

  * **6 × 70 mm (Momo/Sparco/Fanatec pattern)** — primary.
  * **3 × 50 mm (OMP/Nardi compact)** — via adapter ring.
* **Bolt hardware:** M5 × 12–16 mm socket head (with washers).
* **Hub center bore:** 52.0 mm nominal (parametric; adapter rings allowed).
* **Quick-release (v1 mini):** Printed bayonet with **steel pins**; detent spring.

### 1.4 Shafts & Bearings

* **Light/mini assemblies:** **8 mm shaft** with **608ZZ** (8 × 22 × 7 mm).
  Bearing pocket: Ø**22.10 mm** × **7.10 mm** (PLA/PETG).
* **Heavy/main shaft (optional upsize):** **20 mm shaft** with **6004ZZ** (20 × 42 × 12 mm).
  Pocket: Ø**42.10 mm** × **12.10 mm**.
* **Spacers:** 1.0 mm (608) / 1–2 mm (6004) printed washers between paired bearings.
* **Shaft collars:** 8 mm split collars for axial retention.

### 1.5 Drive System — **GT2 T20→T60 Baseline**

* **Belt type:** **GT2**, pitch **2.0 mm**.
* **Widths:** **6 mm** (budget/default), **9 mm** (pro/quiet).
* **Pulleys:**

  * **Motor pulley:** **T20** GT2.

    * Bore options: **3.17 mm** (RS550) or **5.0 mm** (775).
    * If mismatched, use 3.17→5.0 coupler or swap pulley bore.
  * **Driven pulley:** **T60** GT2.

    * Bore options: **8.0 mm** (MiniSim 8 mm shaft) or **20.0 mm** (heavy shaft variant) via hub adapter.
* **Reduction ratio (single stage):** **3:1** (20→60).
  Good for compact MiniSim with ~1–1.5 N·m class output (RS550), responsive feel.
* **Two-stage option (upgrade path):** **(20→60) × (20→60) ≈ 9:1**
  Use a second idler/intermediate shaft and a taller top cover.
* **Common closed-loop belt lengths (recommend stocking):**
  **200 mm**, **220 mm**, **250 mm**, **300 mm** (GT2, 6/9 mm width).

  * Mini base typical centers: **~90–115 mm** with 200–250 mm belts (20/60).
* **Center distance & tensioning:** slotted motor plate with **8–12 mm** travel; belt “dull-note” tension (no twang).

> **HTD-5M** (9–15 mm wide) remains a future pro upgrade for quieter, grippier high-torque builds; standard stays GT2 T20/T60.

### 1.6 Motor Mount Standards

* **RS550**: can Ø ≈ 36 mm; **face holes 2×M3 @ 25 mm**; pilot Ø ≈ 12.2 mm.
  Plate: 3–5 mm thick; holes as **3.4 mm slots** radial ±5 mm around pilot.
* **775**: can Ø ≈ 42 mm; **face holes 2×M4 @ 29 mm**; pilot Ø ≈ 17.2 mm.
  Plate: 4–5 mm; holes as **4.5 mm slots** radial ±5 mm.
* **Ventilation:** rear 20–30 mm circular cut-out; side louvers in cover.
* **Couplers:** 3.17↔5.0 mm (clamp style) if needed; otherwise match pulley bore to motor shaft.

### 1.7 Enclosure & Structural Print Rules

* **Walls:** 3.0 mm; **ribs:** 1.6–2.0 mm every 30–40 mm under motor/bearing zones.
* **Clearances:** rotating parts ≥ 1.0 mm radial; belt guard ≥ 2.5 mm offset.
* **Fan mount:** 40 mm exhaust near driver/motor; opposite side intake slots.
* **Desk clamp (mini):** U-clamp, M8 lead screw, TPU pads; or Rift-40 hard-mount.

### 1.8 Panel & Control Cutouts (recap)

* 12 mm push button: **Ø12.0–12.2 mm**, panel 1–6 mm.
* Rotary encoder (EC11): **Ø7.0 mm**, panel 1–5 mm.
* MX switch (box): **14 × 14 mm** square; 19 mm pitch grid.
* Toggle (MTS-102): **Ø6.0 mm**.
* Potentiometer (B10K): **Ø7.0 mm**; 6 mm D-shaft.
* Hall (AS5600): **20 × 20 mm** dual-screw bracket; 6 mm × 2 mm magnet.

---

## 2) Electrical Standards

### 2.1 Universal Cable — **Rift-15 (HD-15/VGA)**

* **Connector:** HD-15 (DE-15) high-density D-Sub.
* **Cable:** any **straight-through VGA** male↔male.
* **Length:** ≤ **1.5 m** recommended for I²C/SPI.
* **Per-pin current:** design ≤ **0.5 A**.
* **Shield:** braid to chassis at **base end only**.

**Pinout (straight-through both ends):**
1 **+5 V** (fused 1 A total)
2 **+3.3 V** (100 mA aux)
3 **GND1** (power)
4 **GND2** (signal)
5 **SDA** (or MOSI/TX)
6 **SCL** (or SCK/RX)
7 **ENC_A**
8 **ENC_B**
9 **BTN_SER / CS**
10 **ID** (resistor ladder to GND)
11 **AUX1** (GPIO/ADC)
12 **AUX2** (GPIO/ADC)
13 **+12 V (light)** (fans/LED ≤ 0.5 A)
14 **GND3** (12 V return)
15 **SHIELD** (to chassis, base end)

#### Rules

* Use **multiple grounds** (3/4/14) to lower return impedance.
* **No motor power** on Rift-15.
* I²C pull-ups 4.7 kΩ; reduce bus speed for longer runs.
* Optional user tiers: screw-terminal DB15 breakout, IDC ribbon DB15, or solder-cup harness.

### 2.2 Internal Connectors

* **JST-XH** for sensors/buttons (2/3/5-pin).
* Twisted pairs for analog lines & encoder A/B.
* Star ground inside base; polyfuse the +5 V peripheral rail.

---

## 3) Electromechanical Standards

### 3.1 Analog Motion Inputs

* **Budget:** **B10K** rotary potentiometer, 270°, 6 mm D-shaft, Ø7 mm panel.
* **Pro:** **AS5600** magnetic rotary sensor; 3.3–5 V; bracket **20×20 mm**; magnet **Ø6 × 2 mm**.

### 3.2 Digital Inputs & Controls

* **Wheel face:** 12 mm panel push + EC11 encoders.
* **Button box:** MX switches, 19 mm pitch; custom keycaps.
* **Toggles:** MTS-102 (6 mm).
* **Joysticks:** PS-style 2-axis analog; Ø26 mm cap opening.
* **Paddles/hidden:** **limit switch** preferred; 6 mm tactiles acceptable.

### 3.3 Bearings & Shafts (recap)

* **608ZZ / 8 mm** (universal).
* **6004ZZ / 20 mm** (heavy/main).
* Pockets add **+0.10 mm** on printed bores; double-bearing with spacer.

---

## 4) Materials, Tolerances & Print Recipe

* **PLA+/PETG**; PETG preferred near motor/driver heat.
* Hole tolerance: PLA +0.10 mm; PETG +0.15 mm.
* Perimeters: 4–5; Top/Bottom: 5–6; Infill: 30–60% (50–60% under motor/bearing blocks).
* Orient parts so long slots align with XY; bosses vertical when possible.

---

## 5) Testing & Safety (baseline)

* **Mechanical:** bearings seat by hand; no cracking at 3–5 N·m on M5; belt guard fitted; fan airflow verified.
* **Electrical:** continuity 1–15; +5 V at 4.9–5.1 V under peripheral load; no encoder jitter with motor energized.
* **FFB bring-up:** torque limit (duty clamp), soft-start; watchdog drops PWM if USB idle >200 ms; e-stop cuts motor supply only.

---

## 6) Naming & Interface Codes

* **RMS-GRID-20** — 20×20 grid
* **RMS-GRID-40** — 40×40 grid
* **RMS-PCD-6x70 / 3x50** — wheel PCDs
* **RMS-BEAR-608 / 6004** — bearing seats
* **RMS-SHAFT-8 / 20** — shaft systems
* **RMS-BELT-GT2-T20-T60-6W** — GT2 20→60, 6 mm width
* **RMS-BELT-GT2-T20-T60-9W** — GT2 20→60, 9 mm width
* **RMS-POT-10K** — B10K mount
* **RMS-HALL-5600** — AS5600 mount
* **RMS-BTN-12 / ENC-7 / TOG-6 / MX-14** — panel elements

---

## 7) Appendices

### A) Screw/Inserts Quick Sheet

* **M3 insert hole:** Ø4.0; depth 4.4–4.6; boss OD ≥ 11.5; relief gap 0.5 mm to nearest wall; ribs 1.6–2.0 mm to floor/walls.
* **M5 slot:** 6.8–7.0 wide; length 20–40; end radius = slot half-width.
* **Edge distances:** M3 boss ≥ 2.5 mm to edge; M5 hole ≥ 3.5–4.0 mm (≥ 6.0 if slotted).

### B) Suggested Belt Inventories (MiniSim)

* **GT2 closed loops:** 200 / 220 / 250 / 300 mm (6 mm width); optional 9 mm width.
* **Pulleys:** T20 motor bores **3.17 & 5.0**; T60 driven bores **8.0 & 20.0** (or with hub adapters).

### C) Panel Hole Librarian (Fusion)

* Parameterized sketches for all listed cutouts; projected from Rift-20 grid; includes counterbore/countersink variants.

### D) Firmware Pin Map (example – Pico)

* GP0 SDA / GP1 SCL / GP2 ENC_A / GP3 ENC_B / GP4 BTN_SER / GP5 AUX1 / GP6 AUX2 / GP7 ID / 3V3 / VSYS / GND.

---

## TL;DR

* **Belts/Pulleys:** **GT2 T20→T60** (3:1) is the **default**, with stocked belt lengths **200–300 mm**; optional second **T20→T60** stage (~9:1).
* **Wheels:** **6×70** primary PCD; **3×50** adapter.
* **Shafts/Bearings:** **8 mm + 608ZZ** standard; **20 mm + 6004ZZ** heavy option.
* **Screws:** only **3 lengths per diameter** (M3: 8/12/16; M5: 16/25/35).
* **Cable:** **HD-15 (VGA)** straight-through for all peripherals.

---

If you want, I can spin this into a **print-ready PDF** with a cover and table of contents, plus supply a **Fusion 360 starter file** (master sketches + parameters for grids, PCDs, belt centers, and panel cutouts) so you can model against the spec immediately.

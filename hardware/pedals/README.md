# 🦶 Rift Standard Pedal Assembly

## Universal Spring-Based Pedal for Makers and Sim Racers

The Rift Standard Pedal represents the foundation of the Rift ecosystem — a fully 3D-printable or laser-cut pedal design that uses **readily available compression springs** and **modular components**.
It’s designed to be scalable, easy to calibrate, and compatible with both analog potentiometers and digital load cells.

---

## ⚙️ Mechanical Overview

**Layout:**
Top-pivot pedal arm with a **rear-mounted compression spring assembly** and **adjustable preload**.
The mechanism provides a linear-to-progressive feel, depending on the spring type and preload.

```Gherkin
   [ Pedal Arm ]
        |
        |      <- Pivot (M8)
        |
       [Linkage Rod]─────[Spring Cartridge]
                             ||
                             ||  <- Preload Adjuster
                          [Mount Base]
```

**Primary Components:**

* Pedal arm (printed or laser-cut)
* Pivot axle (M8 shoulder bolt)
* Linkage rod (M5 threaded rod, 90–120 mm)
* Spring cartridge housing (Rift Standard spec)
* Potentiometer / load-cell bracket
* Base plate (Rift-20 grid pattern)
* Adjustable pedal angle (slot mount at heel)

---

## 🧱 Spring Cartridge System (Rift Spring Standard)

### Spring Specification (Commonly Available)

| Pedal        | Spring Ø | Wire Ø | Free L | Cut L | Source                             | Notes              |
| ------------ | -------- | ------ | ------ | ----- | ---------------------------------- | ------------------ |
| **Throttle** | 8 mm     | 0.6 mm | 305 mm | 40 mm | 304 SS long coil (Temu/AliExpress) | Light, fast return |
| **Clutch**   | 8 mm     | 0.6 mm | 305 mm | 60 mm | Same coil, longer cut              | Progressive feel   |
| **Brake**    | 10 mm    | 0.6 mm | 305 mm | 80 mm | Same coil                          | Heavy resistance   |

**Mounting Bore:**

* Internal barrel Ø = Spring OD + 0.3 mm
* Recommended barrel Ø: 8.3 / 8.3 / 10.3 mm respectively

**End Plates:**

* 2 mm thick printed washers
* Center hole Ø = M5
* M5 washer + nylock nut or preload adjuster head

**Preload System:**

* M6 threaded rod + M6 nut insert in rear cap
* Travel: 10–15 mm (20–30% stiffness adjustment)

---

## 🔩 Hardware List (per pedal)

| Component     | Spec                       | Qty      |
| ------------- | -------------------------- | -------- |
| Pivot Bolt    | M8 x 40 mm shoulder        | 1        |
| Linkage Rod   | M5 threaded rod, 90–120 mm | 1        |
| Clevis Joints | M5 rod-end ball joints     | 2        |
| Spring        | As per tier (8–10 mm OD)   | 1        |
| Barrel        | Printed PETG, Ø 20–24 mm   | 1        |
| Preload Screw | M6 x 50 mm + locknut       | 1        |
| Potentiometer | 10k linear B-type          | 1        |
| Mount Bolts   | M5 x 12 / 16 / 25          | assorted |

---

## ⚡ Sensor Options

| Type                     | Mount                     | Output             | Notes              |
| ------------------------ | ------------------------- | ------------------ | ------------------ |
| **Potentiometer (B10K)** | Lever arm linkage         | 0–5V analog        | Simplest build     |
| **Hall sensor**          | Magnetic shaft end        | 0–3.3V analog      | No wear            |
| **Load Cell (Future)**   | Inline under spring stack | Analog (HX711 amp) | Pro upgrade option |

---

## 🧠 Material & Print Settings

| Component     | Material       | Walls | Infill | Notes                                                     |
| ------------- | -------------- | ----- | ------ | --------------------------------------------------------- |
| Pedal arm     | PETG / CF-PETG | 5     | 40%    | Reinforced section near pivot                             |
| Base plate    | PETG / PLA+    | 5     | 40%    | Use 4–5 mm laser-cut steel or acrylic for high-end builds |
| Spring barrel | PETG           | 4     | 30%    | Use smooth bore sleeve or grease                          |
| Linkages      | PETG / Nylon   | 5     | 60%    | Replace with metal if load cell used                      |

---

## 🧰 Adjustability

| Feature          | Range    | Description          |
| ---------------- | -------- | -------------------- |
| **Pedal angle**  | ±15°     | Slotted heel mount   |
| **Pedal height** | 0–30 mm  | Spacer inserts       |
| **Preload**      | 0–10 mm  | Adjust with M6 screw |
| **Travel limit** | 20–40 mm | Optional stop screw  |

---

## 📦 Modularity

The pedal base fits the **Rift-20 grid system**, allowing easy rearrangement for:

* 2-pedal or 3-pedal layouts
* Shared mounting plates
* Swappable spring cartridges (Spring / Elastomer / Hybrid)

Future upgrade options:

* Load-cell brake module
* Dual-stage clutch (progressive stack)
* Integrated RC-shock parallel damper (bolt-on)

---

## 🛒 Example Spring Sources

| Supplier       | SKU                                     | Size            | Link             |
| -------------- | --------------------------------------- | --------------- | ---------------- |
| Temu           | 304 SS Compression Spring 0.6×8×305 mm  | Cut to 40–80 mm | [Temu link](#)   |
| Temu           | 304 SS Compression Spring 0.6×10×305 mm | Brake stiffness | [Temu link](#)   |
| Amazon         | Uxcell Compression Spring 1×10×80 mm    | Backup source   | [Amazon link](#) |
| Local Hardware | Generic 8–10 mm compression spring      | Any equivalent  | –                |

---

## 🏁 Summary

> The Rift Standard Pedal uses **universally available stainless compression springs**,
> a **modular cartridge** design, and **M5/M6 hardware** —
> ensuring global reproducibility and easy field repair.

Every pedal shares the same mechanical geometry and barrel mount points,
so upgrading from **spring to elastomer to load-cell** requires no redesign — only cartridge swaps.

---

Would you like me to add a **side-view mechanical spec diagram** (like your attached photo but labeled: pivot, linkage, preload, travel arc, etc.) next?
That’d complete this README visually for your GitHub repo.

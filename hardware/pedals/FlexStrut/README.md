# Rift FlexStrut — hidden resistance-tube “strut”

## What it is

A printable, sealed **tension strut** that looks like a gas spring. Inside, one (or two) lengths of **exercise resistance tube** (the “door anchor/cable system” type) are stretched as you pull the rod out, giving a smooth, quiet spring feel. It’s modular, replaceable, and globally sourceable.

---

## Why tension (not compression)?

Resistance tubes work best in **tension**. So we design the strut so **pedal motion pulls the rod outward**, increasing tube stretch. Externally it still looks like a gas strut; functionally it’s a safe, durable “rubber spring.”

---

## Sizes (two cartridges)

* **FlexStrut-Mini**: outer Ø **22 mm**, rod Ø **8 mm**, **stroke 25–30 mm**. Throttle / clutch.
* **FlexStrut-Standard**: outer Ø **28 mm**, rod Ø **10 mm**, **stroke 30–40 mm**. Brake / stiffer clutch.

Both mount with **M5 clevis** or **M8 eye** ends and bolt to your **Rift-20** grid.

---

## Core parts (per strut)

1. **Outer barrel** (printed): tube with internal keyway; looks like a gas strut body.
2. **Piston rod** (printed or 8/10 mm metal): slides in barrel; has **anti-rotation key**.
3. **Rod end**: clevis or eye (M5 bolt).
4. **End cap**: threaded or bayonet cap with **preload adjuster**.
5. **Tube anchor core(s)**: knurled posts that the **resistance tube** slips over and locks with zip-ties + captured washer.
6. **Wiper cap**: thin front cap with a **low-friction bushing** (PTFE ring or printed sleeve).
7. **Travel limiters**: printed collars (5/10/15 mm) to set max stroke.
8. **Safety sleeve** (optional): thin PETG inner sleeve around the tube as a snap-guard.

---

## Resistance tube spec (easy to source)

* **Material**: natural latex resistance tube (fitness).
* **Common sizes** (OD × wall):

  * Light: **10 × 2 mm** (ID 6 mm)
  * Medium: **12 × 2.5 mm** (ID 7 mm)
  * Heavy: **14 × 3 mm** (ID 8 mm)
* **Working elongation**: aim for **100–150%** (2–2.5× length), not more.
* **Temperature**: avoid >60 °C; PETG barrel recommended.

> Use one tube for Mini, **two tubes in parallel** for Standard (two anchor posts side-by-side).

---

## Geometry & forces (rule-of-thumb)

* **Unstretched tube length inside**: 90–120 mm (Mini); 120–160 mm (Standard).
* **Stroke**: 25–40 mm → keeps tube in the sweet spot.
* **Preload**: set by the **end cap screw** (M6 threaded rod) that shortens the tube’s free length by **2–10 mm**.
* **Force range** (very approximate; varies by brand):

  * 10×2 mm @ 30 mm stroke ≈ **10–20 N**
  * 12×2.5 mm @ 30 mm stroke ≈ **20–35 N**
  * 14×3 mm @ 35–40 mm stroke ≈ **35–60 N**
* For a **brake** feel, use **two 12×2.5** or **two 14×3** in parallel, plus **elastomer bumper** at end-stroke for progressive ramp.

---

## Mounting & travel (pedal integration)

* **Eye-to-eye length (retracted)**:

  * Mini ≈ **140–160 mm** (with 25–30 mm stroke)
  * Standard ≈ **170–190 mm** (with 30–40 mm stroke)
* **Ends**:

  * **Rod end**: M5 clevis (10 mm slot) or M8 spherical eye.
  * **Barrel end**: M5/M8 eye with **Rift-20** side plate (20×20 mm holes).
* **Lever geometry**: place the strut slightly **off-pivot** so pedal pull is near-linear over travel; target **20–30°** pedal rotation.

---

## Anti-rotation & smoothness

* **Keyed rod**: D-profile or 2-flat rod; matching keyway in wiper cap → **no tube twist**.
* **Low-friction bushing**: printed PETG sleeve (Ø rod +0.15 mm) or PTFE ring.
* **Light grease**: silicone on rod; none on tube.

---

## Preload & tuning

* **End cap adjuster**: M6 threaded rod presses the **rear tube anchor** forward; locknut to hold setting.
* **Spacer rings**: drop in 5/10 mm rings to quickly increase baseline stiffness.
* **Dual-tube layout** (Standard): run **two anchors** mirrored; change one tube for fine tuning.

---

## Safety & durability

* **Snap-guard**: thin PETG inner sleeve around tubes (optional, recommended for brake).
* **Vent**: 1 mm micro-vents at rear cap so you don’t create vacuum/compression drag.
* **Strain relief**: zip-ties with **cap washers** on anchors; ends cannot slip off.
* **Allergy**: note **latex** in docs; suggest nitrile-glove handling for sensitive users.
* **Inspection**: advise visual check every 3–6 months; replace if cracking appears.

---

## Materials & print recipe

* **Barrel & caps**: PETG (or ABS/ASA), **4–5 walls**, 40–50% infill.
* **Rod**: PETG (for mini) or **8/10 mm metal** (for standard/brake).
* **Threads**: printed trapezoid or straight; **M6 metal rod** for preload screw.
* **Finish**: matte black; optional vinyl wrap for “gas strut” look.

---

## Bill of materials (per strut)

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

## Fusion 360 parameter set (drop-in)

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

## Assembly (2 minutes)

1. Press tube(s) onto **front anchor** on rod; zip-tie + washer.
2. Feed rod into barrel; seat wiper cap (snap/bolts).
3. Insert **rear anchor** with tube tail(s); fit end cap.
4. Turn **M6 preload screw** until desired baseline force; locknut.
5. Bolt barrel eye to frame; rod clevis to pedal lever.
6. Set **travel limiters**; test full stroke; add elastomer if desired.

---

## Pedal recipes

* **Throttle (light)**: Mini strut, **one 10×2 mm** tube, stroke 25–30 mm, preload 3–4 mm.
* **Clutch (snappy)**: Mini strut, **one 12×2.5 mm** tube, stroke 30 mm, preload 5–6 mm, **hard stop** near end for bite.
* **Brake (progressive)**: Standard strut, **two 12×2.5 or 14×3** tubes, stroke 35–40 mm, preload 6–8 mm, **elastomer bumper** in last 5–8 mm.

---

## Looks like a gas strut

* Smooth cylindrical barrel, **wiper cap** with tiny “dust seal” lip, **matte black** finish, subtle **“Rift”** deboss.
* Optional vinyl “pressure warning” sticker for the pro vibe.

---

### TL;DR

Yes — you can absolutely make a **strut-looking module** that hides **exercise resistance tubes** inside. The **Rift FlexStrut** gives you a clean look, tunable force, easy sourcing worldwide, and drop-in compatibility with your pedal designs.

If you want, I’ll format this as a `/pedals/FlexStrut/README.md` plus a tiny **exploded diagram** callout list so your repo is ready for contributors.

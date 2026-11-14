# Varia VS4 Grinder Reference

A quick reference for grind settings and adjustments on the **Varia VS4 single-dose grinder** with its stock **53 mm conical burrs** (200 W brushless motor, planetary gearing). For your personal grind settings that have worked well, see `grind-map.md` in the project root. For the general logging rules, see [`_NOTATION.md`](_NOTATION.md).

---

## Adjustment System

### Stepless Collar With a Printed Absolute Scale

- Grind is set by turning the collar. It is **stepless**: the vendor quotes 10 µm of burr travel per marked line, and any position between the lines is valid.
- The collar is printed with **whole numbers and a line every 0.1** between them. **Higher number = coarser** (3.5 → 3.7 is coarser).
- The adjustment is separate from the body and the bellows, so using the bellows doesn't move your setting. Independent testing found that switching between settings and back returns the same grind (Kaffeemacher).
- A five-hole micro-calibration pattern shifts the whole scale by ±20 µm. If you ever change it, every logged number moves with it, so treat that like a re-zero (see below).

### Logging Your Setting

The VS4 is an **absolute-scale grinder**: record the **dial number as you read it**, to two decimals when you're between lines (e.g. `2.45`). This is the VS4's native code, the same approach `_NOTATION.md` uses for the Sette's `9D` codes. The bare-marks-from-chirp rule for DF64V-style grinders does **not** apply here. The `grind-map.md` header declares the VS4 dial convention.

Like every grind log, the number is an operator coordinate, not a measured particle size. It means nothing on another grinder and stops being comparable after the calibration is moved or the burrs are swapped. If either happens, mark the old rows as superseded, using the divider convention in [`_NOTATION.md`](_NOTATION.md).

---

## Espresso Operating Point

### Starting Window

Espresso on the stock burrs runs roughly **2.0–4.0**. A reviewer dialled a medium-dark blend (18 g in, 36 g out, 25–30 s) at **3.0 on 150 RPM** (Whole Latte Love). Filter is almost a full turn coarser than espresso.

**Sensitivity:** one 0.1 line moves shot time by roughly **1–1.5 s** (up to ~2 s) according to Kaffeemacher's testing. That makes 0.1 your normal adjustment step and 0.05 a fine-tune.

### Espresso Range

These starting points come from the user's observed 2–4 window and the reviewer's 3.0 data point, at a 19–20 g dose. **They are starting points only.**

| Roast Level | Typical Starting Point | Notes |
|-------------|------------------------|-------|
| Light       | 2.0–2.8 | Fine end; dense beans need more resistance |
| Medium      | 2.6–3.4 | Standard espresso window |
| Dark        | 3.2–4.0 | Coarser to avoid over-extraction and bitterness |

**Important:** Actual settings depend on how fresh the beans are (fresher usually means slightly coarser), dose, target ratio and time, and RPM. A bigger dose needs a coarser grind to keep the same shot time.

---

## Motor Speed (RPM)

The VS4 is variable-speed, with a side knob **stepped at 150 / 200 / 250 / 300 RPM**. Log RPM as a plain integer in its own column, as `_NOTATION.md` describes.

**What independent testing found for espresso:**

- **Kaffeemacher** (particle analysis) recommends **150 RPM** for espresso. Their 150 RPM grind had a narrower main peak and fewer fines (~36% vs ~39%), and a more balanced cup. They see little reason to use 300 except for speed.
- **Whole Latte Love** (tasting + refractometer): **150 RPM** gave a sweet, chewy shot with chocolate, honey and toasted marshmallow. **300 RPM** extracted more (EY ~20.4% vs ~18%) but was clearly more bitter and roasty, with little sweetness. 300 RPM needed a slightly coarser dial (~3.15 vs 3.0) to match shot time.
- The two disagree on which speed produces more fines, so the mechanism is unsettled. Both landed on **lower RPM for espresso**.

**Starting point:** 150–200 RPM for espresso.

### RPM as a dial-in lever

**RPM is the last lever, not the first.** Dial grind, ratio, temperature and puck prep first. Change RPM only as a deliberate, logged experiment. It is **never** a fix for channeling: sour *and* bitter together is a puck-prep problem.

After any RPM change, **re-dial grind to get back your target shot time**, and let the shot timer tell you which way to move. Two reviewers and one coffee each isn't a law. Your own logged RPM↔taste data is the real signal.

---

## Burr Character Note

> **This is a tendency drawn from reviews and the vendor's description, not a measured guarantee. Judge by the cup.**

The stock burr is a **53 mm conical** (described as six-cutting-edge / multi-angle). Conical burrs are generally said to favour body and a rounder, more blended cup over flat-burr separation and clarity. That is a contested generalisation, but the VS4's espresso reviews (chocolate, honey, chewy texture at 150 RPM) fit it. Varia itself points customers after maximum clarity from fruity coffees to the larger VS6. For light roasts on this grinder, extraction (temperature, pre-infusion, ratio) does more to cut sourness than chasing clarity.

---

## Quick Adjustment Guide

Starting from a working shot:

| Problem | Adjustment | Magnitude |
|---------|------------|-----------|
| Shot too fast, tastes sour | Go finer (lower number) | 0.1 (≈1–1.5 s) |
| Shot too slow, tastes bitter | Go coarser (higher number) | 0.1 (≈1–1.5 s) |
| Close, just fine-tuning | Finer or coarser | 0.05 |
| Large correction needed (≥5 s off) | Move 0.3–0.5, then fine-tune | 0.3+ |
| Dose increased to fill the bed | Go coarser to hold shot time | Small step (0.05–0.1), then check the shot time |
| Both sour and bitter | **Do not adjust grind**: fix puck prep (channeling) | — |

Always say the direction and the target number ("coarser, to 3.7") rather than "increase/decrease", which reads both ways.

---

*Sources: Whole Latte Love VS4 review (espresso settings, RPM tasting); Kaffeemacher VS4 test (particle analysis, sensitivity per line, repeatability); retailer specifications (53 mm conical, 150–300 RPM in 50 RPM steps). For your personal successful settings, see `grind-map.md` in the project root. For the logging format, see [`_NOTATION.md`](_NOTATION.md).*

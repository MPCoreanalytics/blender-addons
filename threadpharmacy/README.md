# ThreadPharmacy

**Rx for broken threads.** Rebuild clean ISO threads on 3D-scanned parts, directly in Blender.

<img src="images/threadpharmacy-concept.png" alt="ThreadPharmacy: scanned thread rebuilt as an ISO thread" width="100%">

*Concept visualization on synthetic data.*

Threads are the weakest spot in almost every scan. Crests come out rounded, the profile drowns in noise, small holes are only half visible, and the axis is a degree or two off. Print it like that and the bolt won't go in.

ThreadPharmacy replaces the scanned thread with a mathematically correct one, on the right axis, in the scan itself.

| | |
|---|---|
| **Status** | Next release |
| **Blender** | 4.2 LTS and newer |
| **Family** | Sibling of [MeshPharmacy](../meshpharmacy/). Clean the scan first, then rebuild the threads |

---

## Workflow

```
Open scan  ►  Pick thread (click)  ►  axis + diameter + pitch detected  ►  check / change size
           ►  Generate preview  ►  Apply  ►  repeat for the next thread  ►  export STL + report
```

1. **Click** an external thread (pin, bolt) or an internal one (tapped hole).
2. ThreadPharmacy fits the **axis and diameter**, measures the **pitch** and matches the result against the standard tables. You see the match with a confidence value, for example `M8×1.25 · 92%`.
3. Not sure? Pick the thread from a short list of the closest matches, or choose it manually.
4. **Shift-click a flat face** next to the thread to set it as the datum. The axis is measured against it and can be snapped perpendicular. The report shows how much was corrected.
5. **Apply.** The scanned thread is cut away and replaced with an ideal one. The result is a closed, manifold mesh.

## What it handles

- **Metric ISO threads**, coarse and fine pitch, right- and left-hand (ISO 68-1 profile, ISO 261 sizes).
- **External and internal threads**, through and blind holes, entry chamfer.
- **Datum-based perpendicularity:** axis angle to the datum face, deviation over the thread length, optional snap.
- **Look-alike sizes** that differ only in pitch, such as M10×1.5 vs M10×1.25, or M8×1.25 vs 5/16"-18. Pitch decides, and you get a choice when the scan can't tell.
- **Report** (JSON/CSV): measured vs nominal values for every thread.
- **Non-destructive until Apply:** detected threads stay editable in the panel, and every Apply can be undone.

Unified threads (UNC/UNF), tolerance classes and a print-fit clearance option are planned for later versions.

## What to expect from your scan

The smallest thread that can be detected automatically depends on your scanner, not on the add-on. The thread depth must stand out clearly from the scan noise. On fine threads, ThreadPharmacy still finds the axis and diameter, and you set the pitch manually.

Internal threads are harder to scan than external ones because the scanner often only sees the entry. That is why a datum face is used by default for holes.

---

Part of the [Mirosław Pałucki Blender add-ons](../) family · Documentation © 2026 Mirosław Pałucki, [CC BY-NC-ND 4.0](../LICENSE)

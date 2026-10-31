<p align="center">
  <img src="assets/banner.png" alt="Mirosław Pałucki · Blender add-ons for 3D scans, meshes and reverse engineering" width="100%">
</p>

# Blender add-ons for 3D scans, meshes and reverse engineering

This repository is the public home of my Blender add-ons. It holds the product pages, user guides and release notes.
The add-ons are distributed through [Superhive (formerly Blender Market)](https://superhivemarket.com). The source code ships with every purchase under the GPL, as Blender add-ons require.

All the tools target the same job: you have a raw scan, and you need geometry you can **3D print, measure, boolean or model on**, without leaving Blender.

---

## Add-ons

| Add-on | What it does | Status |
|---|---|---|
| **[MeshPharmacy](meshpharmacy/)** | Cleans, repairs, reduces and quad-remeshes dense scan meshes. Removes hidden interior shells, fills holes, reports whether the result is watertight. Always works on a copy. | v1.3 |
| **[ThreadPharmacy](threadpharmacy/)** | Click a thread on a scan, get its axis and size, and replace it with a clean ISO thread aligned to a datum face. | Next release |

<p align="center">
  <a href="meshpharmacy/"><img src="meshpharmacy/images/interior-walls.png" height="210" alt="MeshPharmacy: interior shells removed"></a>
  <a href="threadpharmacy/"><img src="threadpharmacy/images/threadpharmacy-concept.png" height="210" alt="ThreadPharmacy concept"></a>
</p>

More tools for the same pipeline (alignment, measurement, scan-to-CAD helpers) will be added here as they are released.

---

## How the family fits together

```
 3D scanner  ──►  STL / OBJ  ──►  MeshPharmacy  ──►  ThreadPharmacy  ──►  3D print / CAD / Boolean
                                  clean · repair      rebuild threads
                                  reduce · remesh     on a clean mesh
```

Each add-on does one job well and leaves your original object untouched. They follow the same rules:

- **Non-destructive.** Every operation creates a new, clearly named object. The source is hidden, never edited.
- **Measured, not guessed.** Every run ends with a short report: face counts, deviation from the source, watertight check.
- **Responsive on big scans.** Heavy work runs in a background Blender process, so the viewport stays usable on multi-million-triangle meshes.
- **No extra installs.** Only what ships with Blender. No pip packages, no external binaries.
- **Current Blender.** Built and tested for Blender 4.2 LTS and newer.

---

## About me

**Mirosław Pałucki** · [LinkedIn](https://www.linkedin.com/in/mirosław-pałucki-7948ba35)

Business analyst with 17+ years of international experience in aerospace, automotive and battery manufacturing, working where engineering, quality and IT meet. My foundation is industrial metrology, quality management and precision inspection: SPC, MSA, ISO 9001, ISO 17025 and NADCAP on one side, SQL, Python, Power BI and Tableau on the other.

Next to that I work on reverse engineering, 3D scanning (structured light, laser, NIR) and physical-to-digital workflows. I build tools and add-ons for Blender and Autodesk Fusion that close the gap between raw scan data and production-ready CAD geometry: mesh processing, surface reconstruction and automated data preparation.

These add-ons started as tools I needed myself: raw scans that were too heavy, full of hidden junk, or had threads too blurred to use. I build them the way I expect an engineering tool to behave. Predictable, reversible, and honest about what it changed.

---

## Support

- **Questions and bug reports:** use the message function on the product's Superhive page, or open an [issue](../../issues) in this repository.
- **Documentation:** each add-on folder has a README and a PDF guide.

## License

Documentation, images and text in this repository: [CC BY-NC-ND 4.0](LICENSE).
The add-ons are licensed **GPL-3.0-or-later** and distributed through Superhive.

© 2026 Mirosław Pałucki

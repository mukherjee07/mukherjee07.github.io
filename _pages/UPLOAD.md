# Website update, 2 Nov 2026 (matches poster v6.4)

Upload each file to this path in mukherjee07.github.io (GitHub web UI, "Add files via upload" into the folder):

| File | Repo path | What changed |
|---|---|---|
| Vision.md | _pages/Vision.md | CO2/CH4 paragraph and caption (uptake vs pressure, Fig. 9 effect); multi-fidelity paragraph and caption (acquisition function, not only max sigma) |
| vision_co2_ch4.png | assets/images/vision_co2_ch4.png | real GCMC data, Cu-BTC 240 K: 11.6% CO2 rises then falls, 98% CO2 keeps rising |
| vision_multifidelity.png | assets/images/vision_multifidelity.png | acquisition strip: EI picks the next point, away from max sigma |
| vision_data_fusion.png | assets/images/vision_data_fusion.png | label now "acquisition picks the next simulation or experiment" |
| Research.md | _pages/Research.md | one new figure line in the water-vapor section |
| water_clusters_ICC.png | assets/images/water_clusters_ICC.png | new: water clusters in the five pores (Langmuir 2025, Fig. 2a renders) |

Vision_edit.md and build_vision.py are the editable source for Vision.md (python build_vision.py); they do not get uploaded.
Built on the live site as of commit 06693cfd; Vision.md and Research.md differ from it only in the lines listed above.

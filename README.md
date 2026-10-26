# Disk Scheduling Simulator: LOOK vs C-LOOK

An interactive, single-page web simulator comparing the **LOOK** and **C-LOOK** disk scheduling algorithms for Hard Disk Drives (HDDs).

Built for the **Operating Systems Self Learning Assessment (Stage 2)**, Department of Computer Engineering, Second Year, Semester III, AY 2025–2026.

---

## 👥 Authors
- **Jainel Vora** (PRN: `125BTCM1069`)
- **Anikshaa Yadav** (PRN: `125BTCM1021`)
- **Institution:** Shah & Anchor Kutchhi Engineering College (SAKEC)

---

## 🚀 Key Features

- **No Frameworks or Dependencies:** Built purely with vanilla HTML5, CSS3, and JavaScript in a single self-contained file (`index.html`).
- **Interactive Visualizations:**
  - Stacked horizontal cylinder track lines (0 to `Disk Size - 1`) with animated polyline trajectories and moving head cursors.
  - Distinct algorithmic color-coding: **LOOK (Electric Blue)** vs **C-LOOK (Vivid Orange)**.
  - Return jump in C-LOOK highlighted with an arc and seek distance badge.
  - Time vs Track progression graph plotting head movement over discrete time steps.
- **Dynamic Mode:** Inject new I/O requests mid-simulation (via click on track or manual entry) with automatic dynamic re-planning and track region service distribution heatmaps.
- **Playback Controls:** Play, pause, step forward, step backward, reset, and variable speed slider (0.5x to 3.0x).
- **Automated Verification & Self-Test:** Integrated 10-test automated verification suite reproducing the exact metrics and benchmarks from the project report (Cases A through F, plus FCFS, SSTF, SCAN, and C-SCAN baselines).
- **Batch Experimentation:** Run 100 uniform random workloads with comparative bar charts for Total Head Movement (THM), Average Seek Distance (ASD), and Maximum Completion Distance.
- **Data Export:** Instant CSV export of configuration, algorithmic summaries, per-request completion distances, and baselines.
- **Mathematical Theory & Limitations:** Embedded documentation covering seek time physics, the theorem `C-LOOK - LOOK = p - L`, hardware constraints (rotational latency, actuator acceleration curves, SSD NVMe inapplicability), and UN SDG 4 (Quality Education) alignment.

---

## 📊 Benchmark Test Case A

| Algorithm | Service Order | THM (Tracks) | ASD (Tracks/Req) | Avg Completion | Max Completion |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **LOOK** | 65, 67, 98, 122, 124, 183, 37, 14 | **299** | **37.38** | **114.50** | **299** |
| **C-LOOK (Jump Counted)** | 65, 67, 98, 122, 124, 183, 14, 37 | **322** | **40.25** | **120.25** | **322** |
| **C-LOOK (Jump Excluded)** | 65, 67, 98, 122, 124, 183, 14, 37 | **153** | **19.13** | **120.25** | **153** |
| **FCFS (Baseline)** | 98, 183, 37, 122, 14, 124, 65, 67 | 640 | 80.00 | — | — |
| **SSTF (Baseline)** | 65, 67, 37, 14, 98, 122, 124, 183 | 236 | 29.50 | — | — |
| **SCAN (Baseline)** | 65, 67, 98, 122, 124, 183, 199, 37, 14 | 331 | 41.38 | — | — |
| **C-SCAN (Baseline)** | 65, 67, 98, 122, 124, 183, 199, 0, 14, 37 | 382 | 47.75 | — | — |

---

## 🛠️ How to Run

Simply open `index.html` in any modern web browser:
```bash
open index.html
```
No web server, node packages, or build tools required.

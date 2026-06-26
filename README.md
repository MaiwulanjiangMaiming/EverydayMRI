# Everyday MRI

Read 3 MRI papers every day, take deep notes, and learn scientific writing. Focus on **Non-Cartesian Magnetic Resonance Fingerprinting (MRF)**, walking from physics fundamentals all the way to advanced reconstruction.

> Plan page (on my website): <https://maiwulanjiangmaiming.github.io/pages/everyday.html>
> Full reading roadmap: [roadmap.md](roadmap.md)

## How I learn

1. **Find the paper** — follow the phase order in [roadmap.md](roadmap.md); pick 3 per day.
2. **Read deeply** — go through every paragraph; nail every equation and figure.
3. **Write a reading note** — one Markdown file per paper under `notes/<phase>/`, containing:
   - One-line summary + core method
   - Key equations / figure interpretation
   - What it means for my own research
   - **Writing lessons** (how the authors tell their story)
4. **Sync** — update `index.json`; the website picks it up automatically.

## Directory layout

```
EverydayMRI/
├── README.md            this file
├── roadmap.md           full 8-phase roadmap + reading list
├── index.json           global index (the website reads this)
└── notes/
    ├── P0/              MRI physics & signal fundamentals
    ├── P1/              sampling & reconstruction basics
    ├── P2/              non-Cartesian sampling
    ├── P3/              quantitative imaging basics
    ├── P4/              MRF principles
    ├── P5/              non-Cartesian MRF (core)
    ├── P6/              pulse-sequence design (emphasis)
    └── P7/              advanced reconstruction & frontier
```

## Note naming

`<phase>-<number>-<first-author>-<year>.md`, e.g. `P0-01-bloch-1946.md`.

## Status

Each paper goes `planned` → `reading` → `done`. After finishing a note, set the matching entry's `status` to `done` in `index.json`.

## The 8 phases

| Phase | Topic | Focus |
|-------|-------|-------|
| P0 | MRI physics & signal fundamentals | spin precession, Bloch equation, K-space, Fourier imaging |
| P1 | sampling & reconstruction basics | Cartesian, SENSE/GRAPPA, compressed sensing, ESPIRiT |
| P2 | **non-Cartesian sampling** | Radial, Spiral, NUFFT, gridding, density compensation |
| P3 | quantitative imaging basics | T1/T2 mapping, Look-Locker, DESPOT |
| P4 | MRF principles | Ma 2013, FISP-MRF, dictionary matching, SVD compression |
| P5 | **non-Cartesian MRF (core)** | Spiral/Radial MRF, reconstruction, DL-MRF |
| P6 | **pulse-sequence design** | bSSFP/FISP/FLASH, Pulseq, sequence diagrams |
| P7 | advanced reconstruction & frontier | DL reconstruction, subspace, motion correction, real-time |

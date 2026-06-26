# CLAUDE.md — Instructions for Claude Code

## Project Overview

**EverydayMRI** is a daily MRI reading journal. The author reads **3 papers per day**, writes deep reading notes for each, and tracks progress through an **8-phase roadmap** from MRI physics basics to advanced non-Cartesian MRF reconstruction.

The author's research focus is **non-Cartesian Magnetic Resonance Fingerprinting (MRF)** — spiral/radial sampling, dictionary matching, and deep learning reconstruction.

This repo is consumed by a personal website (`MaiwulanjiangMaiming.github.io`) which renders the roadmap and notes live via jsDelivr CDN.

## Directory Structure

```
EverydayMRI/
├── CLAUDE.md              ← this file
├── README.md              ← project overview (public-facing)
├── roadmap.md             ← full 8-phase reading plan (~120 papers)
├── index.json             ← master data: all phases, papers, statuses
├── .gitignore
└── notes/
    ├── P0/                ← Phase 0: MRI Physics Foundations
    │   ├── P0-01-bloch-1946.md
    │   ├── P0-02-lauterbur-1973.md
    │   └── P0-03-kumar-ernst-1975.md
    ├── P1/                ← Phase 1: Sampling & Reconstruction
    ├── P2/                ← Phase 2: Non-Cartesian Imaging
    ├── P3/                ← Phase 3: Quantitative MRI
    ├── P4/                ← Phase 4: MRF Principles
    ├── P5/                ← Phase 5: Non-Cartesian MRF (core)
    ├── P6/                ← Phase 6: Pulse Sequences
    └── P7/                ← Phase 7: Deep Learning Reconstruction
```

## The 8 Phases

| Phase | Title | Focus |
|-------|-------|-------|
| P0 | MRI Physics Foundations | Bloch equations, relaxation, signal formation |
| P1 | Sampling & Reconstruction | k-space, Fourier transform, sampling theory |
| P2 | Non-Cartesian Imaging | Spiral, radial, rosetter trajectories |
| P3 | Quantitative MRI | T1/T2/T2* mapping, golden-angle, MR fingerprinting origins |
| P4 | MRF Principles | Dictionary, matching, SVD, fingerprinting framework |
| P5 | Non-Cartesian MRF | **Core focus** — spiral MRF, radial MRF, joint recon+mapping |
| P6 | Pulse Sequences | **High priority** — sequence design, SSFP, bSSFP, FISP, FLASH |
| P7 | Deep Learning Reconstruction | Unrolled networks, MoDL, physics-informed recon |

## Daily Workflow (when the user says "I read a paper" or similar)

### Step 1 — Write the reading note

Create a new Markdown file at `notes/PX/PX-XX-short-name.md`, where:
- `PX` = phase number (P0–P7)
- `XX` = zero-padded paper number within that phase (01, 02, 03, ...)
- `short-name` = first author's last name + year (e.g., `ma-2013`, `jiang-2017`)

**Use this exact template** (copy structure from existing notes):

```markdown
---
id: PX-XX
title: "Full Paper Title"
authors: "Author1 A., Author2 B."
year: YYYY
venue: "Journal or Conference Name"
phase: PX
date: YYYY-MM-DD
status: done
tags: [keyword1, keyword2, keyword3]
---

# PX-XX · Paper Title — Author (Year)

> **One-line summary**: one sentence capturing the paper's core contribution.

## Core content

[2–4 paragraphs explaining the key ideas, equations, methods. Include LaTeX
for important equations using $$ ... $$ blocks. Be specific — not vague.]

## Key understanding

| Concept | Insight |
|---------|---------|
| ... | ... |

## Implications for my research

[How does this paper connect to non-Cartesian MRF? What technique can I
borrow? What limitation does it reveal?]

## Writing lessons

[What makes this paper well/poorly written? What structural or rhetorical
technique can I learn from?]

## To dig deeper

- [Follow-up papers, code repos, or concepts to explore next]
```

### Step 2 — Update index.json

Find the matching paper entry in `index.json` and update two fields:

```json
{
  "id": "PX-XX",
  "title": "Full Paper Title",
  ...
  "note": "notes/PX/PX-XX-short-name.md",   ← add this path
  "status": "done"                           ← change from "planned" to "done"
}
```

### Step 3 — Sync the website (optional, if asked)

```bash
cp index.json /Users/rock/Interesting_Projects/Personal_Website_of_MawlanM/data/everyday.json
```

### Step 4 — Commit

```bash
git add -A
git commit -m "Add note: PX-XX Paper Title"
```

## index.json Schema

```json
{
  "title": "Everyday MRI",
  "subtitle": "Daily MRI reading journal",
  "repo": "https://github.com/MaiwulanjiangMaiming/EverydayMRI",
  "lastUpdated": "YYYY-MM-DD",
  "phases": [
    {
      "id": "P0",
      "title": "MRI Physics Foundations",
      "goal": "Understand signal formation, relaxation, and the Bloch equation.",
      "papers": [
        {
          "id": "P0-01",
          "title": "Paper Title",
          "authors": ["Author A", "Author B"],
          "year": 1946,
          "venue": "Physical Review",
          "topic": "short topic description",
          "note": null,              ← null for planned, path string for done
          "status": "planned"        ← "planned" | "reading" | "done"
        }
      ]
    }
  ]
}
```

## Key Conventions

1. **All content in English** — notes, README, index.json, commit messages.
2. **Note filenames**: `PX-XX-author-year.md` (lowercase, hyphens, no spaces).
3. **LaTeX in notes**: use `$inline$` and `$$display$$` syntax.
4. **Status values**: `planned` (not yet read), `reading` (in progress), `done` (note written).
5. **The `note` field** in index.json must exactly match the file path (relative to repo root).
6. **3 papers per day** — when adding new notes, typically process all 3 from the same phase in one session.
7. **Phase P5 (Non-Cartesian MRF) and P6 (Pulse Sequences)** are the highest priority for the author's research.

## Important: Do NOT

- Do NOT create separate repos per paper — everything stays in this single repo.
- Do NOT modify the website code directly — only sync `index.json` → `data/everyday.json`.
- Do NOT add papers that aren't in the roadmap without asking the user first.
- Do NOT change the phase structure (P0–P7) without explicit user request.

---
id: P0-02
title: "Image Formation by Induced Local Interactions; Examples Employing Magnetic Resonance"
authors: "Lauterbur P.C."
year: 1973
venue: "Nature"
phase: P0
date: 2026-06-26
status: done
tags: [MRI foundation, gradient encoding, projection reconstruction, foundational]
---

# P0-02 · The Birth of MRI — Lauterbur (1973, Nature)

> **One-line summary**: superimpose a **linear gradient field** on the homogeneous main field so that protons at different locations resonate at different frequencies, enabling spatial localization and imaging — MRI is born.

## Core content

Lauterbur's key leap: **encode position with a magnetic field that varies linearly in space**.

With gradient $G_x$ applied, the resonance frequency at position $x$ becomes:

$$\omega(x) = \gamma\,(B_0 + G_x \cdot x)$$

So **frequency = position**. One acquisition yields a projection along x; rotate the gradient direction, collect projections at multiple angles, then (borrowing from CT) back-project to reconstruct a 2D image.

The paper demonstrates this with two capillaries of water and heavy water, obtaining the first 2D NMR image.

## Key understanding

```
Homogeneous B0  →  all protons share one frequency, cannot localize
Add Gx          →  frequency varies with position, can localize
Rotate G        →  get multiple projections  →  back-project → image
```

## Implications for my research

1. **The root of all MR encoding**: frequency encoding, phase encoding, K-space sampling — all fundamentally "use gradients to make frequency/phase vary with position". The spiral/radial non-Cartesian trajectories I work on differ only in **scan path**; the physical root is identical.
2. **Projection reconstruction = the ancestor of radial sampling**: Lauterbur's back-projection is the earliest form of radial K-space sampling. From here you can trace the historical lineage straight to my main battlefield (radial MRF).
3. **The paradigm shift from "measuring signal" to "forming an image"**: the greatest value of this paper is proving NMR signal can carry spatial information. Grasping this leap is the prerequisite for understanding all later acceleration/reconstruction work.

## Writing lessons (from Lauterbur)

1. **Minimal length**: a short Nature paper that explains a brand-new concept in the fewest possible words. No redundancy.
2. **Analogy to a known problem**: maps "MR imaging" onto the already-solved "CT back-projection" — **explaining the unknown with what the reader already knows** is a powerful tool for convincing reviewers/readers.
3. **Minimal viable experiment**: two capillaries are enough to prove the concept. **A good paper doesn't pile on experiments; it articulates a new concept.**

## To dig deeper

- [ ] Derive for yourself: given a set of radial projections, how to reconstruct the image via back-projection (write a 1D/2D demo).
- [ ] Think: why did people later abandon direct back-projection in favor of K-space + Fourier reconstruction? (leads into P0-03)

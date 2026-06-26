---
id: P0-03
title: "NMR Fourier Zeugmatography"
authors: "Kumar A., Welti D., Ernst R.R."
year: 1975
venue: "Journal of Magnetic Resonance"
phase: P0
date: 2026-06-26
status: done
tags: [Fourier imaging, K-space, foundational]
---

# P0-03 · Fourier Imaging & K-space — Kumar, Welti, Ernst (1975)

> **One-line summary**: use three orthogonal gradients for phase encoding and frequency encoding, then reconstruct via Fourier transform — establishing the **K-space paradigm** still in use today.

## Core content

Cast imaging rigorously as a "sampling + inverse transform" math problem:

Let spin density be $\rho(\vec r)$. Under gradient $\vec G(t)$, the received signal is the Fourier transform of the spin density:

$$s(t) = \int \rho(\vec r)\, e^{-i\,2\pi\,\vec k(t)\cdot \vec r}\, d\vec r$$

where the **K-space position** $\vec k(t) = \frac{\gamma}{2\pi}\int_0^t \vec G(\tau)\,d\tau$ is the time integral of the gradient.

- Phase encoding: a brief gradient pulse changes the phase of different rows (changes $k_y$).
- Frequency encoding: a gradient applied during readout (advances along $k_x$).
- Reconstruction: inverse Fourier transform of the acquired K-space data → $\rho(\vec r)$.

## Key understanding

| Quantity | Meaning | How to control |
|----------|---------|----------------|
| $\vec k(t)$ | K-space sampling position | The **time integral** of the gradient |
| K-space center | Determines overall contrast | Low-frequency signal |
| K-space periphery | Determines fine resolution | High-frequency signal |
| Trajectory shape | Cartesian / radial / spiral | Timing of gradient waveforms |

## Implications for my research

1. **K-space is the coordinate system of all reconstruction**. The essence of non-Cartesian sampling is letting $\vec k(t)$ follow a non-grid path (radial lines, spirals). Because the samples don't lie on a Cartesian grid, reconstruction needs **NUFFT / gridding** (→ P2).
2. **"The time integral of the gradient" is the key intuition**: designing a spiral means designing $G_x(t), G_y(t)$ so that $\vec k(t)$ unwinds as a spiral. This unifies "sequence design" with "trajectory design".
3. **K-space center vs periphery**: understanding this is why MRF often uses center-dense trajectories like radial/spiral — they are robust to motion and more sensitive to parameter estimation.

## Writing lessons (from Ernst)

1. **Formalize first, then implement**: cast imaging as a strict integral transform before discussing how to sample. **Mathematical formalization makes a method generalizable and provable** — this is why this paper could define the paradigm of an entire field.
2. **Define a new coordinate system**: they effectively defined "K-space", a concept used for 50 years since. **Whoever defines the coordinate system of a problem leads the field.**
3. **Transfer from spectroscopy**: Ernst migrated the Fourier idea from NMR spectroscopy to imaging — the power of **cross-domain analogy**.

## To dig deeper

- [ ] Derive: why is $k(t)$ the integral of the gradient rather than the gradient itself? (start from precession phase = frequency × time)
- [ ] Compare Lauterbur's back-projection with Fourier reconstruction here — why did the latter win? (accuracy, efficiency, ease of acceleration)

---

## Day 1 recap (P0-01 → P0-03)

These three papers string together the **physical and imaging foundation** of MRI:
- **Bloch**: how the signal arises (precession and relaxation of M)
- **Lauterbur**: how to give the signal a spatial location (gradient encoding)
- **Kumar/Ernst**: how to systematically turn signal back into an image (K-space + Fourier)

Next (P0-04 onward): Twieg abstracts the K-trajectory into unified math, Mansfield's EPI, then SNR and echoes — solidifying the foundation before entering sampling & reconstruction (P1).

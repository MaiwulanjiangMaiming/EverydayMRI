# Everyday MRI · Reading Roadmap

Focused on **Non-Cartesian Magnetic Resonance Fingerprinting (MRF)**. Starting from MRI physics, the path goes through sampling, reconstruction, quantification, and MRF, eventually returning to the core direction, with **pulse-sequence design** woven throughout.

- Pace: **3 papers per day**, paragraph-by-paragraph close reading + a reading note.
- Numbering: `P<phase>-<number>`, mapping to files under `notes/P<phase>/`.
- Order: top-to-bottom within each phase is the recommended order; the first 3 of each phase are that phase's must-read intro.
- Marks: ⭐ = foundational must-read; 🔧 = method/engineering; 🧬 = theory/derivation; 🎯 = directly relevant to my direction.

> Titles/years are as accurate as I can make them; some early papers are annotated as "author + year + keyword" — verify against the original when reading.

---

## P0 · MRI Physics & Signal Fundamentals (12)

**Goal**: build complete physical intuition for how a spin becomes an image pixel — how signal arises, is encoded, and is reconstructed.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P0-01 | ⭐🧬 Bloch F. *Nuclear Induction* | 1946·Phys Rev | The starting point of everything. The Bloch equation describes precession and relaxation of the magnetization. |
| P0-02 | ⭐ Lauterbur P.C. *Image Formation by Induced Local Interactions; Examples Employing Magnetic Resonance* | 1973·Nature | The birth of MRI. Gradient localization → imaging. |
| P0-03 | ⭐🧬 Kumar A., Welti D., Ernst R.R. *NMR Fourier Zeugmatography* | 1975·J Magn Reson | 3D Fourier imaging; establishes the concept of K-space. |
| P0-04 | ⭐ Twieg D.B. *The k-trajectory formulation of the NMR imaging process…* | 1983·Med Phys | The unified math of the **K-trajectory** — the key to understanding sampling. |
| P0-05 | ⭐ Mansfield P. *Multi-planar image formation using NMR spin echoes* | 1977·J Phys C | EPI — the origin of ultra-fast sampling. |
| P0-06 | 🧬 Ernst R.R., Anderson W.A. *Application of Fourier Transform Spectroscopy to Magnetic Resonance* | 1966·Rev Sci Instrum | Pulse + Fourier; establishes modern NMR/MR signal processing. |
| P0-07 | Hoult D.I., Richards R.E. *The signal-to-noise ratio of the NMR experiment* | 1976·J Magn Reson | The essence of SNR; understanding coils and noise. |
| P0-08 | Edelstein W.A. et al. *The intrinsic signal-to-noise ratio in NMR imaging* | 1986·Magn Reson Med | Voxel, field strength, and SNR. |
| P0-09 | 🧬 Haacke E.M. et al. *Phase & susceptibility (chemical shift basics)* | — | Intro to phase and susceptibility. |
| P0-10 | 🧬 Hennig J. *Echoes—how they arise and what we can do with them* | 1991·J Magn Reson | How echoes form — the basis for understanding every sequence. |
| P0-11 | 🧬 Le Bihan D. et al. *Separation of diffusion and perfusion…* | 1986·Radiology | Diffusion/perfusion signal; builds the "signal = physical quantity" intuition. |
| P0-12 | 🔧 Bernstein M.A. et al. *Handbook of MRI Pulse Sequences* (selected chapters) | 2004·Book | Ties the previous 11 into a system; keep as a reference. |

**Phase output**: be able to explain, in your own words, "how a hydrogen proton turns into a pixel in an image".

---

## P1 · Sampling & Reconstruction Basics (15)

**Goal**: master every classic weapon for undersampling and reconstruction — the foundation for later non-Cartesian and MRF reconstruction.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P1-01 | ⭐ Pruessmann K.P. et al. *SENSE: Sensitivity encoding for fast MRI* | 1999·MRM | Image-domain parallel imaging; understand coil sensitivity. |
| P1-02 | ⭐ Griswold M.A. et al. *Generalized autocalibrating partially parallel acquisitions (GRAPPA)* | 2002·MRM | K-space-domain parallel imaging; core reconstruction idea. |
| P1-03 | ⭐ Sodickson D.K., Manning W.J. *Simultaneous acquisition of spatial harmonics (SMASH)* | 1997·MRM | Early parallel-imaging idea; understand the history. |
| P1-04 | ⭐🔧 Lustig M., Donoho D., Pauly J.M. *Sparse MRI: The application of compressed sensing for rapid MR imaging* | 2007·MRM | Foundational CS MR reconstruction; sparsity/TV. |
| P1-05 | ⭐🔧 Uecker M. et al. *ESPIRiT—An eigenvalue approach to autocalibrating parallel MRI* | 2014·MRM | The engineering standard for coil-sensitivity estimation. |
| P1-06 | 🔧 Lustig M., Pauly J.M. *SPIRiT: Iterative self-consistent parallel imaging reconstruction* | 2010·MRM | K-space consistency-constrained reconstruction. |
| P1-07 | 🧬 Pruessmann K.P. *Encoding and reconstruction in parallel MRI* | 2004·NMR Biomed | Encoding-theory review; build the math framework. |
| P1-08 | 🔧 Griswold M.A. et al. *Parallel MRI using the GRAPPA operator…* | 2005·MRM | The operator form of GRAPPA; understand reconstruction operators. |
| P1-09 | 🔧 Blaimer M. et al. *SMASH, SENSE, PILS, GRAPPA—how to choose…* | 2004·Top MRI | PI review; cross-compare methods. |
| P1-10 | ⭐🔧 Block K.T., Uecker M., Frahm J. *Undersampled radial MRI with real-time reconstruction* | 2007·MRM | Undersampling + real-time reconstruction; intro to non-Cartesian. |
| P1-11 | 🔧 King K.F. *Parallel magnetic resonance imaging (review)* | 2004·Top MRI | PI engineering-implementation review. |
| P1-12 | 🧬 Liang D. et al. *Accelerating SENSE (CS + PI review)* | — | Combining CS and parallel imaging. |
| P1-13 | 🔧 Uecker M. et al. *Berkeley Advanced Reconstruction Toolbox (BART)* | 2015·ISMRM | Open-source reconstruction toolbox; hands-on. |
| P1-14 | 🧬 Fessler J.A. *Model-based image reconstruction for MRI* | 2010·IEEE TCI | Frame reconstruction as an inverse problem. |
| P1-15 | 🔧 Ramani A., Fessler J.A. *Parallel MR image reconstruction (split Bregman / CG-SENSE)* | 2011·IEEE TMI | Numerical implementation of iterative reconstruction. |

**Phase output**: be able to write a minimal SENSE/GRAPPA implementation and understand the universal "undersampling → inverse problem → regularization" paradigm.

---

## P2 · Non-Cartesian Sampling (18 · Emphasis)

**Goal**: fully digest Radial / Spiral / Rosette trajectories, plus NUFFT, gridding, density compensation — the lifeblood of your direction.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P2-01 | ⭐ Ahn C.B., Kim J.H., Cho Z.H. *High-speed spiral-scan echo planar NMR imaging* | 1986·IEEE TMI | The pioneering work of spiral sampling. |
| P2-02 | ⭐ Meyer C.H. et al. *Fast spiral coronary artery imaging* | 1992·MRM | The classic that made spiral practical. |
| P2-03 | ⭐ Glover G.H., Pauly J.M. *Gradient moment reduction (spiral)* | 1992·MRM | Spiral and motion compensation. |
| P2-04 | ⭐🔧 Fessler J.A., Sutton B.P. *Nonuniform fast Fourier transforms using min-max interpolation* | 2003·IEEE TSP | The gold-standard **NUFFT** algorithm; must read closely. |
| P2-05 | ⭐🔧 Beatty P.J., Nishimura D.G., Pauly J.M. *Rapid gridding reconstruction with a minimal oversampling ratio* | 2005·IEEE TMI | Derivation of the **density compensation function (DCF)**; core of non-Cartesian recon. |
| P2-06 | 🔧 Pipe J.G. *Motion correction with PROPELLER MRI* | 1999·MRM | Rotating blade (radial bands); motion-correction idea. |
| P2-07 | 🔧 Scheffler K. *A pictorial description of steady-states (radial)* | 1999·MRM | Radial steady-state imaging. |
| P2-08 | 🔧 Winkelmann S. et al. *Optimal radial sampling (golden-angle)* | 2007·IEEE TMI | **Golden-angle** radial sampling; cornerstone of dynamic imaging. |
| P2-09 | 🔧 Block K.T., Uecker M., Frahm J. *Suppression of MRI artifacts (robust radial)* | 2007·MRM | Radial robustness to motion. |
| P2-10 | 🧬 Jackson J.I., Meyer C.H., Nishimura D.G., Macovski A. *Selection of a convolution function…* | 1991·IEEE TMI | Choosing the gridding kernel; theoretical foundation. |
| P2-11 | 🧬 O'Sullivan J. *A fast sinc function gridding algorithm…* | 1985·IEEE ASSP | Early gridding theory. |
| P2-12 | 🔧 Pipe J.G., Menon P. *Sampling density compensation…* | 1999·MRM | Comparing multiple DCF estimation methods. |
| P2-13 | 🎯 Irarrazabal P., Nishimura D.G. *Fast three dimensional magnetic resonance imaging* | 1995·MRM | 3D non-Cartesian (stack-of-spiral). |
| P2-14 | 🔧 Dale B.M. et al. *Rapid and accurate (gridding review)* | 2001·Magn Reson Imaging | Gridding implementation review. |
| P2-15 | 🧬 Gurney P.T., Hargreaves B.A., Nishimura D.G. *Design and analysis of a practical 3D cones trajectory* | 2006·MRM | 3D cones trajectory design — design methodology. |
| P2-16 | 🔧 Vasanawala S.S. et al. *Improved spiral imaging (clinical)* | 2000·MRM | Spiral in clinical practice. |
| P2-17 | 🧬 Klaiborger W., Gmitro A. *Rosette trajectories* | — | Rosette sampling; multi-axis interleaved trajectories. |
| P2-18 | 🔧 Wundrak S. et al. *Golden ratio sparse MRI (radial pulse)* | 2015·Tomography | Golden-ratio timing optimization. |

**Phase output**: be able to design a spiral/radial trajectory by hand, do a minimal reconstruction with NUFFT, and explain why DCF is needed.

---

## P3 · Quantitative Imaging Basics (12)

**Goal**: understand how quantitative parameters like T1/T2/T2* are measured — the physical quantities the MRF "fingerprint" maps to.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P3-01 | ⭐ Look D.C., Locker H.R. *Time saving in measurement of NMR and EPR relaxation times* | 1970·Rev Sci Instrum | The **Look-Locker** method; the ancestor of fast T1 measurement. |
| P3-02 | ⭐ Deoni S.C.L., Rutt B.K., Peters T.M. *Rapid combined T1 and T2 mapping (DESPOT)* | 2003·MRM | **DESPOT1/2**; steady-state quantification classic. |
| P3-03 | 🧬 Christensen G.E. et al. *T1 estimation (IR-SE)* | — | The gold standard of inversion-recovery T1. |
| P3-04 | 🔧 Wang J. et al. *T1 FLAIR quantification* | — | Clinical T1 quantification. |
| P3-05 | 🧬 Brix G. et al. *T2 determination (multi-echo SE)* | 1990·JCAT | Multi-echo T2 fitting. |
| P3-06 | 🔧 Cheng H.L.M., Wright G.A. *Rapid high-resolution T1 mapping (variable flip)* | 2006·MRM | Variable flip-angle T1. |
| P3-07 | 🔧 Deoni S.C.L. *Quantitative relaxometry of the brain (review)* | 2010·Top MRI | Quantitative-relaxation review. |
| P3-08 | 🧬 Schwenzer N.F. et al. *T1/T2 mapping review* | 2010·Invest Radiol | Clinical mapping review. |
| P3-09 | 🧬 Maier O. et al. *RAPID T1 mapping* | — | Fast T1 reconstruction. |
| P3-10 | 🔧 Wood T.C. *Highly accelerated T2 mapping* | — | Fast T2. |
| P3-11 | 🧬 Deichmann R. et al. *T1 quantification (MPRAGE optimization)* | — | MPRAGE and T1. |
| P3-12 | 🔧 Henderson E. et al. *Fast T1 mapping (Look-Locker)* | 1999·MRM | Modern Look-Locker implementation. |

**Phase output**: be able to fit a T1/T2 map from a signal model, and understand that pre-MRF quantification methods were "slow and single-parameter".

---

## P4 · MRF Principles (15)

**Goal**: fully digest the entire MRF paradigm — pseudo-random acquisition → dictionary → pattern matching.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P4-01 | ⭐🎯 Ma D. et al. *Magnetic resonance fingerprinting* | 2013·Nature | **The MRF foundation**; the must-read of must-reads. |
| P4-02 | ⭐🎯 Jiang Y. et al. *MR fingerprinting using fast imaging with steady-state precession (FISP)* | 2015·MRM | **FISP-MRF**; the most-used MRF sequence. |
| P4-03 | ⭐🔧 McGivney D.F. et al. *SVD compression…* | 2014·MRM | Dictionary SVD compression; accelerates matching. |
| P4-04 | 🔧 Cruz G. et al. *SVD-based dictionary compression (extension)* | — | Further optimization of compressed dictionaries. |
| P4-05 | 🧬 Assländer J. et al. *Magnetic resonance fingerprinting theory* | — | The theoretical framework of MRF; steady-state analysis. |
| P4-06 | 🔧 Zhao B. et al. *MRF optimization / CRLB sampling design* | — | Optimize MRF acquisition from estimation theory. |
| P4-07 | 🔧 Hamilton J.I. et al. *MR fingerprinting review* | 2015·Top MRI | MRF review; build the big picture. |
| P4-08 | 🔧 Badve C. et al. *MRF T1/T2 clinical (brain/liver)* | — | Clinical feasibility of MRF. |
| P4-09 | 🧬 Hacking C.A. et al. *B1+ correction in MRF* | — | B1 inhomogeneity correction for MRF. |
| P4-10 | 🔧 Breuer F.A. et al. *MRF artifacts / blunting* | — | MRF banding artifacts. |
| P4-11 | 🔧 Körzdörfer G. et al. *MRF dictionary + noise model* | — | Incorporating noise into matching. |
| P4-12 | 🔧 Deshmane A. et al. *MRF review (advanced)* | — | Engineering-oriented MRF review. |
| P4-13 | 🧬 Jiang Y., Ma D. et al. *MRF reconstruction / TI-LOC* | — | MRF reconstruction strategies. |
| P4-14 | 🔧 Wang C.Y. et al. *MRF B1/T1/T2 joint* | — | Multi-parametric joint MRF. |
| P4-15 | 🎯 Ma D. et al. *MRF sequence design (flip-train)* | — | Flip-angle train design. |

**Phase output**: be able to retell the full story of Ma 2013 and explain "why pseudo-random + dictionary matching can quantify many parameters at once".

---

## P5 · Non-Cartesian MRF (18 · Core)

**Goal**: this is your main battlefield. Combine non-Cartesian sampling with MRF; study reconstruction, acceleration, and deep learning.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P5-01 | ⭐🎯 Zhao B. et al. *Spiral magnetic resonance fingerprinting (S-MRF)* | 2014·ISMRM / journal | **Spiral MRF**; the core starting point of your direction. |
| P5-02 | ⭐🎯 Cloos M.A. et al. *Multiparametric imaging with spiral MRF* | 2016·Nat Commun | High-quality spiral MRF implementation; must read closely. |
| P5-03 | 🎯 Jiang Y. et al. *GRASE-MRF / 3D MRF* | — | 3D non-Cartesian MRF. |
| P5-04 | 🎯 Ma D. et al. *MRF + radial (free-breathing)* | — | Motion robustness of radial MRF. |
| P5-05 | 🎯 Assländer J. et al. *Radial MRF theory* | — | Radial MRF steady-state theory. |
| P5-06 | 🎯 Buonincontri G. et al. *Radial MRF (3D)* | — | 3D radial MRF. |
| P5-07 | 🎯 Borisch E.A. et al. *3D spiral MRF* | — | 3D spiral MRF. |
| P5-08 | 🎯 Rieger B. et al. *Spiral MRF dictionary / reconstruction* | — | Spiral MRF reconstruction details. |
| P5-09 | 🎯 Christen T. et al. *Non-Cartesian MRF clinical* | — | Clinical validation. |
| P5-10 | ⭐🎯 Cohen O. et al. *Deep learning MRF reconstruction* | 2018·MRM | DL to accelerate MRF reconstruction. |
| P5-11 | 🎯 Hoppe P. et al. *DL-MRF / dictionary replacement* | — | Replacing dictionary matching with a network. |
| P5-12 | 🎯 Fang Z. et al. *Deep MRF matching* | — | Deep matching networks. |
| P5-13 | 🎯 Cao X. et al. *DL non-Cartesian MRF* | — | DL + non-Cartesian MRF. |
| P5-14 | 🎯 Zhang H. et al. *MRF subspace constraint* | — | Subspace / low-rank MRF reconstruction. |
| P5-15 | 🎯 Blümler P. et al. *Non-Cartesian MRF review* | — | Direction review. |
| P5-16 | 🎯 Sommer K. et al. *MRF trajectory optimization / CRLB* | — | Optimal design of non-Cartesian trajectories. |
| P5-17 | 🎯 Ma D. et al. *MRF quantification precision (non-Cartesian)* | — | Precision analysis under non-Cartesian sampling. |
| P5-18 | 🎯 Hamilton J.I. et al. *Real-time non-Cartesian MRF* | — | Real-time reconstruction. |

**Phase output**: define your own research entry point — find the innovation within the 3D space of "sampling trajectory × sequence × reconstruction/matching".

---

## P6 · Pulse-Sequence Design (15 · Emphasis)

**Goal**: you said "the most important thing is to learn the sequences". This phase fully digests the internals of every sequence you will use.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P6-01 | ⭐ Haase A., Frahm J., Matthaei D. *FLASH imaging. Rapid NMR imaging using low flip-angle pulses* | 1986·J Magn Reson | **FLASH**; spoiled gradient echo; fundamental. |
| P6-02 | ⭐ Oppelt A., Graumann R., Barfuß H. *FISP—a new fast MRI sequence* | 1986·Electromedica | Origin of the **FISP / bSSFP** family. |
| P6-03 | ⭐ Carr H.Y. *Steady-state free precession in nuclear magnetic resonance* | 1958·Phys Rev | The theoretical starting point of **SSFP**. |
| P6-04 | 🧬 Kaiser R., Bartholdi E., Ernst R.R. *Diffusion and field (SSFP theory)* | 1974·J Chem Phys | Complete steady-state analysis of SSFP. |
| P6-05 | 🧬 Gyngell M.L. *The steady-state signals (SSFP signal)* | 1988·J Magn Reson | SSFP signal derivation. |
| P6-06 | 🔧 Scheffler K. et al. *bSSFP review / transient* | 2003·Concepts Magn Reson | bSSFP review; understand banding artifacts. |
| P6-07 | 🔧 Leupold J. et al. *Fast gradient echo / transition* | 2009·MRM | GRE transient behavior. |
| P6-08 | 🔧 Bangerter N.D. et al. *Quantitative analysis of bSSFP (multi-parametric)* | — | bSSFP and multi-parameters (connects to MRF). |
| P6-09 | ⭐🔧 Layton K.J. et al. *Pulseq: A rapid and open-source framework for pulse sequences* | 2017·MRM | **Pulseq**; cross-platform sequence description; hands-on essential. |
| P6-10 | 🔧 Hargreaves B.A. et al. *Versatile (gradient waveform design)* | — | Gradient waveform / eddy design. |
| P6-11 | 🔧 Vannesjo S.J. et al. *Gradient system characterization* | 2013·MRM | Gradient system modeling (K-space accuracy). |
| P6-12 | 🔧 Pauly J.M. et al. *k-space analysis (pulse design)* | — | K-space RF pulse design. |
| P6-13 | 🧬 Hennig J. *Multiecho imaging (RARE/TSE)* | — | Spin-echo sequence family. |
| P6-14 | 🔧 Bernstein M.A. *Handbook chapters (GRE/SSFP)* | 2004·Book | Systematic review of sequence families. |
| P6-15 | 🔧 Crozier S., Bilecen D. *Sequence engineering review* | — | Modern sequence-engineering review. |

**Phase output**: be able to draw the sequence diagrams (RF, gradients, echoes) of FLASH/FISP/bSSFP and implement a simple sequence with Pulseq.

---

## P7 · Advanced Reconstruction & Frontier (15)

**Goal**: bring modern deep-learning reconstruction and frontier methods into your toolbox, to power your own methodological innovation.

| # | Paper | Year·venue | Why read |
|---|-------|-----------|----------|
| P7-01 | ⭐🔧 Hammernik K. et al. *Learning a variational network for representation of accelerating MRI* | 2018·MRM | **VarNet**; model-driven DL reconstruction. |
| P7-02 | ⭐🔧 Schlemper J. et al. *A deep cascade of convolutional neural networks for dynamic MR image reconstruction* | 2018·IEEE TMI | Cascaded-CNN reconstruction. |
| P7-03 | ⭐🔧 Aggarwal H.K., Mani M.P., Jacob M. *MoDL: Model-Based Deep Learning Architecture for Inverse Problems* | 2019·IEEE TMI | **MoDL**; DL + physics model. |
| P7-04 | 🧬 Zhu B. et al. *Image reconstruction by domain-transform manifold learning* | 2018·MRM | End-to-end reconstruction. |
| P7-05 | 🔧 Akçakaya M. et al. *Scan-specific robust (unsupervised DL)* | — | Unsupervised / scan-specific reconstruction. |
| P7-06 | 🔧 Muckley M.J. et al. *DL raw reconstruction / losses* | — | DL reconstruction loss design. |
| P7-07 | 🧬 Hammernik K. et al. *DL reconstruction review* | — | DL-MRI reconstruction review. |
| P7-08 | 🔧 Lonning K. et al. *Recurrent inference* | — | Recurrent-network reconstruction. |
| P7-09 | 🔧 Ramzi Z. et al. *NC-PDAM / parallel DL reconstruction* | — | Fast DL reconstruction training. |
| P7-10 | 🧬 Mardani M. et al. *Deep generative (GAN recon)* | — | Generative-model reconstruction. |
| P7-11 | 🔧 Cheng J.Y. et al. *DL non-Cartesian reconstruction* | — | DL + non-Cartesian (directly relevant). |
| P7-12 | 🎯 Cohen O. / Fang Z. *DL-MRF advanced* | — | DL-MRF frontier. |
| P7-13 | 🧬 Zhang T. et al. *Low-rank / subspace reconstruction* | — | Subspace / low-rank constraints. |
| P7-14 | 🔧 Uecker M. / BART *Real-time reconstruction* | — | Real-time non-Cartesian reconstruction. |
| P7-15 | 🧬 Odille F. et al. *Motion-corrected reconstruction* | — | Motion / free-breathing reconstruction. |

**Phase output**: be able to reproduce a DL-reconstruction baseline (e.g. MoDL/VarNet) and think about how to graft DL onto non-Cartesian MRF.

---

## Pacing advice

- 3 papers a day; **write a note for every one** (even if only 5 lines).
- Spend half a day each weekend **re-reading the week's most important paper** and updating its note.
- About 120 papers in total; at 3/day that's roughly 6–7 weeks for one pass — go slower; quality over quantity.
- After finishing a paper, set its `status` to `done` in `index.json`; the website progress bar updates automatically.

## Where to find papers

- Core journals: Magnetic Resonance in Medicine (MRM), IEEE TMI, NMR in Biomedicine, Journal of Magnetic Resonance, Nature Communications.
- Preprints: arXiv (eess.IV / physics.med-ph).
- Open-source code: BART, Pulseq, SigPy, MRF dictionary tools.

# Portfolio Context — Dmytro Hilei

Source of truth for site content. Mirrors `CV.pdf` — when the CV changes, update this, then the site.

## Who I am
High-performance computing and machine learning engineer and student. Interested in computer
vision, generative language models, and C++/CUDA physical simulations and stencil parallel
computing. Built projects with PyTorch, TensorFlow, OpenMP and CUDA; currently exploring Devito,
CuPy, MSL, AMD HIP and tinygrad.

Originally from Lviv, Ukraine; currently in Tallinn, Estonia.

## Education
- **TalTech** — BSc Integrated Engineering, 2025–2028. GPA 4.8/5.0 (1st & 2nd semesters)
- **Lviv Physics and Mathematics Lyceum** — graduated 2025, specialization in mathematics and
  physics. Average grade 10.8/12

## Projects (in CV order of importance)

### Open-source CUDA optimization — OpenCV `cudastereo` (StereoSGM)
Mentored by an R&D engineer at SoftServe (mentor's affiliation, not an employer).
- Fixed a consistency-check launch-bounds bug that skipped up to a 15-pixel strip on
  non-multiple-of-16 images; merged upstream with the matching regression-baseline update
  (opencv_contrib #4165, opencv_extra #1392)
- Implementing TMA/mbarrier-based path-aggregation kernels for Blackwell (sm_100+), bit-exact with
  the legacy kernel; cuts horizontal-aggregation latency ~11% (RTX 5060 Laptop) to ~48% (RTX 5090)
- Reduces end-to-end pipeline latency up to 5.1% on a rented RTX 5090; open for review
  (opencv_contrib #4169)
- https://github.com/opencv/opencv_contrib/pull/4165
- https://github.com/opencv/opencv_contrib/pull/4169

### Symbolic music generation with a 462M-parameter Transformer (PyTorch)
- Decoder-only autoregressive Transformer (28 layers, d=1152) trained from scratch on multi-instrument
  MIDI (GigaMIDI, Aria-MIDI, Discover); 8.3B notes seen on a single rented RTX 5090. Grew out of a
  10–20M piano model on MAESTRO and an earlier LSTM baseline
- One token per note (pitch, velocity, duration, delta-time on a 20 ms grid), predicted by cascaded
  heads (delta -> pitch -> duration -> velocity): loss 9.412 vs 9.824 independent (6M model, 1 seed)
- RMSNorm + SwiGLU + QK-norm + RoPE block vs nanoGPT block: val CE 3.137 +- 0.013 vs 3.886 +- 0.075
  (42M, 3 seeds); Muon, fp8 + torch.compile; instrument/density conditioning is free on loss
  (1.714 vs 1.716); auxiliary future heads did not help
- Final held-out CE on clean GigaMIDI: 1.679 per note (pitch 0.367, velocity 0.497, duration 0.644,
  delta 0.170), vs 2.242 for the earlier 108M pilot
- Now fine-tuning towards Ukrainian pop-rock piano arrangements (Demucs + basic-pitch reduction)
- https://github.com/DmytroHilei/Music_generative_model

### Physics-based simulation of wave propagation and heat transfer (C++ / OpenMP / CUDA)
- Numerical PDE solvers using the finite difference method
- OpenMP-parallelized grid computations (AMD Ryzen 9 AI HX 370)
- ~20× over the CPU-only baseline via Bentley's-rules optimizations and memory-usage efficiency,
  then a further ~11× porting kernels to CUDA (RTX 5060 Laptop GPU)
- Correctness verified against analytical solutions of the PDE
- https://github.com/DmytroHilei/2D_heat_diffusion_and_wave_propagation

### Automated GitHub issue-discovery daemon — `issuewatch` (C11)
- Single-threaded C11 daemon polling GitHub issues across watched repos via libcurl/HTTP2,
  prefiltered with a hand-written Aho–Corasick keyword automaton
- Batches surviving issues to an LLM (local Ollama or the Anthropic API) for relevance judging,
  publishes a ranked self-updating board to a secret Gist with push notifications
- Near-zero cost via ETag caching, incremental watermarking and batched LLM calls
- https://github.com/DmytroHilei/Search_engine_to_find_opensource_issues

### Not on the site
Older repos, kept public but cut from both the CV and the site to keep the signal tight:
- License plate OCR (YOLO + CRNN/CTC) — https://github.com/DmytroHilei/YOLO_training_on_plates_and_customeOCR
- Speech recognition on Raspberry Pi 5 — https://github.com/DmytroHilei/Speech_Recognition_on_rasberry_pi_5
- SmartBinaryClock (embedded C++) — https://github.com/DmytroHilei/SmartBinaryClock

## Achievements

### Olympiads (each links to official results)
- Silver Medal — IOAA 2025 — https://ioaa2025.in/wp-content/uploads/2025/12/IOAA2025-Final-Result.pdf
- Bronze Medal — IOAA 2024 — https://ioaa2024.on.br/assets/pdf/Final_Scores/IOAA%202024%20Final%20scores.pdf
- Silver Medal — IOAA Junior 2023 — https://www.uoi.ua/en/data/contests/ioaajr/2023/results
- First-stage diplomas — All-Ukrainian Olympiads on Astronomy and Astrophysics
  - 2024 — https://www.uoi.ua/en/data/contests/uao/2024/results/11 ·
    KNU https://space.univ.kiev.ua/wp-content/uploads/2024/04/result2024.pdf
  - 2025 — https://www.uoi.ua/en/data/contests/uao/2025/results/11 ·
    KNU https://space.univ.kiev.ua/wp-content/uploads/2025/04/result2025.pdf

Three consecutive years of IOAA medals — sustained depth, not a one-off.

### Other activities
- Member of the Ukrainian scout organization Plast for 8 years; youth leadership and
  educational/physical activities
- Jury member for the Ukrainian National Olympiad in Astronomy and Astrophysics
- Enjoy playing the guitar

## Skills
- **Programming:** Python, C/C++, LLVM IR, PyTorch, TensorFlow, NumPy, CUDA
- **Machine learning:** deep learning, computer vision, sequence models (RNN, LSTM), transformers,
  detection models
- **Computer vision:** YOLO object detection, OpenCV, FasterRCNN, CNN feature extraction, ViT
- **Tools:** Git, LaTeX, Linux (CLI), Raspberry Pi 5
- **Mathematics & physics:** calculus, probability & statistics, astrophysics, finite difference
  methods for PDEs, numerical simulation, stencil computations
- **Languages:** Ukrainian (native), Polish (B1), English (B2+, IELTS 6.5)

## Contact / links
- Email: dmytrohilei@gmail.com
- GitHub: https://github.com/DmytroHilei
- LinkedIn: https://www.linkedin.com/in/dmytro-hilei-1092b3287/
- Deployed at: https://dmytro-dev-nine.vercel.app

Phone is on the CV only — deliberately not on the public site.

Header photo: `public/profile.jpg`, a 120px circular avatar on the left of the header. Generated
from `Profile_picture.jpg` (the full-resolution iPhone original, kept at the repo root) with the
largest square the source allows — full 3024px height, centred on the face, so the shoulders stay
in frame:

```sh
convert Profile_picture.jpg -crop 3024x3024+938+0 +repage -resize 480x480 \
  -unsharp 0x0.75+0.75+0.008 -strip -quality 82 -interlace Plane public/profile.jpg
```

480px served for a 120px slot covers 4x displays; the unsharp pass restores the detail lost in a
6:1 downsample.

`-strip` matters — the original carries EXIF GPS coordinates.

## Design direction
The site reads as a document, close to `CV.pdf`: section headings with a hairline rule,
right-aligned dates and stacks, tight bullet lists. Single column, text-first.
- Astro, static output
- Near-white theme, typography does the work
- No card grids, no badge pills, no hero, no animations
- Every factual claim that can be sourced links to its source

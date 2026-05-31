# Portfolio Context — Dmytro Hilei

## Who I am
I am an integrated engineering student at Tallinn University of Technology (TalTech), originally from Lviv, Ukraine, currently living in Tallinn, Estonia. I work at the intersection of machine learning and high-performance computing — building and optimizing systems at the level where algorithms meet hardware.

My focus is on ML engineering with a systems/HPC angle: not just training models, but understanding and optimizing what happens underneath — CUDA kernels, memory hierarchies, parallelism.

## Education
- **TalTech** — Integrated Engineering BSc, 2025–2028. GPA: 4.8/5 (semester 1), ~4.7/5 (semester 2, ongoing)
- **Lviv Physics and Mathematics Lyceum** — Graduated 2025. Unweighted GPA: 10.8/12
- **Lviv Polytechnic National University** — parallel enrollment planned, 2026–2030

## Awards
- Silver Medal — IOAA (International Olympiad on Astronomy and Astrophysics), 2025
- Bronze Medal — IOAA, 2024
- Silver Medal — IOAA Junior (under-16 category), 2023
- First-stage diplomas — All-Ukrainian Olympiads in Astronomy and in Astronomy & Astrophysics, 2024 and 2025

Three consecutive years of IOAA medals shows sustained depth, not a one-off result.

## Languages
- Ukrainian — native
- English — fluent (IELTS 6.5), lived in english enviroments for 1 year already
- Estonian — A1.1, actively studying

## Technical skills
- **Languages:** C++, CUDA, C, Python (NumPy, PyTorch, Matplotlib, openCV)
- **ML:** transformer architectures (decoder-only GPT, DETR), RNNs, LSTMs, CNNs, ResNet, object detection, OCR pipelines
- **HPC:** OpenMP, optimisation of classical CV algorithms, TMA, basic cutlas
- **Tools:**  Git, LaTex

## Projects

### YOLO + CRNN/CTC License Plate OCR
End-to-end pipeline: YOLO for plate detection, custom CRNN with CTC loss for text recognition. Trained on a custom-collected dataset of Estonian license plate crops. Shows full pipeline ownership from data to inference.
- GitHub: https://github.com/DmytroHilei/YOLO_training_on_plates_and_customeOCR

### 2D Heat Diffusion & Wave Propagation Simulation
Physics-based PDE simulation parallelized with OpenMP using Bentley optimization rules. Python for visualization. Starting point for further CUDA acceleration work.
- GitHub: https://github.com/DmytroHilei/2D_heat_diffusion_and_wave_propagation

### OpenCV StereoSGM CUDA Optimization (in progress)
Optimizing OpenCV's Semi-Global Matching stereo vision pipeline for NVIDIA Blackwell architecture (sm_120, RTX 5060). Pipeline stages: Census Transform → Path Aggregation → WTA → Median Filter → LR Check. Techniques: `__ldg` cache hints, warp shuffles, vectorized loads, TMA async prefetch. PR to opencv/opencv pending.
- GitHub: https://github.com/DmytroHilei/opencv

### GPT Music Transformer (in progress)
Rewriting an LSTM music generation model into a decoder-only Transformer trained on the Maestro dataset using REMI tokenization. ~20M parameters (6 layers, 8 heads, 512 embedding dim, 1024 context). Training on rented H100 via vast.ai.

### SmartBinaryClock
Embedded C++ project: displays time in binary and military formats alongside temperature, humidity, and voltage readings.
- GitHub: https://github.com/DmytroHilei/SmartBinaryClock

## Volunteering
- Jury member and lecturer at Ukrainian Astronomy Olympiads (while still competing myself)
- Plast member for 7 years (Ukrainian national scouting organization)

## Links
- GitHub: https://github.com/DmytroHilei
- LinkedIn: https://www.linkedin.com/in/dmytro-hilei-1092b3287/

## Design direction (for Claude Code)
Aesthetic target: karpathy.ai — minimal, text-first, no hero animations, feels like a page a serious engineer built for themselves. Not a template.
- Astro framework, static output
- Dark or near-white theme, not gray-gradient
- No card grids, no badge pills, no "My Projects" section headers
- Projects listed as clean lines with brief descriptions and links
- Typography does the work, not decoration

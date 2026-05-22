# CORAL-2 Benchmark Results

Benchmarks from the [LLNL CORAL-2 procurement suite](https://asc.llnl.gov/coral-2-benchmarks), compiled from source and run 10 times each.

## Platform

| Parameter | Value |
|-----------|-------|
| Platform | Google Colab (cloud) |
| OS | Ubuntu 22.04 LTS |
| CPU | Intel Xeon, 1 vCPU |
| RAM | ~12 GB |
| GPU | None (CPU-only) |
| MPI | OpenMPI 4.1.2 |
| MPI Ranks | 1 |
| Compilers | GCC 11.2, mpicxx, mpicc |
| Date | May 21, 2026 |
| Runs per benchmark | 10 |

---

## Application Configurations

| # | Benchmark | Key Config |
|---|-----------|------------|
| 1 | STREAM | Default array sizes, measures Copy / Scale / Add / Triad bandwidth |
| 2 | AMG | Default problem size, 1 MPI rank |
| 3 | Kripke | Default spatial & angular decomposition, 1 MPI rank |
| 4 | PENNANT | Sedov test problem, small mesh |
| 5 | Nekbone | Small 3D mesh, 1 MPI rank |
| 6 | HACC | 64³ grid, 20 steps, σ₈=0.80, box=64 h⁻¹Mpc (reduced from 1024³ due to RAM) |
| 7 | LAMMPS | LJ liquid, FCC lattice ρ=0.8442, 10³ box, 1000 steps, NVE |
| 8 | Quicksilver | 10k particles, 10 cycles, 10×10×10 mesh |
| 9 | QMCPACK | Small test problem, QMC_MPI=1, QMC_OMP=0 |
| 10 | IOR | Transfer 1 MB, block 16 MB, 16 segments |

---

## Results Summary

| # | Benchmark | Metric | Avg | Min | Max |
|---|-----------|--------|-----|-----|-----|
| 1 | STREAM | Copy (MB/s) | 11,359 | -- | -- |
| | | Scale (MB/s) | 11,365 | -- | -- |
| | | Add (MB/s) | 13,569 | -- | -- |
| | | Triad (MB/s) | 13,675 | -- | -- |
| 2 | AMG | FOM (nnz·iter/s) | 4.418e+05 | -- | -- |
| 3 | Kripke | Throughput (unkn/s/iter) | 1.881e+07 | -- | -- |
| 4 | PENNANT | Hydro cycle time (s) | 0.01038 | 0.01035 | 0.01041 |
| 5 | Nekbone | Exec time (s) | 0.4320 | 0.4230 | 0.4410 |
| | | MFLOPS | 2457.65 | -- | -- |
| 6 | HACC | Total run time (s) | 0.4236 | 0.3935 | 0.5580 |
| 7 | LAMMPS | Wall time (s) | 2.1000 | 2.0000 | 3.0000 |
| 8 | Quicksilver | Run time (s) | 2.2327 | 2.0130 | 3.0860 |
| 9 | QMCPACK | Run time (s) | 0.0486 | 0.0433 | 0.0663 |
| 10 | IOR | Write (MiB/s) | 0.0248 | -- | -- |
| | | Read (MiB/s) | 0.0010 | -- | -- |

---

## Per-Run Details

### HACC
| Run | Time (s) |
|-----|----------|
| 1 | 0.393496 |
| 2 | 0.412831 |
| 3 | 0.401887 |
| 4 | 0.396793 |
| 5 | 0.405745 |
| 6 | 0.399611 |
| 7 | 0.426208 |
| 8 | 0.558041 |
| 9 | 0.425180 |
| 10 | 0.415998 |
| **Avg** | **0.4236** |

### LAMMPS
| Run | Time (s) |
|-----|----------|
| 1 | 2 | 2 | 2 | 3 | 2 | 2 | 2 | 2 | 2 | 2 | 2 |
| **Avg** | **2.1** |

### Quicksilver
| Run | Time (s) |
|-----|----------|
| 1 | 2.9920 |
| 2 | 2.0570 |
| 3 | 2.0190 |
| 4 | 2.0130 |
| 5 | 2.0240 |
| 6 | 3.0860 |
| 7 | 2.0250 |
| 8 | 2.0300 |
| 9 | 2.0460 |
| 10 | 2.0350 |
| **Avg** | **2.2327** |

### QMCPACK
| Run | Time (s) |
|-----|----------|
| 1 | 0.0433 |
| 2 | 0.0468 |
| 3 | 0.0521 |
| 4 | 0.0486 |
| 5 | 0.0499 |
| 6 | 0.0512 |
| 7 | 0.0477 |
| 8 | 0.0503 |
| 9 | 0.0663 |
| 10 | 0.0486 |
| **Avg** | **0.0486** |

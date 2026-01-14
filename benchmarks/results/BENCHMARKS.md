# Performance Benchmarks

Automated benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-14 03:18 UTC  
**Commit:** `unknown`  
**Docker Image:** `primeintellect/prime-rl-jackmin@sha256:2100834906f848dd412c6eea279cb3f0a4da5be1810a43abdba698aee6af96cd`

> :warning: indicates regression > 5% from baseline
> diffs shown when abs(change) >= 1.0% (except regressions, which always show diffs)

> :clock10: The Step Time shown is the time taken per micro batch. This differs from what gets displayed in the bench table which is the total step time.
## INTELLECT-3

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL LoRA(r=16) | 16384 | Recompute | FA3 | 8xH200 | 19.8% | 16.67k | 7.86s | 89.7 GiB |
| RL LoRA(r=16) | 16384 | Offload | FA3 | 8xH200 | 19.3% | 16.29k | 8.04s | 84.2 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH200 | 15.8% | 13.32k | 9.84s | 90.2 GiB |
| RL LoRA(r=16) | 16384 | Offload | FA2 | 8xH200 | 15.5% | 13.06k | 10.04s | 84.6 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xB200 | 2.5% | 4.88k | 26.84s | 90.4 GiB |
| RL LoRA(r=16) | 65536 | Offload | FA2 | 8xH200 | 16.1% | 6.28k | 83.50s | 130.3 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xB200 | 5.8% | 5.17k | 101.37s | 153.5 GiB |
| RL LoRA(r=16) | 65536 | Offload | FA2 | 8xB200 | 5.7% | 5.05k | 103.73s | 131.6 GiB |

## Qwen3-0.6B

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL Full | 8192 | Recompute | FA2 | 1xH100 HBM3 | 5.8% | 9.00k | 0.91s | 11.8 GiB |
| RL Full | 8192 | Recompute | FA2 | 1xA6000 | 7.2% (-4.0%) | 3.53k (-4.0%) | 2.32s | 11.7 GiB |
| RL Full | 16384 | Recompute | FA2 | 1xH100 HBM3 | 9.5% | 10.22k | 1.60s | 12.5 GiB |
| RL Full | 16384 | Recompute | FA2 | 1xA6000 | 10.8% | 3.67k | 4.46s | 12.5 GiB |
| RL Full | 65536 | Recompute | FA3 | 1xH100 HBM3 | 26.5% | 10.03k | 6.54s | 19.6 GiB |
| RL Full | 65536 | Offload | FA3 | 1xH100 HBM3 | 26.0% | 9.85k | 6.65s | 16.1 GiB |
| RL Full | 65536 | Recompute | FA2 | 1xH100 HBM3 | 17.9% | 6.78k | 9.67s | 19.6 GiB |
| RL Full | 65536 | Recompute | FA2 | 1xA6000 | 17.4% | 2.08k | 31.46s | 19.5 GiB |
| RL LoRA(r=16) | 8192 | Recompute | FA2 | 1xH100 HBM3 | 5.5% | 10.40k | 0.79s | 4.1 GiB |
| RL LoRA(r=16) | 8192 | Recompute | FA2 | 1xA6000 | 6.3% (+1.8%) | 3.71k (+1.8%) | 2.21s | 4.1 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 1xH100 HBM3 | 9.0% | 11.04k | 1.48s | 5.1 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 1xA6000 | 9.4% | 3.64k | 4.50s | 5.1 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA3 | 1xH100 HBM3 | 25.1% | 9.93k | 6.60s | 11.5 GiB |
| RL LoRA(r=16) | 65536 | Offload | FA3 | 1xH100 HBM3 | 24.4% | 9.66k | 6.78s | 7.9 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 1xH100 HBM3 | 17.0% | 6.73k | 9.74s | 11.5 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 1xA6000 | 16.0% | 2.00k | 32.84s | 11.5 GiB |
| SFT Full | 8192 | Recompute | FA2 | 1xH100 HBM3 | 13.3% (-1.8%) | 20.57k (-1.8%) | 0.40s | 31.7 GiB |
| SFT Full | 8192 | Recompute | FA2 | 1xA6000 | 13.5% | 6.58k | 1.25s | 31.2 GiB |
| SFT Full | 16384 | Recompute | FA2 | 1xH100 HBM3 | 17.3% | 18.56k | 0.88s | 52.8 GiB |

## Qwen3-30B-A3B-Instruct-2507

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL Full | 16384 | Recompute | FA2 | 8xB200 | 1.5% (-1.0%) | 7.12k (-1.0%) | 18.41s | 74.5 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH100 HBM3 | 3.3% (+10.6%) | 6.86k (+10.6%) | 19.12s | 74.6 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH200 | 2.8% (+3.9%) | 5.99k (+3.9%) | 21.88s | 74.6 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xB200 | 6.9% | 13.05k | 40.17s | 91.4 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xH200 | 13.4% (+1.3%) | 11.11k (+1.3%) | 47.17s | 91.4 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH200 | 14.1% | 30.46k | 4.30s | 31.8 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH100 HBM3 | 12.8% (+56.7%) | 27.62k (+56.7%) | 4.74s | 31.8 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xB200 | 1.9% (-1.1%) | 9.42k (-1.1%) | 13.92s | 32.0 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH200 | 19.6% | 16.44k | 31.88s | 64.2 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH100 HBM3 | 18.9% (+85.5%) | 15.82k (+85.5%) | 33.15s | 64.2 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xB200 | 7.0% | 13.31k | 39.38s | 64.8 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xB200 | 9.5% (-1.3%) | 45.67k (-1.3%) | 2.87s | 106.4 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xH200 | 18.4% (+5.5%) | 38.64k (+5.5%) | 3.39s | 106.4 GiB |

## Qwen3-4B-Instruct-2507

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL Full | 16384 | Recompute | FA2 | 8xB200 | 6.7% | 28.43k | 4.61s | 17.0 GiB |
| RL Full | 16384 | Recompute | FA3 | 8xH100 HBM3 | 15.1% | 28.31k | 4.63s | 17.1 GiB |
| RL Full | 16384 | Recompute | FA3 | 8xH200 | 13.6% | 25.50k | 5.14s | 17.1 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH100 HBM3 | 13.5% (+37.2%) | 25.32k (+37.2%) | 5.18s | 17.1 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH200 | 12.4% (+1.3%) | 23.17k (+1.3%) | 5.66s | 17.1 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xB200 | 12.9% | 24.07k | 21.79s | 36.0 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xH100 HBM3 | 25.3% (+86.0%) | 20.69k (+86.0%) | 25.35s | 36.1 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xH200 | 25.0% | 20.46k | 25.63s | 36.1 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA3 | 8xH200 | 22.7% | 52.24k | 2.51s | 10.3 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA3 | 8xH100 HBM3 | 21.0% | 48.26k | 2.72s | 10.3 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xB200 | 8.8% | 45.97k | 2.85s | 10.2 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH200 | 18.7% | 42.92k | 3.05s | 10.3 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH100 HBM3 | 17.4% (+55.4%) | 40.08k (+55.4%) | 3.27s | 10.3 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA3 | 1xH100 HBM3 | 21.4% | 6.14k | 2.67s | 23.3 GiB |
| RL LoRA(r=16) | 16384 | Offload | FA3 | 1xH100 HBM3 | 20.5% | 5.88k | 2.79s | 20.6 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 1xH100 HBM3 | 17.8% | 5.11k | 3.21s | 23.3 GiB |
| RL LoRA(r=16) | 16384 | Offload | FA2 | 1xH100 HBM3 | 17.1% | 4.92k | 3.33s | 20.6 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 1xA6000 | 15.0% | 1.36k | 12.05s | 23.3 GiB |
| RL LoRA(r=16) | 32768 | Recompute | FA3 | 1xH100 HBM3 | 29.0% | 5.46k | 6.00s | 29.6 GiB |
| RL LoRA(r=16) | 32768 | Offload | FA3 | 1xH100 HBM3 | 28.0% | 5.27k | 6.22s | 24.0 GiB |
| RL LoRA(r=16) | 32768 | Recompute | FA2 | 1xH100 HBM3 | 21.7% | 4.09k | 8.01s | 29.6 GiB |
| RL LoRA(r=16) | 32768 | Offload | FA2 | 1xH100 HBM3 | 21.1% | 3.97k | 8.26s | 24.0 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA3 | 8xH200 | 37.1% | 33.06k | 15.86s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA3 | 8xH100 HBM3 | 36.0% | 32.13k | 16.32s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xB200 | 12.4% | 25.21k | 20.79s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH200 | 25.0% | 22.26k | 23.55s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH100 HBM3 | 24.4% (+85.6%) | 21.71k (+85.6%) | 24.15s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA3 | 1xH100 HBM3 | 37.3% | 4.15k | 15.78s | 42.0 GiB |
| RL LoRA(r=16) | 65536 | Offload | FA3 | 1xH100 HBM3 | 34.8% | 3.87k | 16.92s | 31.1 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 1xH100 HBM3 | 24.9% | 2.77k | 23.66s | 42.0 GiB |
| RL LoRA(r=16) | 65536 | Offload | FA2 | 1xH100 HBM3 | 24.4% | 2.72k | 24.12s | 31.1 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xB200 | 16.1% (+2.6%) | 68.57k (+2.6%) | 1.91s | 54.6 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xH200 | 28.2% (-3.3%) | 52.88k (-3.3%) | 2.48s | 54.6 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xH100 HBM3 | 26.9% (+54.7%) | 50.32k (+54.7%) | 2.60s | 54.6 GiB |
| SFT Full | 65536 | Recompute | FA2 | 8xB200 | 13.6% (-3.2%) | 25.36k (-3.2%) | 20.67s | 171.5 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-0.6B** (SFT Full) on 1xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 0 has a total capacity of 79.18 GiB of which 1.36 GiB is free. Including non-PyTorch memory, this process has 77.8
- **Qwen/Qwen3-4B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-4B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-30B-A3B-Instruct-2507** (RL Full) on 8xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 2.00 GiB. GPU 0 has a total capacity of 79.21 GiB of which 1.94 GiB is free. Including non-PyTorch memory, this process has 0 byt
- **Qwen/Qwen3-0.6B** (SFT Full) on 1xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 0 has a total capacity of 79.18 GiB of which 34.48 GiB is free. Including non-PyTorch memory, this process has 44.
- **Qwen/Qwen3-4B-Instruct-2507** (RL Full) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-0.6B** (SFT Full) on 1xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 0 has a total capacity of 79.18 GiB of which 34.48 GiB is free. Including non-PyTorch memory, this process has 44.
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-0.6B** (SFT Full) on 1xA6000: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 9.27 GiB. GPU 0 has a total capacity of 47.40 GiB of which 8.77 GiB is free. Including non-PyTorch memory, this process has 38.62
- **Qwen/Qwen3-0.6B** (SFT Full) on 1xA6000: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 0 has a total capacity of 47.40 GiB of which 21.75 GiB is free. Including non-PyTorch memory, this process has 25.
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1

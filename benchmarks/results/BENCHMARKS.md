# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 21:34 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline
> diffs shown when abs(change) >= 1.0% (except regressions, which always show diffs)

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xA6000 | 8192 | Recompute | FA2 | 7.1% (+59.5%) | 6.97k (+59.5%) | 3.53s (-39.4%) | 25.0 GiB |
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | **4.2%** :warning: (-8.0%) | **5.03k** :warning: (-8.0%) | **6.39s** :warning: (+6.0%) | 23.8 GiB |
| SFT Full | 2xA6000 | 8192 | Recompute | FA2 | 10.6% (+75.3%) | 10.32k (+75.3%) | 3.13s (-43.8%) | 25.0 GiB |
| RL Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **5.2%** :warning: (-8.1%) | **16.18k** :warning: (-8.1%) | **1.27s** :warning: (+16.0%) | 25.0 GiB |
| RL LoRA(r=16) | 2xH100 HBM3 | 8192 | Recompute | FA2 | **5.5%** :warning: (-6.4%) | **20.67k** :warning: (-6.4%) | **1.59s** :warning: (+6.9%) | 23.8 GiB |
| SFT Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **10.3%** :warning: (-22.8%) | **31.93k** :warning: (-22.8%) | **1.03s** :warning: (+30.6%) | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 10.0% (+75.7%) | 2.47k (+75.7%) | 13.27s (-42.4%) | 33.8 GiB |
| RL Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **7.4%** :warning: (-12.7%) | **4.42k** :warning: (-12.7%) | **3.40s** :warning: (+38.8%) | 61.4 GiB |
| RL LoRA(r=16) | 2xH100 HBM3 | 8192 | Recompute | FA2 | 11.2% | 8.72k | 3.76s | 33.8 GiB |
| SFT Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **16.3%** :warning: (-36.5%) | **9.74k** :warning: (-36.5%) | **3.33s** :warning: (+57.6%) | 58.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (RL Full) on 2xA6000: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 4.64 GiB. GPU 0 has a total capacity of 47.54 GiB of which 3.28 GiB is free. Process 226403 has 44.23 GiB memory in use. Of the a
- **Qwen/Qwen3-4B** (SFT Full) on 2xA6000: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 4.64 GiB. GPU 0 has a total capacity of 47.54 GiB of which 4.27 GiB is free. Process 223098 has 43.26 GiB memory in use. Of the a

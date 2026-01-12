# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 20:50 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xA6000 | 8192 | Recompute | FA2 | **4.1%** :warning: (-8.0%) | **4.02k** :warning: (-8.0%) | **6.24s** :warning: (+7.2%) | 25.0 GiB |
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 4.7% (+2.1%) | 5.58k (+2.1%) | 5.83s (-3.3%) | 23.8 GiB |
| SFT Full | 2xA6000 | 8192 | Recompute | FA2 | 6.2% (+3.4%) | 6.09k (+3.4%) | 5.30s (-4.9%) | 25.0 GiB |
| RL Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **5.2%** :warning: (-8.4%) | **16.12k** :warning: (-8.4%) | **1.26s** :warning: (+14.7%) | 25.0 GiB |
| RL LoRA(r=16) | 2xH100 HBM3 | 8192 | Recompute | FA2 | **5.5%** :warning: (-7.1%) | **20.52k** :warning: (-7.1%) | **1.60s** :warning: (+7.6%) | 23.8 GiB |
| SFT Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **10.1%** :warning: (-24.1%) | **31.38k** :warning: (-24.1%) | **1.03s** :warning: (+31.3%) | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 6.1% (+6.6%) | 1.50k (+6.6%) | 21.91s (-4.9%) | 33.8 GiB |
| RL Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **7.3%** :warning: (-14.3%) | **4.34k** :warning: (-14.3%) | **3.43s** :warning: (+39.7%) | 61.4 GiB |
| RL LoRA(r=16) | 2xH100 HBM3 | 8192 | Recompute | FA2 | 11.2% | 8.71k | 3.76s | 33.8 GiB |
| SFT Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | **16.3%** :warning: (-36.6%) | **9.74k** :warning: (-36.6%) | **3.33s** :warning: (+57.6%) | 58.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (RL Full) on 2xA6000: Unknown error
- **Qwen/Qwen3-4B** (SFT Full) on 2xA6000: Unknown error

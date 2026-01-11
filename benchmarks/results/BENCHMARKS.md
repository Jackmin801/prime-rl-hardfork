# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-11 00:10 UTC  
**Commit:** `abc12345`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL LoRA(rank=16) | 4xA6000 | 8192 | Recompute | FA2 | 10.4% | 5.15k | 25.50s | 29.6 GiB |
| Full FT | 8xH100 | 8192 | Recompute | FA2 | 42.5% | 11.80k | 9.20s | 32.1 GiB |
| RL LoRA(rank=16) | 8xH100 | 8192 | Recompute | FA2 | 45.2% (+2.7%) | 12.50k (+4.2%) | 8.50s (-3.4%) | 28.5 GiB |
| SFT LoRA(rank=16) | 8xH100 | 8192 | Recompute | FA2 | 48.1% | 13.20k | 7.90s | 26.2 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL LoRA(rank=16) | 4xA6000 | 8192 | Recompute | FA2 | **8.2%** :warning: (-8.9%) | **3.79k** :warning: (-9.8%) | **42.10s** :warning: (+10.8%) | 44.5 GiB |
| RL LoRA(rank=16) | 8xH100 | 8192 | Recompute | FA2 | 38.5% | 9.80k | 12.10s | 42.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (full) on 4xA6000: CUDA out of memory. Tried to allocate 2.5 GiB but only 1.2 GiB available.

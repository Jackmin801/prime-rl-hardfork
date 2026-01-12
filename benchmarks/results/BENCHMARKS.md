# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 05:50 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xA6000 | 8192 | Recompute | FA2 | 4.3% | 4.23k | 6.22s | 25.0 GiB |
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 5.0% | 5.90k | 5.55s | 23.8 GiB |
| SFT Full | 2xA6000 | 8192 | Recompute | FA2 | 5.9% | 5.78k | 5.77s | 25.0 GiB |
| RL Full | 2xHBM3 | 8192 | Recompute | FA2 | 5.7% | 17.74k | 1.10s | 25.0 GiB |
| RL LoRA(r=16) | 2xHBM3 | 8192 | Recompute | FA2 | 5.8% | 21.91k | 1.50s | 23.8 GiB |
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 12.2% | 37.72k | 0.87s | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 6.3% | 1.54k | 21.31s | 33.8 GiB |
| RL Full | 2xHBM3 | 8192 | Recompute | FA2 | 8.5% | 5.05k | 2.47s | 61.4 GiB |
| RL LoRA(r=16) | 2xHBM3 | 8192 | Recompute | FA2 | 14.3% | 11.17k | 2.93s | 33.8 GiB |
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 25.6% | 15.26k | 2.12s | 58.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (RL Full) on 2xA6000: Unknown error
- **Qwen/Qwen3-4B** (SFT Full) on 2xA6000: Unknown error

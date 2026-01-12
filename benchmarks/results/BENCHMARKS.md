# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 05:33 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xHBM3 | 8192 | Recompute | FA2 | 5.7% | 17.54k | 1.09s | 25.0 GiB |
| RL LoRA(r=16) | 2xHBM3 | 8192 | Recompute | FA2 | 5.9% | 22.03k | 1.49s | 23.8 GiB |
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 13.4% | 41.41k | 0.79s | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xHBM3 | 8192 | Recompute | FA2 | 8.5% | 5.09k | 2.46s | 61.4 GiB |
| RL LoRA(r=16) | 2xHBM3 | 8192 | Recompute | FA2 | 14.3% | 11.16k | 2.94s | 33.8 GiB |
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 25.7% | 15.33k | 2.12s | 58.3 GiB |

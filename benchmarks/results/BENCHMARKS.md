# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 20:12 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xA6000 | 8192 | Recompute | FA2 | 4.5% | 4.37k | 5.82s | 25.0 GiB |
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 4.6% | 5.47k | 6.03s | 23.8 GiB |
| SFT Full | 2xA6000 | 8192 | Recompute | FA2 | 6.0% | 5.89k | 5.58s | 25.0 GiB |
| RL Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | 5.7% | 17.60k | 1.10s | 25.0 GiB |
| RL LoRA(r=16) | 2xH100 HBM3 | 8192 | Recompute | FA2 | 5.9% | 22.08k | 1.48s | 23.8 GiB |
| SFT Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | 13.4% | 41.34k | 0.79s | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL LoRA(r=16) | 2xA6000 | 8192 | Recompute | FA2 | 5.7% | 1.41k | 23.05s | 33.8 GiB |
| RL Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | 8.5% | 5.07k | 2.45s | 61.4 GiB |
| RL LoRA(r=16) | 2xH100 HBM3 | 8192 | Recompute | FA2 | 14.3% | 11.16k | 2.93s | 33.8 GiB |
| SFT Full | 2xH100 HBM3 | 8192 | Recompute | FA2 | 25.8% | 15.35k | 2.12s | 58.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (RL Full) on 2xA6000: Unknown error
- **Qwen/Qwen3-4B** (SFT Full) on 2xA6000: Unknown error

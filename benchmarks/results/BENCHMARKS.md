# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 05:01 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xA6000 | 8192 | Recompute | FA2 | 4.0% | 3.91k | 6.18s | 25.0 GiB |
| SFT Full | 2xA6000 | 8192 | Recompute | FA2 | 6.3% | 6.11k | 5.35s | 25.0 GiB |
| RL Full | 2xHBM3 | 8192 | Recompute | FA2 | 5.8% | 18.07k | 1.09s | 25.0 GiB |
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 13.4% | 41.44k | 0.79s | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xHBM3 | 8192 | Recompute | FA2 | 8.4% | 5.03k | 2.45s | 61.4 GiB |
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 25.7% | 15.33k | 2.12s | 58.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (RL Full) on 2xA6000: Unknown error
- **Qwen/Qwen3-4B** (RL LoRA(r=16)) on 2xA6000: Unknown error
- **Qwen/Qwen3-4B** (SFT Full) on 2xA6000: Unknown error
- **Qwen/Qwen3-0.6B** (RL LoRA(r=16)) on 2xHBM3: Unknown error
- **Qwen/Qwen3-4B** (RL LoRA(r=16)) on 2xHBM3: Unknown error
- **Qwen/Qwen3-0.6B** (RL LoRA(r=16)) on 2xA6000: Unknown error

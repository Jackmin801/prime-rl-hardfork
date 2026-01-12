# Performance Benchmarks

Automated nightly benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-12 04:29 UTC  
**Commit:** `unknown`

> :warning: indicates regression > 5% from baseline

## Qwen3-0.6B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| RL Full | 2xA6000 | 8192 | Recompute | FA2 | 4.8% | 4.64k | 5.59s | 25.0 GiB |
| SFT Full | 2xA6000 | 8192 | Recompute | FA2 | 10.8% | 10.57k | 3.09s | 25.0 GiB |

## Qwen3-4B

| Type | Hardware | SeqLen | AC | Attn | MFU | TPS | Step Time | Peak Mem |
|------|----------|--------|----|----|-----|-----|-----------|----------|
| SFT Full | 2xHBM3 | 8192 | Recompute | FA2 | 25.8% | 15.35k | 2.12s | 58.3 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-4B** (RL Full) on 2xA6000: Unknown error
- **Qwen/Qwen3-4B** (SFT Full) on 2xA6000: Unknown error

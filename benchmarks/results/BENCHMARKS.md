# Performance Benchmarks

Automated benchmark results for prime-rl using `--bench` flag.

**Last Updated:** 2026-01-13 19:36 UTC  
**Commit:** `unknown`
**Docker Image:** `primeintellect/prime-rl-jackmin@sha256:9d9093cc3859822777c381cb8f4874098e8b28168760fccf5cfeab5fb88e2d13`

> :warning: indicates regression > 5% from baseline
> diffs shown when abs(change) >= 1.0% (except regressions, which always show diffs)
> :clock10: The Step Time shown is the time taken per micro batch. This differs from what gets displayed in the bench table which is the total step time.
## INTELLECT-3

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH200 | 15.9% | 13.41k | 9.77s | 90.2 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xB200 | 2.6% | 4.89k | 26.79s | 90.4 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xB200 | 5.8% | 5.17k | 101.36s | 153.6 GiB |

## Qwen3-0.6B

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL Full | 8192 | Recompute | FA2 | 1xH100 HBM3 | 5.8% | 8.95k | 0.92s | 11.8 GiB |
| RL Full | 8192 | Recompute | FA2 | 1xA6000 | 7.5% | 3.68k | 2.23s | 11.7 GiB |
| RL LoRA(r=16) | 8192 | Recompute | FA2 | 1xH100 HBM3 | 5.5% | 10.30k | 0.80s | 4.1 GiB |
| RL LoRA(r=16) | 8192 | Recompute | FA2 | 1xA6000 | 6.1% | 3.64k | 2.25s | 4.1 GiB |
| SFT Full | 8192 | Recompute | FA2 | 1xH100 HBM3 | 13.5% | 20.94k | 0.39s | 31.7 GiB |
| SFT Full | 8192 | Recompute | FA2 | 1xA6000 | 13.5% | 6.59k | 1.24s | 31.2 GiB |

## Qwen3-30B-A3B-Instruct-2507

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL Full | 16384 | Recompute | FA2 | 8xB200 | 1.5% | 7.20k | 18.21s | 74.5 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH100 HBM3 | 2.9% | 6.20k | 21.14s | 74.6 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH200 | 2.7% | 5.77k | 22.72s | 74.6 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xB200 | 7.0% | 13.10k | 40.01s | 91.4 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xH200 | 13.2% | 10.97k | 47.80s | 91.4 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH200 | 14.0% | 30.30k | 4.33s | 31.8 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH100 HBM3 | 8.1% | 17.63k | 7.43s | 31.8 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xB200 | 1.9% | 9.52k | 13.77s | 32.0 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH200 | 19.7% | 16.52k | 31.73s | 64.2 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xB200 | 7.0% | 13.33k | 39.34s | 64.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH100 HBM3 | 10.2% | 8.53k | 61.49s | 64.2 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xB200 | 9.7% | 46.28k | 2.83s | 106.4 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xH200 | 17.4% | 36.62k | 3.58s | 106.4 GiB |

## Qwen3-4B-Instruct-2507

| Type | SeqLen | AC | Attn | Hardware | MFU | TPS | Step Time | Peak Mem |
|------|--------|----|----|----------|-----|-----|-----------|----------|
| RL Full | 8192 | Recompute | FA2 | 1xH100 HBM3 | 7.4% | 2.21k | 3.71s | 76.5 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xB200 | 6.6% | 28.30k | 4.63s | 17.0 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH200 | 12.2% | 22.88k | 5.73s | 17.1 GiB |
| RL Full | 16384 | Recompute | FA2 | 8xH100 HBM3 | 9.9% | 18.46k | 7.10s | 17.1 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xB200 | 12.9% | 24.04k | 21.81s | 36.0 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xH200 | 25.1% | 20.58k | 25.47s | 36.1 GiB |
| RL Full | 65536 | Recompute | FA2 | 8xH100 HBM3 | 13.6% | 11.12k | 47.15s | 36.1 GiB |
| RL LoRA(r=16) | 4096 | Recompute | FA2 | 1xA6000 | 9.2% | 1.37k | 2.98s | 18.9 GiB |
| RL LoRA(r=16) | 8192 | Recompute | FA2 | 1xH100 HBM3 | 13.7% | 5.35k | 1.53s | 20.3 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xB200 | 8.8% | 46.27k | 2.83s | 10.2 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH200 | 18.6% | 42.72k | 3.07s | 10.3 GiB |
| RL LoRA(r=16) | 16384 | Recompute | FA2 | 8xH100 HBM3 | 11.2% | 25.79k | 5.08s | 10.3 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xB200 | 12.5% | 25.27k | 20.75s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH200 | 25.2% | 22.45k | 23.35s | 28.8 GiB |
| RL LoRA(r=16) | 65536 | Recompute | FA2 | 8xH100 HBM3 | 13.1% | 11.70k | 44.81s | 28.8 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xB200 | 15.7% | 66.85k | 1.96s | 54.6 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xH200 | 29.2% | 54.71k | 2.40s | 54.6 GiB |
| SFT Full | 16384 | Recompute | FA2 | 8xH100 HBM3 | 17.4% | 32.53k | 4.03s | 54.6 GiB |
| SFT Full | 65536 | Recompute | FA2 | 8xB200 | 14.1% | 26.21k | 20.01s | 171.5 GiB |

## Failed Benchmarks

- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **PrimeIntellect/INTELLECT-3** (SFT Full) on 8xH100 HBM3: [rank6]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 9.25 GiB. GPU 6 has a total capacity of 79.21 GiB of which 1.37 GiB is free. Including non-PyTorch memory, this process has 0 byt
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xH200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL Full) on 8xH200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xH200: Non-zero exit code: 1
- **PrimeIntellect/INTELLECT-3** (RL LoRA(r=16)) on 8xH100 HBM3: [rank5]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 1.38 GiB. GPU 5 has a total capacity of 79.21 GiB of which 974.75 MiB is free. Including non-PyTorch memory, this process has 0 b
- **Qwen/Qwen3-4B-Instruct-2507** (SFT Full) on 8xH100 HBM3: [rank2]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 2 has a total capacity of 79.21 GiB of which 25.56 GiB is free. Including non-PyTorch memory, this process has 0 b
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (SFT Full) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-4B-Instruct-2507** (SFT Full) on 8xH200: [rank1]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 1 has a total capacity of 139.80 GiB of which 11.96 GiB is free. Including non-PyTorch memory, this process has 12
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL Full) on 8xH100 HBM3: [rank7]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 384.00 MiB. GPU 7 has a total capacity of 79.21 GiB of which 274.75 MiB is free. Including non-PyTorch memory, this process has 0
- **PrimeIntellect/INTELLECT-3** (RL Full) on 8xH100 HBM3: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (SFT Full) on 8xH100 HBM3: [rank4]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 384.00 MiB. GPU 4 has a total capacity of 79.21 GiB of which 366.75 MiB is free. Including non-PyTorch memory, this process has 0
- **Qwen/Qwen3-30B-A3B-Instruct-2507** (SFT Full) on 8xH100 HBM3: [rank5]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 96.00 MiB. GPU 5 has a total capacity of 79.21 GiB of which 48.75 MiB is free. Including non-PyTorch memory, this process has 0 b
- **Qwen/Qwen3-30B-A3B-Instruct-2507** (SFT Full) on 8xH100 HBM3: [rank2]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 2 has a total capacity of 79.21 GiB of which 30.68 GiB is free. Including non-PyTorch memory, this process has 0 b
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL Full) on 8xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 384.00 MiB. GPU 0 has a total capacity of 79.21 GiB of which 274.75 MiB is free. Including non-PyTorch memory, this process has 0
- **PrimeIntellect/INTELLECT-3** (RL LoRA(r=16)) on 8xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 1024.00 MiB. GPU 0 has a total capacity of 79.21 GiB of which 1008.75 MiB is free. Including non-PyTorch memory, this process has
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL Full) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xH100 HBM3: [rank2]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 20.00 MiB. GPU 2 has a total capacity of 79.21 GiB of which 16.75 MiB is free. Including non-PyTorch memory, this process has 0 b
- **PrimeIntellect/INTELLECT-3** (RL Full) on 8xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 4.00 GiB. GPU 0 has a total capacity of 79.21 GiB of which 3.86 GiB is free. Including non-PyTorch memory, this process has 0 byt
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (SFT Full) on 8xB200: Non-zero exit code: 1
- **PrimeIntellect/INTELLECT-3** (RL Full) on 8xH200: [rank7]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 352.00 MiB. GPU 7 has a total capacity of 139.80 GiB of which 153.06 MiB is free. Including non-PyTorch memory, this process has 
- **Qwen/Qwen3-30B-A3B-Instruct-2507** (SFT Full) on 8xH200: [rank5]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 5 has a total capacity of 139.80 GiB of which 35.64 GiB is free. Including non-PyTorch memory, this process has 10
- **PrimeIntellect/INTELLECT-3** (SFT Full) on 8xH200: [rank7]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.00 GiB. GPU 7 has a total capacity of 139.80 GiB of which 24.68 GiB is free. Including non-PyTorch memory, this process has 11
- **Qwen/Qwen3-4B-Instruct-2507** (SFT Full) on 1xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 96.00 MiB. GPU 0 has a total capacity of 79.18 GiB of which 20.25 MiB is free. Including non-PyTorch memory, this process has 79.
- **PrimeIntellect/INTELLECT-3** (RL Full) on 8xB200: [rank7]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 352.00 MiB. GPU 7 has a total capacity of 178.36 GiB of which 96.12 MiB is free. Including non-PyTorch memory, this process has 1
- **PrimeIntellect/INTELLECT-3** (SFT Full) on 8xB200: [rank5]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 352.00 MiB. GPU 5 has a total capacity of 178.36 GiB of which 264.12 MiB is free. Including non-PyTorch memory, this process has 
- **PrimeIntellect/INTELLECT-3** (RL LoRA(r=16)) on 8xH200: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 8.00 GiB. GPU 0 has a total capacity of 139.80 GiB of which 7.20 GiB is free. Including non-PyTorch memory, this process has 132.
- **PrimeIntellect/INTELLECT-3** (SFT Full) on 8xB200: [rank2]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.00 GiB. GPU 2 has a total capacity of 178.36 GiB of which 26.02 GiB is free. Including non-PyTorch memory, this process has 15
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (SFT Full) on 8xH200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xB200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL LoRA(r=16)) on 8xH100 HBM3: [rank1]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 20.00 MiB. GPU 1 has a total capacity of 79.21 GiB of which 16.75 MiB is free. Including non-PyTorch memory, this process has 0 b
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (SFT Full) on 8xH200: Non-zero exit code: 1
- **Qwen/Qwen3-30B-A3B-Instruct-2507** (SFT Full) on 8xB200: [rank1]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 37.09 GiB. GPU 1 has a total capacity of 178.36 GiB of which 36.88 GiB is free. Including non-PyTorch memory, this process has 14
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL Full) on 8xH200: Non-zero exit code: 1
- **Qwen/Qwen3-30B-A3B-Instruct-2507** (RL Full) on 8xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 2.00 GiB. GPU 0 has a total capacity of 79.21 GiB of which 1.94 GiB is free. Including non-PyTorch memory, this process has 0 byt
- **PrimeIntellect/INTELLECT-3** (RL Full) on 8xB200: [rank5]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 352.00 MiB. GPU 5 has a total capacity of 178.36 GiB of which 62.12 MiB is free. Including non-PyTorch memory, this process has 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (RL Full) on 8xB200: Non-zero exit code: 1
- **PrimeIntellect/INTELLECT-3** (SFT Full) on 8xH100 HBM3: [rank0]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 4.00 GiB. GPU 0 has a total capacity of 79.21 GiB of which 3.87 GiB is free. Including non-PyTorch memory, this process has 0 byt
- **PrimeIntellect/INTELLECT-3** (RL Full) on 8xH200: Non-zero exit code: 1
- **Qwen/Qwen3-235B-A22B-Instruct-2507** (SFT Full) on 8xH100 HBM3: [rank1]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 384.00 MiB. GPU 1 has a total capacity of 79.21 GiB of which 366.75 MiB is free. Including non-PyTorch memory, this process has 0
- **PrimeIntellect/INTELLECT-3** (SFT Full) on 8xH200: [rank5]: torch.OutOfMemoryError: CUDA out of memory. Tried to allocate 9.25 GiB. GPU 5 has a total capacity of 139.80 GiB of which 2.86 GiB is free. Including non-PyTorch memory, this process has 136.

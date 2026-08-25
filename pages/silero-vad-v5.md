# Silero VAD v5

`silero-vad-v5`

Default voice activity detector. Most accurate backend measured (F1 0.940) and permissively licensed. See docs/adr/0001-vad-backend-licensing.md.

| | |
|---|---|
| Task | voice activity detection |
| Mode | live |
| Languages | any |
| Size | 2.2 MB |
| Licence | MIT |
| Runtime | `onnx/silero-vad` |

## Where this comes from

Published by snakers4/silero-vad.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 12 MB resident, 30 MB at peak. Needs at least 128 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_8t` | 0.006 |

Accuracy, measured — word error rate, lower is better:

| Benchmark | Score |
|---|---|
| `f1_ten_testset` | 94.0% |
| `precision_ten_testset` | 92.5% |
| `recall_ten_testset` | 95.6% |

Accelerators: cpu, coreml, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `silero_vad.onnx` | 2.2 MB | `1a153a22f4509e292a94e67d6f9b85e8deb25b4988682b7e174c65279d8788e3` |


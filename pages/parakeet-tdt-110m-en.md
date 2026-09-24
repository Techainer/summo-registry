# Parakeet TDT 110M · English

`parakeet-tdt-110m-en`

The most accurate English model measured here: 8.4% WER and 5.7% CER on a hundred FLEURS en clips, at 108 MB. A transducer, so text appears while you are still speaking rather than when you stop. Its accuracy was left blank in this registry for a while, with a note that it produced nothing at all for 44 of those clips — that was not the model. Summo was feeding it audio at whatever level it was recorded at, and a NeMo model near the log-mel floor is mostly floor. The recorder levels every utterance now and the same files score 8.4%. See docs/benchmarks.md.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | en |
| Size | 103 MB |
| Licence | CC-BY-4.0 |
| Runtime | `sherpa-onnx/transducer-offline` |

## Where this comes from

Published by NVIDIA NeMo (parakeet-tdt_ctc-110m), ONNX export by k2-fsa/sherpa-onnx.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 200 MB resident, 900 MB at peak. Needs at least 1024 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_8t` | 0.024 |

Accuracy, measured — word error rate, lower is better:

| Benchmark | Score |
|---|---|
| `cer_fleurs_en` | 5.7% |
| `wer_fleurs_en` | 8.4% |

Accelerators: cpu, coreml.

## Files

| Name | Size | sha256 |
|---|---|---|
| `parakeet-tdt-110m-en-int8.tar.bz2` | 103 MB | `f628312e9fdf8686374cb01a69425c41732529d540860311f16f37cbc32cfe9b` |


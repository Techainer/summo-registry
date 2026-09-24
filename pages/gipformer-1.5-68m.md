# Gipformer 1.5 · Vietnamese

`gipformer-1.5-68m`

The Vietnamese model Summo recommends. A 68M-parameter Zipformer transducer exported to INT8, and better than the 65M it replaces on every axis measured: 8.3% WER and 6.2% CER on FLEURS vi against 8.6% and 6.8%, at a slightly lower real-time factor despite being the larger model. Its vocabulary is byte-identical to its predecessor, so it is a drop-in. Measured here on the same hundred clips and the same harness that produced every other figure in docs/benchmarks.md; the publisher reports 15.44% on their own tele-medium set, which is a different benchmark and not comparable.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | vi |
| Size | 70 MB |
| Licence | MIT |
| Runtime | `sherpa-onnx/transducer-offline` |

## Where this comes from

Published by g-group-ai-lab, ONNX export by the publisher.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 150 MB resident, 800 MB at peak. Needs at least 1024 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_4t` | 0.020 |
| `cpu_x86_avx512vnni_8t` | 0.017 |

Accuracy, measured — word error rate, lower is better:

| Benchmark | Score |
|---|---|
| `cer_fleurs_vi` | 6.2% |
| `wer_fleurs_vi` | 8.3% |

Accelerators: cpu, coreml.

## Files

| Name | Size | sha256 |
|---|---|---|
| `encoder.int8.onnx` | 68 MB | `b528768939c7711a889be81a718ea7f2ee50d0d2d384d53f399e15b44bd9408c` |
| `decoder.int8.onnx` | 1.2 MB | `e0a156b5454722a524230f9e35d5d928cfcdd3723437b418e5bd5e04f1c3a101` |
| `joiner.int8.onnx` | 1009 KB | `12636559d135315f002a1e1b477077d415e888477378db0fd450aee5b21ac551` |
| `tokens.txt` | 25 KB | `f536d03c2e95ebd2930cf0abec88e823bd17d3c1933da7ae6a82db3b80605e15` |


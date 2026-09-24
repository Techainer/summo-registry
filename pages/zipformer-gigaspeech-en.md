# Zipformer GigaSpeech · English

`zipformer-gigaspeech-en`

English at 8.9% WER and 5.7% CER on a hundred FLEURS en clips, in 73 MB — the best accuracy per megabyte here, and seven times faster than Whisper base. A transducer, so it produces text while you are still speaking; Whisper declines to decode a half-spoken sentence because it invents an ending for one. Trained on GigaSpeech: ten thousand hours of podcasts, videos and audiobooks. See docs/benchmarks.md.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | en |
| Size | 70 MB |
| Licence | Apache-2.0 |
| Runtime | `sherpa-onnx/transducer-offline` |

## Where this comes from

Published by k2-fsa/icefall, trained on GigaSpeech, ONNX export by csukuangfj.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 210 MB resident, 950 MB at peak. Needs at least 1024 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_4t` | 0.021 |
| `cpu_x86_avx512vnni_8t` | 0.020 |

Accuracy, measured — word error rate, lower is better:

| Benchmark | Score |
|---|---|
| `cer_fleurs_en` | 5.7% |
| `wer_fleurs_en` | 8.9% |

Accelerators: cpu, coreml.

## Files

| Name | Size | sha256 |
|---|---|---|
| `encoder-epoch-30-avg-1.int8.onnx` | 69 MB | `60d83e92a412b137e89c369d7b99ab00effc3cfedb06bc678041cc4dc7e3d0d6` |
| `decoder-epoch-30-avg-1.int8.onnx` | 528 KB | `2b0580feb757696fa929922670b7126aaee609630349a1809fd5a2aee926d56e` |
| `joiner-epoch-30-avg-1.int8.onnx` | 253 KB | `80160e45cca71dd52f6b0a6d3d12be18126f5308b2d4ba03f001300fea377c64` |
| `tokens.txt` | 4.9 KB | `0ef7d736bf4de3ef947292e4b119ef13f6808cd5f3aec225a843a7135ac1c2ce` |


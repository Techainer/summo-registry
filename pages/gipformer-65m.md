# Gipformer 65M · Vietnamese

`summo pull gipformer-65m`

The Vietnamese model Summo defaults to. A 65M-parameter Zipformer transducer exported to INT8, trained on Vietnamese telephony and meeting speech. 2.4% WER on Fleurs VI against Whisper tiny's 65.5%, in a fifth of the memory — which is the whole reason a specialised model is worth having over a multilingual one.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | vi |
| Size | 70 MB |
| Licence | MIT |
| Runtime | `sherpa-onnx/transducer-offline` |

## Where this comes from

Published by g-group-ai-lab, Zipformer transducer trained with k2-fsa/icefall.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 150 MB resident, 800 MB at peak. Needs at least 1024 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx2_4t` | 0.060 |
| `cpu_x86_avx512vnni_8t` | 0.024 |

Accelerators: cpu, coreml.

## Files

| Name | Size | sha256 |
|---|---|---|
| `encoder-epoch-35-avg-6.int8.onnx` | 68 MB | `3cc1a719f04d6051210e03833eef0d42939352c6f4704b67c34655ceecb98809` |
| `decoder-epoch-35-avg-6.int8.onnx` | 1.2 MB | `2b6235b8a8be57b5ba57024f6119398a1aace6aff23347a04d59c9bd2686c1f6` |
| `joiner-epoch-35-avg-6.int8.onnx` | 1009 KB | `eb74e2ead853d64161ee7af2aa2bce5fcc64752d07f72e0683926b238296d58f` |
| `tokens.txt` | 25 KB | `f536d03c2e95ebd2930cf0abec88e823bd17d3c1933da7ae6a82db3b80605e15` |


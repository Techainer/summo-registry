# CAM++ speaker embedding

`summo pull campplus-sv`

Turns a finished utterance into a voice fingerprint, so the remote lane can be split by speaker. Runs after the text is already on screen and costs single-digit milliseconds per utterance.

| | |
|---|---|
| Task | speaker embedding |
| Mode | batch |
| Languages | any |
| Size | 27 MB |
| Licence | Apache-2.0 |
| Runtime | `sherpa-onnx/speaker-embedding` |

## Where this comes from

Published by 3D-Speaker (Alibaba DAMO), ONNX export by csukuangfj.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 60 MB resident, 180 MB at peak. Needs at least 512 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_8t` | 0.006 |

Accelerators: cpu, coreml, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `campplus.onnx` | 27 MB | `f682b514c05d947ee3fa91cd6ec6c5c7543479a128373fa29b1faedccd21fd11` |


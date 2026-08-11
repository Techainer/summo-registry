# Whisper tiny (99 languages)

`summo pull whisper-tiny`

Smallest multilingual model. Good on English, weak on Vietnamese — see the measured numbers before choosing it for a language a specialised model covers.

| | |
|---|---|
| Task | speech recognition |
| Mode | batch |
| Languages | any |
| Size | 99 MB |
| Licence | MIT |
| Runtime | `sherpa-onnx/whisper` |

## Where this comes from

Published by OpenAI Whisper, ONNX export by csukuangfj.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 200 MB resident, 600 MB at peak. Needs at least 1024 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx2_4t` | 0.300 |
| `cpu_x86_avx512vnni_8t` | 0.107 |

Accelerators: cpu, coreml, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `tiny-encoder.int8.onnx` | 12 MB | `d24fb083ae3b1041fc24e97971d60e280c9342201fbb67b0ab428a8b4a51a434` |
| `tiny-decoder.int8.onnx` | 86 MB | `d2fece8dd42771f1df975c6c0445770d0c292bf7547c2cae04a6c0cc57540925` |
| `tiny-tokens.txt` | 798 KB | `b34b360dbb493e781e479794586d661700670d65564001f23024971d1f2fa126` |
| `tiny-encoder.onnx` | 36 MB | `42c1d4cbf889632ba21ab6f0d4064c80209755f265ce5cd630db4a6793e7089c` |
| `tiny-decoder.onnx` | 109 MB | `e144c07dc6b55cece24392811f2d934b97013811f5e677d1315d341a0a74a25d` |


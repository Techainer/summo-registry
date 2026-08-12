# SMALL100 · translation, 100 languages

`summo pull small100`

The small option: 330M parameters against MiLMMT's 1B, and the only translation model here that is not built on a 262 000-token embedding table — which is why it can be small at all. Quantized to int8 it is 449 MB and 377 ms a line, half the disk of the smallest usable MiLMMT and faster; the published export is fp32 and much larger, so quantize it locally (see docs/translation.md). MIT, so unlike the MiLMMT weights it may be redistributed freely. The trade is quality: on Vietnamese meeting speech it makes lexical errors MiLMMT does not — “chốt lại spec API” comes back as “closing the spec” — while still producing complete, on-topic sentences in the right language. That is still far better than any general model of comparable size: Qwen3-0.6B repeated one phrase forty times on the same test and returned nothing at all for English into Vietnamese.

| | |
|---|---|
| Task | translation |
| Mode | batch |
| Languages | ar, az, bg, bn, ca, cs, da, de, el, en, es, fa, fi, fr, he, hi, hr, hu, id, it, ja, kk, km, ko, lo, ms, my, nl, no, pl, pt, ro, ru, sk, sl, sv, ta, th, tl, tr, ur, uz, vi, zh |
| Size | 1.7 GB |
| Licence | MIT |
| Runtime | `onnx/m2m100` |

## Where this comes from

Published by Alireza Mohammadshahi et al., Idiap Research Institute — SMALL100, distilled from M2M100.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 1900 MB resident, 2400 MB at peak. Needs at least 3072 MB free.

No real-time factor has been measured yet. Rather than guess, the registry says so — run `summo-bench` and send the numbers.

Accelerators: cpu, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `model.onnx` | 1.7 GB | `e9af23aff4bb7c277fcd20c94a6edef88e908b82a5af82c269f725010e6f4cc1` |
| `sentencepiece.bpe.model` | 2.3 MB | `d8f7c76ed2a5e0822be39f0a4f95a55eb19c78f4593ce609e2edbc2aea4d380a` |
| `vocab.json` | 3.5 MB | `b6e77e474aeea8f441363aca7614317c06381f3eacfe10fb9856d5081d1074cc` |


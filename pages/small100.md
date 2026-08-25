# SMALL100 · translation, 100 languages

`small100`

The default translator, and the small one: 330M parameters and 611 MB installed, against 806 MB for the 1B alternative — and 244 ms a line, which is the fastest of anything measured. It is the only translation model here not built on a 262 000-token embedding table, which is why it can be small at all: quantizing the 1B harder barely helps, because the table dominates the file. Exported as a separate encoder and decoder, so the twelve-layer encoder runs once per line instead of once per generated token — worth 2x on its own. MIT, so unlike the MiLMMT weights it may be redistributed freely. The trade is accuracy: on Vietnamese meeting speech it makes lexical errors the 1B does not, while still producing complete, on-topic sentences in the right language. Still far ahead of any general model of comparable size — Qwen3-0.6B repeated one phrase forty times on the same test and returned nothing at all for English into Vietnamese.

| | |
|---|---|
| Task | translation |
| Mode | batch |
| Languages | ar, az, bg, bn, ca, cs, da, de, el, en, es, fa, fi, fr, he, hi, hr, hu, id, it, ja, kk, km, ko, lo, ms, my, nl, no, pl, pt, ro, ru, sk, sl, sv, ta, th, tl, tr, ur, uz, vi, zh |
| Size | 583 MB |
| Licence | MIT |
| Runtime | `onnx/m2m100` |

## Where this comes from

Published by Alireza Mohammadshahi et al., Idiap Research Institute — SMALL100, distilled from M2M100. INT8 ONNX export by lyphanthuc..

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 700 MB resident, 1100 MB at peak. Needs at least 1536 MB free.

Nobody has measured how fast this runs yet, and the registry says so rather than guessing.

Accelerators: cpu, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `encoder_int8.onnx` | 274 MB | `83352cd4f325aa50715d09b10faee4e1e504a739032e5054e5526ffa64871c18` |
| `decoder_int8.onnx` | 303 MB | `f8b77cb2f9761cec13f1d0a9a2114f3dea8afeeed16a55d3c383c499b7d2468c` |
| `sentencepiece.bpe.model` | 2.3 MB | `d8f7c76ed2a5e0822be39f0a4f95a55eb19c78f4593ce609e2edbc2aea4d380a` |
| `vocab.json` | 3.5 MB | `b6e77e474aeea8f441363aca7614317c06381f3eacfe10fb9856d5081d1074cc` |


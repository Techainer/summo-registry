# Zipformer · English

`zipformer-en`

English, and fast enough to put words on screen while somebody is still talking. A transducer rather than an encoder-decoder, which is what makes it usable live: it commits an utterance as soon as the speaker stops instead of re-reading the whole segment.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | en |
| Size | 67 MB |
| Licence | Apache-2.0 |
| Runtime | `sherpa-onnx/transducer-offline` |

## Where this comes from

Published by k2-fsa/icefall, trained on LibriSpeech and GigaSpeech, ONNX export by csukuangfj.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 200 MB resident, 900 MB at peak. Needs at least 1024 MB free.

Nobody has measured how fast this runs yet, and the registry says so rather than guessing.

Accelerators: cpu, coreml.

## Files

| Name | Size | sha256 |
|---|---|---|
| `encoder-epoch-99-avg-1.int8.onnx` | 66 MB | `52a48f46c17b19a36fe3927c4d59479bb16eeb2493313ed82c4bf775c2cb8bc8` |
| `decoder-epoch-99-avg-1.int8.onnx` | 1.2 MB | `783cd6b23b8db8e14a43804ecf972ae96e71499cce799e334ab95c961800d797` |
| `joiner-epoch-99-avg-1.int8.onnx` | 253 KB | `48de5d6467a2ab1e72cb5c4d828330be06524d877bc458118b6a4198ca031357` |
| `tokens.txt` | 4.9 KB | `49e3c2646595fd907228b3c6787069658f67b17377c60aeb8619c4551b2316fb` |

## From the publisher

Reproduced verbatim from the project that published these weights. Summo did not write it and has not edited it.

<!-- upstream:begin -->

---
license: apache-2.0
---

The torchscript model is from
https://huggingface.co/Zengwei/icefall-asr-librispeech-zipformer-2023-05-15

The training code is from
https://github.com/k2-fsa/icefall/pull/1058
See https://github.com/k2-fsa/icefall/pull/1058

<!-- upstream:end -->

# VAIS 1000 · giọng tiếng Việt

`vits-vi-vais1000`

One Vietnamese voice, for reading a translated meeting back aloud — `summo dub` lays it over the original recording. Ships as a directory rather than a file: the weights are 63 MB and the rest is the phoneme data piper needs to pronounce anything at all.

| | |
|---|---|
| Task | speech synthesis |
| Mode | batch |
| Languages | vi |
| Size | 64 MB |
| Licence | MIT |
| Runtime | `sherpa-onnx/vits` |

## Where this comes from

Published by piper by rhasspy, finetuned on the VAIS-1000 corpus (CC-BY-4.0); ONNX export published by k2-fsa for sherpa-onnx.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 60 MB resident, 300 MB at peak. Needs at least 512 MB free.

Nobody has measured how fast this runs yet, and the registry says so rather than guessing.

Accelerators: cpu.

## Files

| Name | Size | sha256 |
|---|---|---|
| `vits-piper-vi_VN-vais1000-medium.tar.bz2` | 64 MB | `fa1367710767d36ed5cf13b4a449e20c35ffd12791c2e47c2e64142bfa55551a` |

## From the publisher

Reproduced verbatim from the project that published these weights. Summo did not write it and has not edited it.

<!-- upstream:begin -->

# Model card for vais1000 (medium)

* Language: vi_VN (Vietnamese, Vietnam)
* Speakers: 1
* Quality: medium
* Samplerate: 22,050Hz

## Dataset

* URL: https://ieee-dataport.org/documents/vais-1000-vietnamese-speech-synthesis-corpus
* License: https://creativecommons.org/licenses/by/4.0/

## Training

Finetuned from U.S. English lessac voice (medium quality).

<!-- upstream:end -->

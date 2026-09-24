# LJ Speech · English voice

`vits-en-ljspeech`

One English voice, for reading a translated meeting back aloud — `summo dub` lays it over the original recording. 22.05 kHz, which is the full-bandwidth end of what these voices publish. Measured on this codebase: RTF 0.061 on 4 threads, 235 MB peak while speaking. The training data is public domain, which is rarer among English voices than it sounds — most of the published ones sit on corpora licensed for research only.

| | |
|---|---|
| Task | speech synthesis |
| Mode | batch |
| Languages | en |
| Size | 64 MB |
| Licence | Public domain |
| Runtime | `sherpa-onnx/vits` |

## Where this comes from

Published by rhasspy's piper, trained by Bryce Beattie on the LJ Speech Dataset (public domain); ONNX export published by k2-fsa for sherpa-onnx.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 60 MB resident, 240 MB at peak. Needs at least 512 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_4t` | 0.061 |

Accelerators: cpu.

## Files

| Name | Size | sha256 |
|---|---|---|
| `vits-piper-en_US-ljspeech-medium.tar.bz2` | 64 MB | `3dfb4b759d8be032a4903a9538d128b0fda2a06ab1de6cbc2d93a97e2dd83dba` |


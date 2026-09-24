# AISHELL-3 · 中文语音

`vits-zh-aishell3`

One Mandarin voice, for reading a translated meeting back aloud — `summo dub` lays it over the original recording. The smallest voice here at 32 MB, and the fastest: RTF 0.030 on 4 threads, 158 MB peak while speaking. It synthesises at 8 kHz, which sounds like a phone call beside the 22 kHz English and Vietnamese voices — that is the trade for a Mandarin voice on a licence that can be redistributed, and it is stated here rather than discovered on playback. Pronounces numbers and dates from its own lexicon, so a line with neither is not where it is weakest.

| | |
|---|---|
| Task | speech synthesis |
| Mode | batch |
| Languages | zh |
| Size | 30 MB |
| Licence | Apache-2.0 |
| Runtime | `sherpa-onnx/vits` |

## Where this comes from

Published by k2-fsa/icefall, trained on AISHELL-3 (Beijing Shell Shell, Apache-2.0); ONNX export published by k2-fsa for sherpa-onnx.

Redistributable under its licence, so Summo mirrors it. The checksums below are what you should get from either source.

## What it costs

Memory: about 60 MB resident, 160 MB at peak. Needs at least 512 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_4t` | 0.030 |

Accelerators: cpu.

## Files

| Name | Size | sha256 |
|---|---|---|
| `vits-icefall-zh-aishell3.tar.bz2` | 30 MB | `ab468db3a3308cdd861495e0db2f25d79418a0c00639f74944c7cdf5dd8c6ec1` |


# SenseVoice small · 中文 日本語 한국어 English

`summo pull sense-voice-small`

Chinese, Cantonese, Japanese, Korean and English in one 234 MB model. Non-autoregressive — one encoder pass, no decoder loop — so it is fast enough to drive live text and, unlike Whisper, has no generative decoder to invent an ending for a half-spoken sentence. Measured at RTF 0.044 on eight threads of a Xeon 6226R and 0.062 on four, which is about 2.5× the cost of the Vietnamese transducer per decode; Vietnamese is not one of its languages and gipformer-65m remains the right choice there. Accuracy has not yet been measured by summo-bench: the upstream claim is that it beats Whisper-small while running roughly five times faster, and that claim is theirs, not ours. Summo does not redistribute this model — the files come straight from the publisher under their own licence, which permits commercial use and requires attribution.

| | |
|---|---|
| Task | speech recognition |
| Mode | live |
| Languages | zh, yue, ja, ko, en |
| Size | 228 MB |
| Licence | FunASR Model Open Source License Agreement v1.1 |
| Runtime | `sherpa-onnx/sense-voice` |

## Where this comes from

Published by FunAudioLLM / Alibaba Tongyi SpeechTeam, ONNX export by csukuangfj.

**Not redistributed by Summo.** The download goes to the original host under that project's own terms. Summo is the software that can load the file; it is not the distributor of it.

## What it costs

Memory: about 300 MB resident, 800 MB at peak. Needs at least 1536 MB free.

Real-time factor, measured — below 1.0 keeps up with live audio:

| Machine | RTF |
|---|---|
| `cpu_x86_avx512vnni_4t` | 0.062 |
| `cpu_x86_avx512vnni_8t` | 0.044 |

Accelerators: cpu, coreml, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `model.int8.onnx` | 228 MB | `c71f0ce00bec95b07744e116345e33d8cbbe08cef896382cf907bf4b51a2cd51` |
| `tokens.txt` | 308 KB | `f449eb28dc567533d7fa59be34e2abca8784f771850c78a47fb731a31429a1dc` |
| `model.onnx` | 894 MB | `977016bd9c79f9eb343430b5cc305e07ab64d5212dff41b0dcfa1694bee9a8cb` |


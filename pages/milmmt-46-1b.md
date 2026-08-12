# MiLMMT 46 · 1B · translation

`summo pull milmmt-46-1b`

Translation between 46 languages, running inside Summo — no Ollama, no second process. 806 MB on disk, about 700 ms a line on eight CPU threads, and nothing per line ever. This is what makes translation the one text feature that costs nothing: a 1B model trained for translation beats a general 8B model at it, so the expensive model stays optional and a user with no API key can still translate every meeting they record. Measured against SMALL100, the obvious smaller alternative: better on every sentence tried, at less than half the disk. Vietnamese, Japanese, Chinese, Korean and English are all in its set. Summo does not redistribute it — the file comes from the publisher under the Gemma Terms of Use, which permit commercial use and impose conditions on passing the weights on.

| | |
|---|---|
| Task | translation |
| Mode | batch |
| Languages | ar, az, bg, bn, ca, cs, da, de, el, en, es, fa, fi, fr, he, hi, hr, hu, id, it, ja, kk, km, ko, lo, ms, my, nb, nl, pl, pt, ro, ru, sk, sl, sv, ta, th, tl, tr, ur, uz, vi, yue, zh, zh-Hant |
| Size | 769 MB |
| Licence | Gemma Terms of Use |
| Runtime | `llama.cpp/gguf` |

## Where this comes from

Published by Xiaomi Research (MiLMMT-46-1B-v1.0, built on Gemma 3 1B), GGUF conversion by mradermacher.

**Not redistributed by Summo.** The download goes to the original host under that project's own terms. Summo is the software that can load the file; it is not the distributor of it.

## What it costs

Memory: about 900 MB resident, 1200 MB at peak. Needs at least 2048 MB free.

No real-time factor has been measured yet. Rather than guess, the registry says so — run `summo-bench` and send the numbers.

Accelerators: cpu, metal, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `MiLMMT-46-1B-v1.0.Q4_K_M.gguf` | 769 MB | `74d38ba75108d455326e9deeaf9ab01bb266dfa665eae9c4aa84e84485d4fdf9` |


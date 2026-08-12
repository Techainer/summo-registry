# MiLMMT 46 · 4B · translation

`summo pull milmmt-46-4b`

The same translator, three times the size and measurably better at the sentences that matter. Against the 1B on Vietnamese meeting speech it fixed every error the smaller model made: “chiều nay” as this afternoon rather than this morning, “test tải” as load testing rather than download speed, and the line where the 1B answered a request for Japanese in Thai. It costs about 1.8× the time per line — 2.1 s against 1.2 s on eight CPU threads — and 2.5 GB of disk. Worth it on a machine with the memory to spare; the 1B remains the default because it is the one that fits everywhere. Summo does not redistribute it: the file comes from the publisher under the Gemma Terms of Use.

| | |
|---|---|
| Task | translation |
| Mode | batch |
| Languages | ar, az, bg, bn, ca, cs, da, de, el, en, es, fa, fi, fr, he, hi, hr, hu, id, it, ja, kk, km, ko, lo, ms, my, nb, nl, pl, pt, ro, ru, sk, sl, sv, ta, th, tl, tr, ur, uz, vi, yue, zh, zh-Hant |
| Size | 2.3 GB |
| Licence | Gemma Terms of Use |
| Runtime | `llama.cpp/gguf` |

## Where this comes from

Published by Xiaomi Research (MiLMMT-46-4B-v1.0, built on Gemma 3 4B), GGUF conversion by mradermacher.

**Not redistributed by Summo.** The download goes to the original host under that project's own terms. Summo is the software that can load the file; it is not the distributor of it.

## What it costs

Memory: about 2700 MB resident, 3200 MB at peak. Needs at least 6144 MB free.

No real-time factor has been measured yet. Rather than guess, the registry says so — run `summo-bench` and send the numbers.

Accelerators: cpu, metal, cuda.

## Files

| Name | Size | sha256 |
|---|---|---|
| `MiLMMT-46-4B-v1.0.Q4_K_M.gguf` | 2.3 GB | `25424cbb5423afaa22b1b53bfb3d8aa116cfd84b5f8dcfa82363bfb3c4221ddf` |


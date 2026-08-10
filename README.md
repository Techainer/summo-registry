# Summo model registry

The catalogue Summo installs models from. Static JSON, nothing else — no server, no database, no
API. That is the point: a registry that is only files can be forked, mirrored, served from a
directory, or read straight from this repository if every piece of Summo's own infrastructure
disappears.

## How the app finds it

Summo resolves a model id through a chain and takes the first source that answers:

1. `SUMMO_REGISTRY` — a URL or a local directory, for a private or offline registry
2. `https://registry.summo.app` — a CDN mirror of this repository, faster and nothing more
3. `https://raw.githubusercontent.com/summo-app/summo-registry/main` — this repository
4. the `url` and `mirror` fields inside the manifest itself, which point upstream

So a model stays installable when the CDN is gone, when this repository is unreachable, and when
both are — as long as whoever published the weights still hosts them.

## Adding a model

Write `models/<id>.json` and open a pull request. CI does the rest: it validates the schema, fetches
each file to confirm the digest and size, runs a short benchmark where one applies, and fails on a
missing licence or attribution.

```json
{
  "schema": 1,
  "id": "my-model",
  "name": "My Model",
  "task": "asr",
  "mode": "batch",
  "runtime": "sherpa-onnx/transducer-offline",
  "langs": ["vi"],
  "license": "Apache-2.0",
  "attribution": "whoever-published-it",
  "profile": {
    "rss_mb": { "idle": 150, "peak": 800 },
    "min_ram_mb": 1024,
    "rtf": { "cpu_x86_avx512vnni_8t": 0.021 },
    "quality": { "wer_fleurs_vi": 0.024 },
    "accel": ["cpu"]
  },
  "files": [
    { "name": "encoder.onnx", "sha256": "…", "size": 123, "url": "https://…" }
  ],
  "params": { "encoder": "encoder.onnx", "tokens": "tokens.txt" }
}
```

`params` is not decoration. Installed files are stored by content hash, so nothing can be found on
disk by looking for `encoder.onnx` — `params` is the only mapping from what a runtime expects to a
real path.

`profile` is what makes a recommendation possible. `rtf` is keyed by hardware class, so the app can
tell a user whether a model will keep up on *their* machine rather than quoting a number measured
on a server. A model with no measurements is treated as slow, because guessing optimistically
recommends something that then cannot keep up.

## What the rules exist for

**`license` is required.** A model with unclear terms cannot ship in a product anyone sells.

**`attribution` is required for attribution licences.** CC-BY-4.0 is a real obligation, not a
formality, and it is the kind that gets missed by accident.

**`redistributable: false` means we may not host it.** Such a manifest must point at upstream, and
CI rejects one that references a Summo CDN — otherwise a mirroring job would quietly make us the
distributor of something we are not allowed to distribute.

**Digests are fatal on mismatch.** A corrupted model does not crash; it produces confidently wrong
transcripts, which is worse.

## Validating locally

```bash
cargo run -p summo-cli -- registry check .
SUMMO_REGISTRY=. summo setup --lang vi
```

## Licence

Manifests: MIT. The models they describe keep their own licences — see [NOTICE](NOTICE).

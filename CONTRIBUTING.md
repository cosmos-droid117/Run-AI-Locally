# Contributing

Thanks for helping keep this guide accurate! Local AI moves fast, so small fixes are very welcome.

## Easy ways to help

- **Update a model recommendation** when something clearly better appears for a tier (8 / 16 / 32 GB).
- **Fix a wrong number** (download size, memory use, speed) and say how you measured it.
- **Add a troubleshooting entry** for a problem you solved.
- **Add your hardware to the benchmarks** (see below).
- **Improve wording**, fix typos, translate docs.

## Updating the recommender script

Model tiers live in the `TIERS` list at the top of `scripts/recommend.py`. Each entry is:

```python
("ollama-tag", approx_download_gb, "short note")
```

Before opening a PR, check that the tag exists in the [Ollama library](https://ollama.com/library) and run:

```bash
python scripts/recommend.py --ram 8
python scripts/recommend.py --ram 16
python scripts/recommend.py --ram 32
```

## Benchmark contributions

Add one row to `docs/choose-a-model.md` (community section) in this format:

`CPU/GPU | RAM/VRAM | model:tag | tokens per second | OS`

Get tokens per second with `ollama run <model> --verbose` and read the `eval rate` line.

## Pull request checklist

- [ ] Facts are verified (link a source when you can)
- [ ] Commands were actually run
- [ ] No affiliate links or promotion
- [ ] Short, plain English

Be kind and constructive. Everyone starts as a beginner.

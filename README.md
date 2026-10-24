# Run AI Locally 🧠💻

> Run ChatGPT-style AI **for free, offline and private** on your own laptop. No account, no subscription, no data leaving your machine.

**Last verified: October 2026** · Beginner friendly · Windows / macOS / Linux

## Why run AI locally?

- **Free:** no monthly fee, no usage limits.
- **Private:** your documents and prompts never leave your computer.
- **Offline:** works on a plane, in a cabin, behind a firewall.
- **Yours:** no sudden model changes, no account bans.

## Quick start (5 minutes)

**1. Install Ollama** (the easiest way to run local models): <https://ollama.com/download>

**2. Find the right model for your computer:**

```bash
python scripts/recommend.py
```

The script reads your RAM/GPU and prints the exact command to run, for example:

```bash
ollama run qwen3:8b
```

**3. Chat.** That's it. The first run downloads the model, then it works offline.

> No Python? Skip step 2 and use the table below.

## Which model should I run?

Match the model to your memory first. Quantized (Q4) models need roughly their download size plus 2-3 GB of headroom.

| Your RAM (or GPU VRAM) | Good first choice | Also good | Command |
| --- | --- | --- | --- |
| 8 GB | Qwen3 8B (tight) or Gemma 3 4B | Qwen3 4B, Llama 3.2 3B, Phi-4-mini | `ollama run gemma3:4b` |
| 16 GB | Qwen3 14B | Gemma 3 12B, Phi-4, DeepSeek-R1 14B | `ollama run qwen3:14b` |
| 32 GB | Qwen3 32B | Gemma 3 27B, gpt-oss 20B | `ollama run qwen3:32b` |
| 64 GB+ | Llama 3.3 70B | Qwen3 32B | `ollama run llama3.3:70b` |

Rough speed: on CPU only, a 14B model gives about 6-10 tokens/second (readable chat speed); with a GPU holding the whole model, expect several times faster. Real numbers depend on your hardware.

Full guide with use-case picks (coding, writing, reasoning): [docs/choose-a-model.md](docs/choose-a-model.md)

## Guides

- [Install Ollama and run your first model](docs/install.md)
- [Choose a model for your hardware and task](docs/choose-a-model.md)
- [Troubleshooting: slow, crashing, out of memory](docs/troubleshooting.md)

## Hardware auto-detector

[`scripts/recommend.py`](scripts/recommend.py) uses only the Python standard library.

```bash
python scripts/recommend.py            # auto-detect
python scripts/recommend.py --ram 16   # "what if I had 16 GB?"
python scripts/recommend.py --vram 12  # "what if my GPU has 12 GB?"
```

## Contributing

Models change fast, and this repo only stays useful if it stays current. Found a better model for a tier, a wrong number, or a fix for a common problem? Please open a pull request. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Star history / support

If this saved you time or money, a ⭐ helps others find it.

## License

[MIT](LICENSE)

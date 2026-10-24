# Choose a model for your hardware and task

_Last verified: October 2026. Models change quickly: check the [Ollama library](https://ollama.com/library) for newer releases and open a PR if this page is out of date._

## The one rule

**Memory decides what you can run.** A Q4 model needs about its download size plus 2-3 GB for the system and the conversation. If a model does not fit, it gets very slow or crashes.

## By memory

### 8 GB

Stay in the 3B-8B range.

| Model | Approx. size | Command | Notes |
| --- | --- | --- | --- |
| Gemma 3 4B | ~3.3 GB | `ollama run gemma3:4b` | Light, good on laptops and Apple Silicon |
| Qwen3 4B | ~2.6 GB | `ollama run qwen3:4b` | Comfortable headroom |
| Qwen3 8B | ~5 GB | `ollama run qwen3:8b` | Best quality that fits; close other apps first |
| Phi-4-mini | ~2.5 GB | `ollama run phi4-mini` | Small and surprisingly capable |

### 16 GB (the sweet spot)

| Model | Approx. size | Command | Notes |
| --- | --- | --- | --- |
| Qwen3 14B | ~9 GB | `ollama run qwen3:14b` | Daily driver |
| Gemma 3 12B | ~8 GB | `ollama run gemma3:12b` | Strong, handles images |
| Phi-4 | ~9 GB | `ollama run phi4` | Good reasoning, shorter context |
| DeepSeek-R1 14B | ~9 GB | `ollama run deepseek-r1:14b` | Shows step-by-step thinking |

### 32 GB and up

| Model | Approx. size | Command | Notes |
| --- | --- | --- | --- |
| Qwen3 32B | ~20 GB | `ollama run qwen3:32b` | Near-frontier quality offline |
| Gemma 3 27B | ~17 GB | `ollama run gemma3:27b` | Excellent all-rounder |
| gpt-oss 20B | ~14 GB | `ollama run gpt-oss:20b` | Reasoning and agent-style tasks |

A good habit at 32 GB: keep a fast small model for quick questions and a big one for hard problems.

## By task

| I want to... | Try |
| --- | --- |
| Chat, summarize, write | Qwen3 or Gemma 3 at the size that fits your RAM |
| Get coding help | `qwen2.5-coder:7b` (16 GB), larger Qwen coder models with more memory |
| Solve logic / math problems | `deepseek-r1:14b`, `phi4` |
| Describe images | `gemma3:12b` (multimodal) |
| Search my own documents (RAG) | Any chat model plus `nomic-embed-text` for embeddings |

Reasoning ("thinking") models are slower because they write out their steps first. Do not use them for fast autocomplete.

## CPU, GPU and Apple Silicon

- **GPU with enough VRAM:** fastest. Fit the whole model inside VRAM.
- **Apple Silicon (M1-M4):** memory is shared, so your total RAM is your budget. Works very well.
- **CPU only:** works fine for chat, just slower. A 14B model gives roughly 6-10 tokens per second, which is about reading speed.

## Community benchmarks

Add your own row (see [CONTRIBUTING.md](../CONTRIBUTING.md)).

| CPU / GPU | RAM / VRAM | Model | Tokens/s | OS |
| --- | --- | --- | --- | --- |
| _your hardware here_ | | | | |

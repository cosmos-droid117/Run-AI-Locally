# Troubleshooting

## It is extremely slow

- The model is probably too big for your memory and is spilling to disk. Run `ollama ps` to see how much is on CPU versus GPU.
- Pick the next size down (for example 14B to 8B, or 8B to 4B).
- Close your browser and other heavy apps.
- Reduce context length if you set it very high.

## My computer froze or the model crashed

Out of memory. Use a smaller model or a more compressed one. Remember: model size + 2-3 GB must fit in RAM/VRAM.

## `ollama: command not found`

Close and reopen your terminal after installing. If it still fails, reinstall from <https://ollama.com/download>.

## Download keeps failing

Re-run the same `ollama pull <model>` command; downloads resume. Check free disk space with your OS tools. A 14B model needs about 9 GB.

## The GPU is not used

- Update your GPU drivers.
- Run `ollama ps` and look at the PROCESSOR column.
- If the model is larger than your VRAM, part of it runs on CPU. Use a smaller model to fit fully on the GPU.

## Answers are wrong or made up

Local models can hallucinate, especially small ones. Use a bigger model, give it the source text in the prompt, and double-check important facts.

## How do I free disk space?

```bash
ollama list
ollama rm <model-name>
```

## Still stuck?

Open an issue with your OS, RAM, GPU (if any), the command you ran and the full error message.

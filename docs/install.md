# Install Ollama and run your first model

Ollama is a free tool that downloads and runs open AI models with one command.

## 1. Install

| System | How |
| --- | --- |
| Windows | Download the installer from <https://ollama.com/download> and run it |
| macOS | Download the app from <https://ollama.com/download> and drag it to Applications |
| Linux | Follow the install command shown on <https://ollama.com/download> |

Check that it works:

```bash
ollama --version
```

## 2. Pick a model

```bash
python scripts/recommend.py
```

Or use the table in the [README](../README.md).

## 3. Run it

```bash
ollama run gemma3:4b
```

The first run downloads the model (a few GB), so use a good connection. After that it works offline. Type your question and press Enter. Type `/bye` to exit.

## Useful commands

```bash
ollama list              # models you have downloaded
ollama ps                # models currently loaded in memory
ollama pull qwen3:8b     # download without starting a chat
ollama rm qwen3:8b       # delete a model to free disk space
ollama run qwen3:8b --verbose   # show speed (tokens/second)
```

## Use it from your own code

Ollama runs a local server at `http://localhost:11434` and also offers an OpenAI-compatible API, so many existing tools can point at it:

```python
from openai import OpenAI

client = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")
reply = client.chat.completions.create(
    model="qwen3:8b",
    messages=[{"role": "user", "content": "Explain recursion in one paragraph."}],
)
print(reply.choices[0].message.content)
```

## Prefer a graphical app?

Desktop apps such as LM Studio let you search, download and chat with models without a terminal. The model recommendations in this repo apply to them too.

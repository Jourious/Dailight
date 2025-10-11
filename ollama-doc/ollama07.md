# Context length

Context length is the maximum number of tokens that the model has access to in memory.

<Note>
  The default context length in Ollama is 4096 tokens.
</Note>

Tasks which require large context like web search, agents, and coding tools should be set to at least 32000 tokens.

## Setting context length

Setting a larger context length will increase the amount of memory required to run a model. Ensure you have enough VRAM available to increase the context length.

For best performance, use the maximum context length for a model, and avoid offloading the model to CPU. Verify the split under `PROCESSOR` using `ollama ps`.

```
ollama ps
```

```
NAME             ID              SIZE      PROCESSOR    CONTEXT    UNTIL
gemma3:latest    a2af6cc3eb7f    6.6 GB    100% GPU     65536      2 minutes from now
```

### App

Change the slider in the Ollama app under settings to your desired context length.
<img src="https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=e8a7ccd30fd9cee5e93662db05b43dc7" alt="Context length in Ollama app" data-og-width="2724" width="2724" data-og-height="2570" height="2570" data-path="images/ollama-settings.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?w=280&fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=434e8ffd8ad5ce5a6cf77cef285aa4d7 280w, https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?w=560&fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=879ba157a13c3ef59a76cf21f04baae4 560w, https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?w=840&fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=7c7314c5f77798307a93ff466501d1cc 840w, https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?w=1100&fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=b39e7ab998d6894649f5e4ac4bfb51e0 1100w, https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?w=1650&fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=1c854c1d41672b2f937ba9db4454e159 1650w, https://mintcdn.com/ollama-9269c548/SjntZZpXgbN5v4M5/images/ollama-settings.png?w=2500&fit=max&auto=format&n=SjntZZpXgbN5v4M5&q=85&s=1f1b926851fec5786cb5fc886cd41cdc 2500w" />

### CLI

If editing the context length for Ollama is not possible, the context length can also be updated when serving Ollama.

```
OLLAMA_CONTEXT_LENGTH=32000 ollama serve
```

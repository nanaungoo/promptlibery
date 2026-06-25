# Zed + 9Router Integration Notes

## Environment

* Zed Version: `1.8.2`
* 9Router URL: `http://localhost:20128/v1`
* 9Router is exposing an OpenAI-compatible API.
* `requireApiKey = false` in 9Router configuration.
* Available API key:

  * Managed through 9Router UI.
  * Recommended: configure in Zed Provider Settings instead of settings.json.

---

## Verified 9Router Models

Output from:

```bash
curl http://localhost:20128/v1/models
```

Returned combo models:

* light
* high
* free
* fast
* neviada

Returned direct models:

### Antigravity

* ag/gemini-3-flash-agent
* ag/gemini-3.5-flash-low
* ag/gemini-3.5-flash-extra-low
* ag/gemini-pro-agent
* ag/gemini-3.1-pro-low
* ag/claude-sonnet-4-6
* ag/claude-opus-4-6-thinking
* ag/gpt-oss-120b-medium
* ag/gemini-3-flash

### Gemini CLI

* gc/gemini-3.1-pro-preview
* gc/gemini-3-pro-preview
* gc/gemini-3-flash-preview
* gc/gemini-3.1-flash-lite-preview
* gc/gemini-2.5-pro
* gc/gemini-2.5-flash
* gc/gemini-2.5-flash-lite

### GitHub Models

* gh/gpt-5.2
* gh/gpt-5.2-codex
* gh/gpt-5.3-codex
* gh/gpt-5.4
* gh/gpt-5.4-mini
* gh/claude-haiku-4.5
* gh/claude-opus-4.5
* gh/claude-sonnet-4.5
* gh/claude-sonnet-4.6
* gh/claude-opus-4.6
* gh/claude-opus-4.7
* gh/gemini-2.5-pro
* gh/gemini-3-flash-preview
* gh/gemini-3.1-pro-preview
* gh/grok-code-fast-1
* gh/oswe-vscode-prime
* gh/goldeneye-free-auto

### NVIDIA

* nvidia/minimaxai/minimax-m2.7

---

## Combo Definitions

### high

Models:

* ag/gemini-pro-agent
* gh/claude-sonnet-4.6
* gc/gemini-2.5-pro
* ag/claude-sonnet-4-6
* ag/claude-opus-4-6-thinking
* gh/claude-opus-4.6
* gh/gemini-3.1-pro-preview
* gh/gpt-5.4
* gc/gemini-3.1-pro-preview

Purpose:

* Highest quality
* Best reasoning
* Best coding

---

### fast

Models:

* ag/gemini-3-flash
* gh/grok-code-fast-1
* gh/claude-haiku-4.5
* gc/gemini-3.1-flash-lite-preview
* ag/gemini-3.5-flash-low
* oc/deepseek-v4-flash-free

Purpose:

* Fast responses
* Good coding speed

---

### light

Models:

* ag/gemini-3.5-flash-extra-low
* mmf/mimo-auto
* oc/deepseek-v4-flash-free

Purpose:

* Lightweight usage
* Low cost

---

### free

Models:

* oc/minimax-m3-free
* oc/deepseek-v4-flash-free
* mmf/mimo-auto
* oc/nemotron-3-ultra-free
* oc/mimo-v2.5-free
* oc/big-pickle
* oc/north-mini-code-free
* oc/qwen3.6-plus-free

Purpose:

* Free-tier models only

---

### neviada

Models:

* nvidia/minimaxai/minimax-m2.7

Purpose:

* NVIDIA route

---

## Recommended Zed Configuration

```json
{
  "language_models": {
    "openai_compatible": {
      "9router": {
        "api_url": "http://localhost:20128/v1",
        "available_models": [
          {
            "name": "high",
            "display_name": "9Router High",
            "max_tokens": 1000000,
            "capabilities": {
              "tools": true,
              "images": true,
              "parallel_tool_calls": true,
              "prompt_cache_key": true,
              "chat_completions": true,
              "interleaved_reasoning": true
            }
          },
          {
            "name": "fast",
            "display_name": "9Router Fast",
            "max_tokens": 1000000,
            "capabilities": {
              "tools": true,
              "images": true,
              "parallel_tool_calls": true,
              "prompt_cache_key": true,
              "chat_completions": true,
              "interleaved_reasoning": true
            }
          },
          {
            "name": "light",
            "display_name": "9Router Light",
            "max_tokens": 1000000,
            "capabilities": {
              "tools": true,
              "images": true,
              "parallel_tool_calls": true,
              "prompt_cache_key": true,
              "chat_completions": true,
              "interleaved_reasoning": true
            }
          },
          {
            "name": "free",
            "display_name": "9Router Free",
            "max_tokens": 1000000,
            "capabilities": {
              "tools": true,
              "images": true,
              "parallel_tool_calls": true,
              "prompt_cache_key": true,
              "chat_completions": true,
              "interleaved_reasoning": true
            }
          },
          {
            "name": "neviada",
            "display_name": "9Router Neviada",
            "max_tokens": 128000,
            "capabilities": {
              "tools": true,
              "images": true,
              "parallel_tool_calls": true,
              "prompt_cache_key": true,
              "chat_completions": true,
              "interleaved_reasoning": true
            }
          }
        ]
      }
    }
  },

  "agent": {
    "default_model": {
      "provider": "9router",
      "model": "high"
    }
  }
}
```

---

## Notes

* Zed requires `max_tokens`.
* Zed does not automatically import models from `/v1/models`.
* Combo models are preferable to exposing dozens of underlying models.
* API keys should be configured through Zed Provider Settings UI.
* `high` is the preferred default model.
* `fast` is useful for quick coding tasks.

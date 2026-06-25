{
    "edit_predictions": {
        "provider": "open_ai_compatible_api",
        "open_ai_compatible_api": {
            "model": "9Router High",
            "api_url": "http://localhost:20128/v1"
        },
        "ollama": {
            "api_url": "http://localhost:11434"
        }
    },
    "context_servers": {
        "mcp-server-markitdown": {
            "enabled": true,
            "remote": false,
            "settings": {
                "package_version": "latest"
            }
        },
        "codebase-memory-mcp": {
            "command": "/home/nanaungoo/.local/bin/codebase-memory-mcp",
            "args": [
                ""
            ]
        }
    },
    "agent": {
        "tool_permissions": {
            "tools": {
                "terminal": {
                    "default": "allow"
                }
            }
        },
        "inline_assistant_model": {
            "provider": "9router",
            "model": "fast",
            "enable_thinking": false
        },
        "default_profile": "write",
        "default_model": {
            "provider": "9router",
            "model": "fast",
            "enable_thinking": false
        },
        "favorite_models": [],
        "model_parameters": []
    },
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
                        "max_tokens": 200000,
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
                        "max_tokens": 200000,
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
                        "max_tokens": 180000,
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
    }
}

# Available Models

Every Hosted Claws plan includes AI models — no API keys required. Models are hosted on DigitalOcean Gradient and billed as part of your plan.

## Model Catalog

### Standard Tier ($25/mo)

| Model | Parameters | Context | Best For |
|-------|-----------|---------|----------|
| **GPT-OSS 20B** | 21B (3.6B active) | 128k | Daily tasks, chat, coding — fast and capable |
| **GPT-OSS 120B** | 120B (5.1B active) | 128k | Complex reasoning, longer tasks |
| **GPT-5 nano** | — | — | Quick responses, simple queries |

All three models support **tool calling** and **chain-of-thought reasoning**.

### Pro Tier ($50/mo)

Everything in Standard, plus:

| Model | Parameters | Context | Best For |
|-------|-----------|---------|----------|
| **GPT-5 mini** | — | — | Stronger reasoning, multi-step tasks |
| **Llama 3.3 70B** | 70B | 128k | Open-weight alternative, strong at code |

### Enterprise Tier ($200/mo)

Everything in Pro, plus:

| Model | Parameters | Context | Best For |
|-------|-----------|---------|----------|
| **GPT-5.2** | — | — | Frontier reasoning and coding |
| **GPT-5.3 Codex** | — | — | Specialized code generation |
| **Claude Sonnet 4.6** | — | 200k | Nuanced writing, analysis, long context |
| **Claude Opus 4.6** | — | 200k | Most capable Claude — complex tasks |

## How Models Are Selected

Your OpenClaw assistant automatically selects the best model for each task based on complexity. You can also specify a model preference in your assistant's configuration.

## About GPT-OSS

GPT-OSS models are OpenAI's open-weight models released under the **Apache 2.0** license. They use a Mixture-of-Experts (MoE) architecture — only a fraction of parameters are active per token, making them fast and efficient while maintaining strong benchmark scores.

The 20B model matches **o3-mini** on most benchmarks, making it an exceptional value for the Standard tier.

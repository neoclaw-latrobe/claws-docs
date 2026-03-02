# Getting the Best Out of Your OpenClaw

Welcome to your managed OpenClaw instance. Your assistant is not just a chatbot—it is an autonomous agent capable of modifying its own world.

## The "Art of the Possible"
Trial users often hit a wall trying to figure out what to ask. Here are the Golden Rules for a powerhouse assistant:

### 1. Let the Bot Build Its Own Skills
Don't just ask "Can you do X?" Ask: **"I want you to be able to do X. Research the API/documentation for X and help me build a new skill to handle it."**

### 2. Autonomous Configuration
Instead of manually editing your `openclaw.json`, try telling your bot: 
- "I want to connect my Discord. What information do you need from me to configure the channel yourself?"
- "Set up a 4-hour heartbeat to monitor my Shopify orders and report back."

### 3. The "Director" Mindset
Treat your assistant as an Operations Manager. Give it a goal, a budget (token/resource limits), and a schedule. 

## Best Practices
- **Memory is Durable:** Your assistant uses `MEMORY.md`. Periodically ask it to "Summarise our recent progress and update your long-term memory."
- **Skill Discovery:** Run `agents_list` or ask "What skills do you currently have access to?"
- **Proactive Heartbeats:** Configure tasks in `HEARTBEAT.md` to ensure your assistant works while you sleep.

---
*Managed by Hosted-Claws.com*

## Mastering the Prompt
To get the best results from your assistant, we recommend following industry-standard prompt engineering practices.

### Recommended Reading
*   **Anthropic's Prompt Engineering Guide** - [Docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
    *   Best for: Claude-powered instances and learning "Chain of Thought" reasoning.
*   **OpenAI Prompting Best Practices** - [Docs](https://platform.openai.com/docs/guides/prompt-engineering)
    *   Best for: GPT-powered instances and clear, instruction-based tasking.
*   **PromptingGuide.ai** - [Visit Site](https://www.promptingguide.ai/)
    *   A comprehensive resource for advanced techniques like Few-Shot prompting and Delimiters.

### Key Tip: Use Delimiters
When providing your bot with text to analyze (like an email or a script), wrap it in triple quotes (`\"\"\"`) or XML tags (`<text>...</text>`). This helps the agent distinguish between your instructions and the data it needs to process.

---
*Managed by Hosted-Claws.com*

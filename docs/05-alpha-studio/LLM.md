---
sidebar_position: 4
---

# LLM Configuration

The LLM Configuration section of the UI allows users to seamlessly set up and manage the Large Language Model (LLM) settings for their agents. This configuration panel ensures agents can connect to the appropriate provider and utilize the desired model for processing tasks, queries, and responses. With a simple and intuitive interface, users can define the LLM provider, model type, and authentication credentials in just a few clicks.

![LLM Config](./img/LLM_config.jpg)


#### UI Components

1. Provider:
   - Dropdown menu to select the LLM provider (e.g., OpenAI, Anthropic).
   - Ensures flexibility in choosing the right provider for your use case.

2. Model:
   - A secondary dropdown to specify the exact model to use (e.g., `gpt-4`, `claude-2`).
   - The list of available models updates dynamically based on the selected provider.

3. API Key:
   - A secure input field to enter the API key required to authenticate with the selected provider.
   - The key is securely stored and used only for the configured model requests.

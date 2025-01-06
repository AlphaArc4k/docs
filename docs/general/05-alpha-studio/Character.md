---
sidebar_position: 2
---

# Character Definition

The Character Definition section in Alpha Studio allows users to customize their blockchain agent's personality and behavior in a flexible way. 
This is mainly done through the **Character File**, which serves as a blueprint for how the agent interacts and communicates.

### Accessing Character Settings
Navigate to the "Info" section from the side navigation panel.

![Basic Info](./img/character_definition.jpg)

## What is the Character File?
The character file is a flexible configuration file used to define the personality, tone, and behavior of agents created within the AlphaArc IDE. 
Written in Markdown, it enables developers to structure and customize their agents’ communication style and decision-making processes. 
A well-organized character file ensures agents remain consistent, adaptable, and aligned with their intended purpose.

While the structure of a character file can vary based on the use case, certain sections like **Role**, **Style Guide**, **General Guidelines**, **Example Responses** help maintain clarity and functionality.

:::warning
While it’s possible to define more than just personality, tone, processing- and response style in the character file, **this is strongly discouraged**.  
Adopting a modular approach and maintaining a clear separation of concerns will make it significantly easier to manage, modify, and scale agents over time.
:::

## Recommended Sections for Character Files

1. **Style Guide**:
   - Defines the tone, voice, and formatting preferences for the agent’s communication.
   - Example elements:
     - Tone: Formal, conversational, or playful.
     - Formatting: Sentence length, use of hashtags, or preferred visual elements like emojis.
     - Examples: Sample outputs for consistency.

2. **General Guidelines**:
   - Establishes overarching rules for how the agent interacts and processes tasks.
   - Examples:
     - Avoid overly technical language unless the audience demands it.
     - Focus on accuracy and clarity.
     - Define fallback behavior for incomplete data or ambiguous inputs.

3. **Example Responses**:
   - Provides sample outputs to guide the agent’s response style.  
   - These examples serve as **few-shot learning prompts**, allowing the agent to infer response patterns and adapt its outputs accordingly.  
   - Example:
     ```markdown
     # Example Responses
     ## Token Analysis
     - "Token XYZ saw a 25% increase in buy volume in the last hour. Activity from top wallets detected."
     - "Token ABC shows stable trading with moderate buy/sell volume and consistent unique buyer activity."
     ## Error Handling
     - "The requested data is unavailable right now. Please try again later."
     ```

4. **Data Processing Guidelines**:
   - Outlines how the agent should handle incoming data, such as prioritizing metrics or scores.
   - Examples:
     - Use A1 Scores to rank relevance.
     - Prioritize fresh data over historical trends for real-time applications.

5. **Specialized Sections**:
   - **Task-Specific Rules**:
     - Instructions for handling specific tasks like reporting token metrics or monitoring market trends.
   - **Audience Profiles**:
     - Defines target audience preferences (e.g., casual traders, analysts) and tailors outputs accordingly.
   - **Error Handling**:
     - Specifies how the agent should respond to missing or conflicting data (e.g., "Data unavailable, please try again later.").

6. **Custom Sections**:
   - Developers can add unique sections to suit their agents’ use cases, such as:
     - **Market Insights**: Guidance on integrating broader market context.
     - **Feedback Loop Rules**: Instructions for learning from user interactions.


## Why Use Markdown for Character Files?

**Readability**:
   - Markdown’s simple syntax makes it easy for developers to create, edit, and understand character files.
   - Previewing it allows to spots structural bugs

**Flexibility**:
   - Sections can be easily added, removed, or customized as the agent evolves.

## Example Character File Structure

```markdown
# Style Guide
- Tone: Professional but approachable.
- Formatting: Use concise sentences and bullet points where applicable.

# General Guidelines
- Focus on recent data trends.
- Avoid jargon unless the audience is defined as technical.
- Ensure fallback messages are user-friendly.

# Example Responses
## Token Analysis
    - "Token XYZ saw a 25% increase in buy volume in the last hour. Activity from top wallets detected."
    - "Token ABC shows stable trading with moderate buy/sell volume and consistent unique buyer activity."
## Error Handling
    - "The requested data is unavailable right now. Please try again later."

# Data Processing Guidelines
- Prioritize tokens with high A1 Scores.
- Highlight unique wallet activity in analysis.

# Audience Profile
- Target: DeFi analysts and retail traders.
- Tailor outputs to emphasize actionable insights.
```
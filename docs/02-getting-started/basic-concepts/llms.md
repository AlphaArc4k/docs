---
sidebar_position: 2
---

# Large Language Models (LLMs)

## 2.2.1 LLMs

Large Language Models (LLMs) like GPT are at the core of AlphaArc’s agents, acting as both the reasoning engine and the natural language interface.

On a higher level their role includes:

- **Understanding Blockchain Data:** AlphaArc transforms raw Solana data into formats that LLMs can understand, such as natural language or structured JSON.
- **Pattern Detection:** LLMs identify trends and anomalies, such as unusual buy volumes or wallet behaviors.
- **Decision-Making:** Based on their training and provided tools, LLMs decide how to respond to the detected patterns.
- **Communication:** LLMs craft human-readable messages, summaries, or reports to notify users via preferred channels (e.g., newsletters, Twitter, Slack).

Here's how they fit into the broader agent graph and perform inference:

### Pretraining and Weights
LLMs are trained on vast datasets (usually, Web2 crawled data), enabling them to develop a broad understanding of natural language and reasoning.
Their pretrained weights encapsulate this knowledge, making them capable of answering complex questions, generalizing across domains, and interpreting structured or unstructured data. 

On the flipside they can only reliably answer questions based on knowledge they have & data (categories) they've seen. If the pre-trained model only includes Web2 data we either have to fine-tune, augment or inject additional data.
AlphaArc leverages popular commercial LLMs but expands their ability to analyze transaction data, detect patterns, and produce meaningful insights.

### Inference
In the context of AlphaArc, inference refers to the LLM's process of reasoning over inputs (e.g., queries or blockchain data).

During inference, the LLM:
        - **Interprets structured data** from the indexing pipeline (e.g., token metrics or wallet transactions).
        - **Applies reasoning** to identify trends or anomalies (e.g., detecting unusual token buy volume).
        - **Generates outputs** that are actionable, such as summaries, alerts, or predictions.

    **Example:** Given a query like "Which wallets are driving this token's buy volume today?", the LLM analyzes wallet activity data and synthesizes an answer.

### Context Window

**What is the Context Window?**

The context window refers to the maximum number of tokens (words, punctuation, or other textual units) an LLM can process in a single inference cycle. 
Modern LLMs typically support windows ranging from 2,048 tokens (basic models) to [128,000 tokens](https://platform.openai.com/docs/models#gpt-4o) or more (advanced models like GPT-4 Turbo).

**Challenges in Blockchain Applications:**

Blockchain data is inherently verbose. For instance, analyzing a day’s worth of Solana transactions can exceed the token limit of even the largest context windows.
Essential details can be buried within massive datasets, making it critical to prioritize and condense information.

### LLMs Inside the Agent Graph
Within the agent graph, LLMs act as dynamic nodes that perform multiple roles:
    - **Decision Nodes:** The LLM evaluates conditions and determines the next step in the workflow, such as whether to fetch more data or generate a report.
    - **Reasoning Nodes:** The LLM processes the data it receives from other nodes (e.g., query engine results) to extract insights or detect patterns.
    - **Output Nodes:** The LLM generates natural language outputs, translating complex analysis into user-friendly formats for notifications or reports.

### LLMs in Blockchain Agents
Unlike traditional agents, blockchain agents handle large, dynamic datasets. 

LLMs play a critical role in:
    - **Interpreting Transformed Data:** The indexing pipeline preprocesses raw blockchain data into formats LLMs can understand, such as JSON or tokenized text.
    - **Enabling Generalization:** By leveraging their pretrained knowledge, LLMs can make sense of blockchain data and identify high-level patterns (e.g., market trends, token anomalies).
    - **Driving Real-Time Decisions:** LLMs within the graph respond to live queries, ensuring blockchain agents remain responsive and context-aware.
    






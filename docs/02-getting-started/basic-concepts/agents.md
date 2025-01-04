---
sidebar_position: 1
---
# Agents

## 2.1.1 Agents
Agents are the backbone of AlphaArc, enabling AI-driven decision-making tailored for specific tasks. 

Here's how they work:

### Graph Concept
Agents operate conceptually as graphs, where:

- **Nodes** represent tasks, tools, or data sources (e.g., a query engine, a summarizer, or a notification channel).
- **Edges** represent the flow of data or control between nodes, determining the sequence of operations.
- **State** each graph execution creates a state that is passed between nodes in the graph as they execute, and each node updates this internal state with its return value after it executes.

[TODO] Detailed AlphaArc agent lifecycle


### Inference
At the core of an agent’s functionality is inference, driven by Large Language Models (LLMs):

1) An agent receives a **query** or task request as input (e.g., "Analyze token buy volume over the past hour").<br/>
2) It processes the input using a pretrained model, and predefined flow, queries data sources, and **synthesizes the results** and intermediate steps.
3) The LLM performs **reasoning** and generates actionable insights or recommendations.

### Workflow to Output 

Internally, agents follow these steps:<br/>
- **Task Decomposition:** Break down a complex query into smaller, manageable operations.
- **Query Execution:** Use tools (e.g., AlphaArc's query engine) to gather relevant data.
- **Data Interpretation:** Apply the LLM to analyze and interpret results, leveraging its reasoning and language capabilities.
- **Output Generation:** Produce human-readable outputs (e.g., notifications, reports) or structured data for further processing.

Agents are a flexible, modular systems capable of adapting to various tasks by connecting data sources, tools, and AI capabilities through this graph-based approach.


## 2.1.2 Blockchain Agents
While traditional agents focus on tasks like text summarization or text completion, blockchain agents add a new dimension by interacting with decentralized, high-throughput data streams such as Solana.

### Unique Characteristics of Blockchain Agents

    - **Dynamic Data Environment:** Blockchain agents deal with real-time, high-volume transaction data.
    - **Custom Queries:** Instead of querying static databases or raw transaction instructions, blockchain agents analyze indexed blockchain data—e.g., token transfers, swaps on decentralized exchanges, or market patterns.
    - **Advanced Tools:** These agents use specialized query engines and preprocessing pipelines to interpret raw blockchain data before applying AI inference. They use specialized tools like cryptographic wallets to sign transactions and submit them to network nodes.

### Data Generalization 
Blockchain data, when transformed into AI-ready formats, allows LLMs to generalize and detect patterns (e.g., identifying unusual wallet behaviors).
- **Natural Language Outputs:** LLMs enable blockchain agents to communicate findings in user-friendly formats, such as alerts, tweets, telegram messages or detailed reports.
- **Task Flexibility:** Blockchain agents can perform multiple roles—from monitoring DeFi metrics to generating market health newsletters.

AlphaArc’s agents are purpose-built for blockchain environments, powered by a robust indexing pipeline and query engine.
By combining graph-based agent mechanics with Solana’s Web3 data, AlphaArc enables LLMs to deliver actionable insights from otherwise inaccessible blockchain data.
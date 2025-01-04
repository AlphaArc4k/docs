---
sidebar_position: 1
---
# Overview

Intro, data sizes and infrastructure planning.

## About
AlphaArc provides a collection of curated datasets designed to bridge the gap between raw blockchain data and AI-driven analysis.
Datasets are designed to handle the massive scale of blockchain data, providing structured insights while maintaining flexibility for diverse use cases. Due to the high throughput of Solana, clients must be prepared to manage substantial data volumes and bandwidth requirements, especially when working with real-time or large-interval datasets.

Many fields are similar to those found in Solana RPC responses, but AlphaArc datasets go beyond this by offering enriched, transformed, and fully derived datasets optimized for AI workflows.

These datasets go through intense preprocessing and thoughtful structuring, making them a perfect match for Large Language Models (LLMs) and other AI tools. Instead of just cleaning up raw data, we refine it, strip away noise, and focus on high-value insights. Every dataset is purpose-built to handle complex data flows and transform it into something clean, actionable, and optimized for advanced analysis.

## Data format
AlphaArc leverages [Apache Parquet](https://parquet.apache.org/), a widely adopted "Big Data" storage format optimized for analytics. Parquet is designed to handle massive datasets efficiently, making it ideal for the scale and complexity of blockchain data.

- **Columnar Format:** Unlike traditional row-based storage, Parquet stores data in a columnar fashion. This structure improves query performance by allowing selective access to specific columns without needing to scan the entire dataset.
- **Row Groups:** Each Parquet file is divided into row groups, which partition the data into manageable subsets. This allows for parallel processing and efficient retrieval of only the rows relevant to a query.
- **Binary Storage:** Data in Parquet files is stored in a compact binary format, reducing file size and improving read/write performance.

By using Parquet, AlphaArc ensures that its datasets are both scalable and performant, enabling users to query and analyze data with minimal latency.

## Compression
AlphaArc datasets are compressed using [Meta's zstd (Zstandard)](https://github.com/facebook/zstd), a modern compression algorithm.

- **Effective Compression:** zstd reduces dataset size by compressing similar values within columns, such as timestamps or transaction data.
- **Fast Access:** Compressed data can be read without full decompression, allowing for faster data retrieval.
- **Resource Efficiency:** The combination of Parquet and zstd helps reduce storage and bandwidth requirements.

This approach ensures that large datasets remain manageable and accessible for analysis.

## Normalization
While normalized data structures are excellent for storage and maintenance in relational databases, they are not always ideal for high-performance processing tasks, especially in AI-driven workflows. 

A dataset is said to be in a specific Normal Form (NF) if it satisfies certain rules, starting with the First Normal Form (1NF) and progressing to higher levels such as 3NF or BCNF. For more details, see [Database Normalization on Wikipedia](https://en.wikipedia.org/wiki/Database_normalization).

AlphaArc takes a pragmatic approach, balancing:

- **Efficiency:**
    - Flattened structures minimize joins for the most common queries, allowing faster data retrieval.
    - Pre-computed aggregates (e.g., token metrics, program counts) reduce computation overhead.

- **Flexibility:**
    - Datasets are optimized for direct use in AI and analytics tasks, often at the cost of some redundancy.
    - When joins are necessary (e.g., linking tokens to their metadata or transactions to programs), the schemas are designed to make these joins straightforward.

- **Scalability:**
    - By prioritizing chunked and pre-aggregated datasets, AlphaArc ensures that even large-scale queries remain performant.

### Joins
:::warning
Custom joins are strongly discouraged. If your application requires a specific set of information, request a view or datset instead.
:::
Joins are discouraged but possible.
While most tasks can be completed using the standalone datasets, certain specialized cases might necessitate joins. 


For scenarios requiring joins, users should:
- Minimize the size of datasets involved (e.g., filter data before joining).
- Use efficient indexing and caching mechanisms.
- Avoid joins on high-frequency, real-time queries.

## Data size
Below is an example breakdown of dataset sizes for different types and time intervals. These sizes serve as guidelines to help clients plan their infrastructure and bandwidth needs effectively.

| **Dataset Type**   | **Interval**   | **Example Size**  | **Description**                                                                 |
|---------------------|----------------|-------------------|---------------------------------------------------------------------------------|
| **Blocks**          | 60 minutes    | 100 KB            | Includes details of all blocks produced within the interval                   |
| **Transactions**    | 60 minutes    | 1.4 GB            | Contains all transaction data, including signatures and involved accounts     |
| **Swaps**           | 60 minutes    | 100 MB             | Specific to token swaps across decentralized exchanges                        |
| **Fees**            | 60 minutes    | 150 MB             | Priority fees and compute units                               |
| **Programs**        | 60 minutes    | 250 MB            | Captures activity for deployed programs, including invocation counts          |
| **Tokens**          | 60 minutes    | 500 KB            | Token miniting  |
| **Sol transfers**          | 60 minutes    | 180 MB            | Sol transfers  |
| **Token transfers**          | 60 minutes    | 15 MB            | Token transfers  |

______

## Infrastructure Planning

### Bandwidth Requirements
High-frequency streams, such as 5-minute datasets, will require significantly more bandwidth due to increased request rates.
Clients processing multiple dataset types concurrently should plan for scalable network capacity.

### Storage Considerations
Historical data can grow rapidly, especially when storing multiple types or intervals. Efficient compression and chunking are recommended.

### Streaming vs. Batch Processing
Streaming is ideal for real-time monitoring and alerts, but batch processing can be more efficient for historical analysis or periodic insights.

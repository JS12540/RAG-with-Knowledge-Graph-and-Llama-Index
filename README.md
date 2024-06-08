# RAG-with-Knowledge-Graph-and-Llama-Index

### Technology Stack Used:

1. **LlamaIndex**:
   - LlamaIndex is an orchestration framework that simplifies the integration of private data with public data for building applications using Large Language Models (LLMs).
   - It provides tools for data ingestion, indexing, and querying, making it a versatile solution for generative AI needs.
   - Version used: llama-index 0.10.33

2. **Embedding Model**:
   - The Embedding Model is required to convert the text into a numerical representation of a piece of information for the provided text.
   - The representation captures the semantic meaning of what is being embedded, making it robust for many industry applications.
   - Model used: thenlper/gte-large

3. **LLM**:
   - The Large Language Model is required to generate a response based on the question and context provided.
   - Model used: Zephyr 7B beta

# Knowledge Graph Creation with Llama Index

This guide will walk you through creating a knowledge graph using Llama Index. The process involves reading a PDF file, converting it into a structured knowledge graph, storing the embeddings in a graph data repository, and retrieving relevant context to match user queries. The retrieved context is then provided to the LLM to generate responses.

## Steps

1. **Read a PDF file and convert it into a structured knowledge graph.**
2. **Store the embeddings in a graph data repository.**
3. **Retrieve relevant context matching the user query.**
4. **Provide the response to the LLM to generate a response.**


# Overview of Packages

## SimpleDirectoryReader
- **Purpose**: Reads unstructured data.
- **Usage**: Ideal for loading and processing unstructured datasets.

## ServiceContext
- **Purpose**: Supplies contextual data vital for orchestrating various services.
- **Note**: This package has been deprecated and replaced by `Settings`.

## KnowledgeGraphIndex
- **Purpose**: Required for both construction and manipulation of Knowledge Graphs.
- **Usage**: Essential for creating and managing structured knowledge representations.

## SimpleGraphStore
- **Purpose**: Serves as a straightforward repository for storing graph data.
- **Usage**: Useful for storing and retrieving graph-based information efficiently.

## HuggingFaceInferenceAPI
- **Purpose**: Module for leveraging Open-Source LLMs (Large Language Models).
- **Usage**: Integrates with Hugging Face's models for inference tasks.

# Construct the Knowledge Graph Index

Creating a Knowledge Graph usually involves specialized and complex tasks. However, by utilizing the Llama Index (LLM), the KnowledgeGraphIndex, and the GraphStore, we can facilitate the creation of a relatively effective Knowledge Graph from any data source supported by Llama Hub.

- **max_triplets_per_chunk** : it governs the number of relationship triplets processed per data chunk
- **include_embeddings** : toggles the inclusion of vector embeddings within the index for advanced analytics.

# Graph Visualization
- pyvis library is used for graphical representation of knowledge graph
- notebook=True secures graphs compatibility with Jupyter notebook
- cdn_resources=”in_line” specifies the in-line arrangement of resources
- directed=True designates graph as a directed entry

## Data Persistence
- Data Retention plays an instrumental role, particularly when your knowledge graph asnd associated index are intricate or have necessitated significant computational effort for their construction.
- By persisting the data we can effortlessly retrieve the data for future analysis without the need for a complete rebuild

```python
storage_context.persist()
```
## Reference Link
[Implement RAG with Knowledge Graph and Llama Index](https://medium.aiplanet.com/implement-rag-with-knowledge-graph-and-llama-index-6a3370e93cdd)

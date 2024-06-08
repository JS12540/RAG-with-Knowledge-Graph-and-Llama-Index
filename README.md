# RAG-with-Knowledge-Graph-and-Llama-Index

# Main Components of Knowledge Graph

Knowledge graphs are typically composed of two main components:

1. **Vertex/Node**: Represents entities or objects in the domain of knowledge. Each node corresponds to a unique entity and is identified by a unique identifier. For example, in a knowledge graph about the Chennai Kings, nodes could have values such as “Philadelphia Phillies” and “Major League Cricket.”

2. **Edge**: Represents the relationship between two nodes. For example, an edge “compete in” might connect the node for “Chennai Kings” to the node for “Major League Cricket.”

## Triplets in Knowledge Graph

A triplet is a basic unit of data in the graph. It consists of three parts:

1. **Subject**: The node that the triplet is about.

2. **Object**: The node that the relationship points to.

3. **Predicate**: The relationship between the subject and the object.

In the following triplet example, “Chennai Kings” is the subject, “compete in” is the predicate, and “Major League Cricket” is the object:

(Chennai Kings) — [compete in] —> (Major League Cricket)

A Knowledge Graph database can efficiently store and query complex graph data by storing triplets.


## Comparing Graph Databases and Vectored Databases

When comparing a graph database and a vectored database, there are several important questions to consider. Here are some key questions to explore:

1. **Nature of the Data and Relationships**:
   - What is the nature of the data and its relationships?
   - Does the data primarily consist of structured or unstructured information?
   - Are there complex relationships and dependencies between entities?

2. **Querying and Analysis Requirements**:
   - What are the specific requirements for querying and analysis?
   - Are efficient similarity searches and recommendations necessary?
   - Is there a need for complex graph traversals and relationship exploration?
   - Are semantic analysis and reasoning capabilities crucial?
   - Is low latency critical for real-time applications?
   - Are there multiple types of relationships and attributes that need to be captured?

3. **Query Languages, APIs, and Ecosystem Integrations**:
   - What are the available query languages, APIs, and ecosystem integrations?

In summary, vectored databases and knowledge graphs use different methodologies to store and represent data. While vectored databases are suitable for similarity-based operations, knowledge graphs are designed to capture and analyze complex relationships and dependencies. Choosing the right approach depends on the specific requirements and objectives of your project.

# Comparison Factors

## Data Structure:
- **Graph Database**: Built to store nodes and edges, excelling at mapping relationships which are treated as a first-class citizen.
- **Vector Database**: Stores data as numeric arrays.

## Data Retrieval and Analysis:
- **Graph Database**: Analyzes relationships between entities.
- **Vector Database**: Good at analyzing patterns.

## Query:
- **Graph Database**: Queries relationships between entities and complex networks.
- **Vector Database**: Efficient for similarity search or best match searches.

## Performance:
- **Graph Database / Knowledge Graph**: Great at processing queries involving relationships.
- **Vector Database**: Provides fast similarity searches.

## Storage

## Data Structure:
- **Graph Database**:
  - Utilizes nodes and edges to represent relationships.
  - Well-suited to analyze relationships between entities and complex networks.
- **Vector Database**:
  - Uses numeric arrays for data storage.
  - Ideal for similarity search and best match searches.

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

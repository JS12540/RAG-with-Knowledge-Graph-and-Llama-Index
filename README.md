# RAG-with-Knowledge-Graph-and-Llama-Index

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

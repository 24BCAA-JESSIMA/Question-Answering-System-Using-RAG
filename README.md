# Financial Document Question Answering using RAG

An AI-powered Question Answering system that uses
Retrieval-Augmented Generation (RAG) to retrieve relevant
information from financial documents and generate
context-based answers.

---

## Project Overview

Large financial reports contain a huge amount of information,
making it difficult and time-consuming to manually search
for specific details.

This project solves this problem by building a
**Retrieval-Augmented Generation (RAG) based Question
Answering system**.

The system uses **Apple Inc.'s 2020 financial report** as
the knowledge source. The document is processed, divided
into smaller chunks, converted into semantic embeddings,
and stored in a **FAISS vector store**.

When a user asks a question, the system retrieves the most
relevant document chunks and provides them as context to
**Llama 2 13B**, which generates the final answer.

---

## Problem Statement

Large financial documents contain extensive business and
financial information. Finding a specific answer manually
from these lengthy documents can be difficult and
time-consuming.

### Problem

> How can we efficiently retrieve relevant information from
> a large financial document and generate accurate,
> context-based answers to user questions?

This project addresses the problem using **RAG**, combining
semantic search with Large Language Model generation.

---

## Objectives

The main objective of this project is to develop an
AI-powered Question Answering system using RAG.

### Specific Objectives

- Load and process financial documents
- Split large documents into manageable text chunks
- Generate semantic embeddings for each chunk
- Store embeddings in a FAISS vector store
- Retrieve relevant information based on user queries
- Generate answers using Llama 2 13B
- Evaluate generated answers for relevance
- Evaluate whether answers are grounded in the retrieved
  context

---

## Business Context

Companies generate large amounts of financial and business
information through annual reports and Management Discussion
and Analysis (MDA) documents.

Manually searching these lengthy reports can take significant
time.

A RAG-based Question Answering system can help users quickly
find and understand relevant information using natural
language questions.

### Business Value

- Faster access to business information
- Reduces manual document searching
- Makes lengthy financial reports easier to understand
- Provides context-based answers
- Supports efficient information retrieval

---

## Dataset

The project uses **Apple Inc.'s 2020 financial report /
Management Discussion and Analysis (MDA)** as the knowledge
source.

The dataset contains information related to:

- Products and services
- Net sales
- Geographic segments
- Inventory
- Business performance
- Financial conditions
- Risks and market factors

### Document Processing

The financial document is divided into smaller text chunks
before generating embeddings.

| Parameter | Value |
|---|---:|
| Chunk Size | 2,000 characters |
| Chunk Overlap | 200 characters |
| Total Chunks | 715 |

---

## RAG Architecture

The overall workflow of the project is:

```text
                Financial Document
                        │
                        ▼
                 Load Document
                        │
                        ▼
                  Text Chunking
                        │
                        ▼
                BGE Embeddings
                        │
                        ▼
                FAISS Vector Store
                        │
                        │
                  User Question
                        │
                        ▼
              Semantic Retrieval
                        │
                        ▼
             Relevant Document Chunks
                        │
                        ▼
                  Llama 2 13B
                        │
                        ▼
                Generated Answer
                        │
                        ▼
           Relevance & Groundedness
                  Evaluation

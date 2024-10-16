Advanced Vector Search for RAG Systems
======================================

Basic Information
-----------------
This `project <https://github.com/SUNGOD3/AdvancedVectorSearch>`__, 
tentatively named "AdvancedVectorSearch", aims to develop and implement 
novel vector search methods for RAG (Retrieval Augmented Generation) systems.

The nature of LLM (Large Language Model) technology introduces unpredictability 
in LLM responses. Additionally, LLM training data is static and introduces 
a cut-off date on the knowledge it has. (e.g. Instagram's parent company is 
called Meta, but an LLM trained only on pre-2020 data would answer Facebook.)

RAG combines the power of LLM with information retrieval systems. It works by:

1. Retrieving relevant information from a knowledge base: This step involves 
   converting the user's query into a vector representation and then searching 
   the knowledge base for the most similar vectors.
2. Feeding this information to the LLM along with the user's query.
3. Having the LLM generate a response based on both the retrieved information 
   and its pre-trained knowledge.

Vector search is a crucial component in modern information retrieval systems, 
particularly in RAG applications. While FAISS (Facebook AI Similarity Search) 
is a well-established library for efficient similarity search, there's room for 
innovation in search methodologies.

.. note::

   The goal of this project will focus on vector search, similarity comparison 
   function, vector data storage, and does not include matrix calculations of LLM.

Problem to Solve
----------------
The primary challenges this project aims to address are:

1. Improving search speed beyond basic linear search, especially for 
   high-dimensional vector spaces common in RAG systems.
2. Developing new similarity metrics that may be more suitable for 
   specific RAG applications.
3. Creating a flexible, extensible framework that allows for easy 
   experimentation with different search algorithms and metrics.
4. Balancing speed, accuracy, and memory usage in vector search operations.

Prospective Users
-----------------
This project will benefit:

1. Researchers and developers working on RAG systems.
2. Data scientists and machine learning engineers dealing with large-scale 
   similarity search problems.
3. Information retrieval specialists looking for customizable vector 
   search solutions.
4. Anyone working with high-dimensional data requiring efficient similarity 
   search capabilities.
5. Graduate students who lack a graduation thesis.

System Architecture
-------------------
The AdvancedVectorSearch system will consist of the following components:

1. Dataset Module: For generating and managing large-scale, high-dimensional 
   vector datasets for testing and benchmarking.
2. Index Module: Implementing various similarity comparison functions and 
   indexing structures.
3. Search Module: Providing add and search functionalities with support for 
   different search algorithms.
4. Benchmark Module: For comparing the implemented methods against linear 
   search and potentially FAISS in terms of speed, accuracy, and memory usage.

Index Module
------------

The Index Module is responsible for implementing various similarity comparison 
functions and indexing structures. It supports basic operations for adding, 
searching, and removing vectors from the index. The basic index structure 
includes the following:

- **vector<float>** : Stores the vector data.
- **int** : Stores the vector dimension.
- **int** : Stores the number of vectors in the index.
- **string** : Unique identifier for each vector.

The module provides the following methods:

- **add(vector)** : Adds vectors to the index.
- **search(query_vector)** : Searches the index given a query vector.
- **remove(vector)** : Removes vectors from the index.

Supported Index Types
---------------------

The Index Module supports the following types of indices:

1. **Flat Index**: 
   A simple index that stores vectors in memory and performs an 
   exhaustive search.

2. **IVF (Inverted File) Index**: 
   An index that partitions the vector space into clusters for 
   faster search.

   This method provides a more efficient search process compared 
   to flat indices, especially for large-scale datasets.

The system will be implemented in C++ for core functionalities, with Python 
bindings for ease of use.

API Description
---------------

The AdvancedVectorSearch API will include:

1. Dataset Management
2. Index Operations
3. Search Operations
4. Benchmark

Engineering Infrastructure
--------------------------

- Version Control: Git, hosted on GitHub
- CI: GitHub Actions for automated testing and benchmarking

Schedule
--------

- Week 1: Set up project repository, basic infrastructure, and start on 
  dataset generation module.
- Week 2: Implement basic linear search as a baseline and develop the 
  benchmark module.
- Week 3: Research and implement the first advanced search algorithm.
- Week 4: Develop and integrate parallel processing capabilities for the 
  search algorithms.
- Week 5: Implement additional similarity metrics and corresponding search 
  algorithms.
- Week 6: Create Python bindings and ensure seamless integration with 
  Python environments.
- Week 7: Conduct comprehensive benchmarking and optimize performance.
- Week 8: Refine documentation, create usage examples, and prepare for 
  initial release.

Note: This time plan is generated by GPT-4o, and the actual work progress 
may vary.

References
----------

1. FAISS (Facebook AI Similarity Search): 
   https://github.com/facebookresearch/faiss
2. RAG: https://arxiv.org/abs/2005.11401
3. FAISS index structures: 
   https://faiss.ai/cpp_api/struct/structfaiss_1_1Index.html

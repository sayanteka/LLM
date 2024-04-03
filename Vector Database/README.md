Vector database: Stores embeddings/vectors in order to fetch queries based on semantic meaning  similarity search.

Features for embeddings are generated during back-propogation.

Widely used vector database: chroma, weaviate, redis, faiss, pinecone.

For LLM, Vector Database is a knowledgebase.

Pinecone's index like in our case the index name is "myindex"  associated with Pod.
Each pod has ram and storage.
Basic pod is p1(free) which can store upto 1 million vectors of 768 dim.

Chroma db is self-hosted but pinecone is managed.
The rough calculation for RAM requirement in chromadb for N vectors with dimension dim is N×dim×4 bytes.
Approximately, 1 GB of RAM can store around 300,000 768-dim vectors (Sentence Transformer) or 150,000 1536-dim vectors (OpenAI).

To store 2.5M OpenAI 1536-dim vectors, the memory requirements would be 2.5M vectors×1536 dimensions×4 bytes≈16 GB.
Therefore, to support the same load as the Pinecone S1 pod, you would need at least a 16 GB RAM machine for ChromaDB. Pricing for chromadb will be more compared to s1 pod.

For local testing/prototyping, we can go on using chromadb

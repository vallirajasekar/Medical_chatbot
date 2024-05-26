# Medical_chatbot

# Architecture Overview

## Medical Chatbot Implementation Using Custom Data

### Architecture

1. **Data Ingestion**  
   We start with the ingestion of PDF files, specifically medical books.

2. **Data Extraction**  
   After extracting the data/content from the PDFs, we create text chunks.

3. **Text Chunk Creation**  
   - **Corpus Creation:** In the context window, we have tokens, so we need to relate them.
   - We are using **Llama2** with a 4096 token limit.
   - Since our data exceeds 4096 tokens, we need different chunks.
     - **Chunk Size:** 200 tokens per chunk to avoid input problems.
     - **Chunk Overlap:** 20 tokens overlap between chunks (the second chunk will include 20 words from the first chunk).

4. **Embedding Component**  
   - Converts chunks to embeddings (vectors).
   - **Semantic Index:** Builds clusters where similar concepts (e.g., "king" and "queen") are in the same index.
   - **Knowledge Base:** Uses Pinecone for vector storage.

### Backend Components

1. **User Interaction Flow**  
   - **User Question:** The user asks a question.
   - **Query Embedding:** The question is converted into an embedding.
   - **Knowledge Base Search:** Finds the closest vector to the query.
   - **Llama2 Filtering:** Filters out the exact result.
   - **Response:** Sends the filtered result back to the user.

### Complete Architecture of the Medical Chatbot

![Medical Chatbot Architecture](path_to_architecture_diagram_image)

This architecture outlines the implementation process of our medical chatbot, ensuring efficient data processing and accurate responses.

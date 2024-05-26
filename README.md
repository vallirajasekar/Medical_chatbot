Here's the continuation of your README.md with the provided information:

```markdown
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



## Tech Stack Used

1. Python
2. Langchain -- Generative AI framework
3. Frontend/Webapp -- Flask
4. LLM- Meta llama 2
5. Vector DB - Pinecone

## Git Steps for the Project

```sh
git add .
git commit -m "Initial commit"
git push -u origin main
```

## Running the Project

### Creating the Environment

```sh
conda create -n mchatbot python==3.9 -y
```

### Activating the Environment

```sh
conda activate mchatbot
```

### Installing Requirements

```sh
pip install -r requirements.txt
```

Replace `path_to_architecture_diagram_image` in the architecture section with the actual path to your architecture diagram image, if available.
```

This README.md section now includes information about the tech stack used, Git steps for the project, and instructions for running the project. It's all set for you to copy and paste into your README.md file.
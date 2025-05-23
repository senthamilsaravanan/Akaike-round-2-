# 🧠 Local Document Q/A System using LLM (FLAN-T5)

This project demonstrates how to build a local Question-Answering (Q/A) system using a `.txt` document, sentence-transformer embeddings, FAISS for semantic search, and the FLAN-T5 large language model for natural language answers.

---
## Objective

Create an intelligent assistant that can read a document, understand its content, and answer user questions by retrieving relevant sections and generating responses using a local large language model.

 ##Technologies Used

| Tool/Library             | Purpose                              |
|--------------------------|--------------------------------------|
| `sentence-transformers`  | To generate embeddings for text chunks |
| `faiss-cpu`              | For fast vector similarity search     |
| `transformers`           | To load and run the FLAN-T5 model     |
| `ipywidgets`             | For user interaction and file upload  |
| `torch`                  | Backend for transformer models        |


 Step-by-Step Process

### 1. Install Required Libraries

Install all necessary Python packages:
2.  Upload Your Document
Use the ipywidgets.FileUpload widget to upload a .txt document manually within a Jupyter Notebook.

3. Read and Parse Document
Read the uploaded file using Python’s built-in methods, decode its content, and store it in a text variable.

4. ✂Split Document into Chunks
Divide the document into overlapping chunks using a custom function. This improves retrieval accuracy during similarity search.

5. Generate Embeddings
Use the all-MiniLM-L6-v2 model from Sentence Transformers to create vector embeddings for each chunk of text.

6.  Build FAISS Index
Add embeddings to a FAISS index for efficient similarity search and fast retrieval of relevant chunks.

7.  Load the FLAN-T5 LLM
Use the open-source google/flan-t5-base model from Hugging Face Transformers to generate answers from text.

8.  Ask Questions
Define a get_answer() function:

Embed the user's question

Use FAISS to retrieve top-k relevant chunks

Construct a prompt using these chunks

Generate and return the answer from FLAN-T5


####Credits
1.Hugging Face Transformers
2.Sentence Transformers

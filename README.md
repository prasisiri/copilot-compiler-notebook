# copilot-compiler-notebook
## Architecture Diagram
<img width="1234" alt="image" src="https://github.com/user-attachments/assets/00462f26-e3bd-4928-bc0a-62a28cb6f61b">


The diagram illustrates a workflow for processing and analyzing documents using AI technologies. Here's a breakdown of each component and their interactions:

## Document Loaders
- **PyPDFLoader & WebBaseLoader**: These components are responsible for loading documents from PDFs and web sources, respectively. They serve as the initial step in the data pipeline, providing raw text data for further processing.

## Text Processing
- **RecursiveCharacterTextSplitter**: This module splits the loaded text into manageable chunks. This is essential for handling large documents, ensuring that the text can be efficiently processed and embedded.

### Embeddings
- **OpenAIEmbeddings**: This component generates vector representations (embeddings) of the text chunks. These embeddings capture semantic information, making it easier to compare and search through the text data.

### Vector Store
- **FAISS**: The FAISS (Facebook AI Similarity Search) module stores the embeddings in a vector database. It enables fast similarity searches, allowing for efficient retrieval of relevant information based on query inputs.

#### Language Model
- **ChatOpenAI**: This element represents an AI language model used to generate responses or analyze text based on user queries. It interacts with the vector store to retrieve relevant data and produce meaningful outputs.

### Prompt Handling
- **PromptTemplate, RunnablePassthrough, StrOutputParser**: 
  - **PromptTemplate**: Defines how queries are structured before being sent to the language model.
  - **RunnablePassthrough**: Acts as a conduit, passing structured prompts to the language model.
  - **StrOutputParser**: Parses the output from the language model into a usable format for display or further processing.

### Flask App
- The Flask App serves as the interface between users and this entire system, handling incoming requests and delivering processed results back to users.

This design efficiently processes and analyzes documents by combining document loading, text processing, embedding generation, and AI-driven analysis within a cohesive workflow.

## Sequence Diagram
<img width="775" alt="image" src="https://github.com/user-attachments/assets/5cf245a5-7103-4dd9-b8ac-efe3a1d72a5b">



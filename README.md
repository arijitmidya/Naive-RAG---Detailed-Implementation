# Naive-RAG---Detailed-Implementation

Naive RAG : 

Naive RAG is a simplified approach to using LLMs in conjunction with document retrieval for improved information access and response generation. Naive RAG works in three basic steps:

Indexing: Data from formats like PDF or HTML is cleaned up and converted into plain text. This text is then divided into smaller parts (chunks) and turned into vector representations by passing the chunks into the embedding model to make it easier to find later.

Retrieval: When someone asks a question, the RAG system turns that question into vector embedding using the same method used in indexing. Then, it compares this vector to the vectors of the indexed text parts to find the k most similar chunks. These k most similar chunks are used in the next step as a context.

Generation: The system combines the retrieved text parts (context) with the original question to create a prompt. The language model uses this prompt to answer the question. Depending on the question, the model might use its own knowledge or focus on the information it found earlier.

![image](https://github.com/user-attachments/assets/329f9351-e030-411a-b5a2-588dc0fba59a)

Implementation : 

Step 1 : Install and import the necessary libraries

Step 2 : Data indexing : Upload the PDF file , apply chunking to break it into multiple chunks , create embeddings for the text chunk leveraging OpenAI Embedding model and store the chunks and embeddings in chroma vector store

Step 3 : Retrieval process : Specify a query , and perform similarity search on the chroma db for top 5 searches

Step 4 : Augment process : Define a prompt template to instruct the model on how to generate the response . I have created multiple versions of the prompt : 

a. Standard template

b. Response in German

c. Response in French

d. Response to a moajor corporation executive

e. Response to a technical user 

Step 5 : Generation process : We instantiate an openai model instance , pass the retrieved information and prompt to generate the response 


Note : Update the following things while running the code 

1. Replace the OpenAI key with your personal key

2. Update the Doc path with your specific pdf , you want to use for the RAG Q & A

3. Update the CHROMA_PATH pointing to where you have the chromadb

4. Play with different types of prompts like language , technical depth of response through workplace persona and response style through famous people's .

Happy coding :)



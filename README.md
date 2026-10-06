<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a RAG API with FastAPI

**Project Link:** [View Project](https://nextwork.ai/projects/99ec4595-3d7b-5584-a799-aafb9c373bbb)

**Author:** talari yashwanth  
**Email:** ft.yashwanth.talari@gmail.com

---

## Introducing Today's Project!

In this project, I'm going to... This will help me... I'm interested in this because...: RAG is the industry standard for building domain-specific AI assistants (such as querying internal company docs, medical records, or support tickets) without needing expensive model fine-tuning.

### Key tools and concepts

The key tools I used include... Key concepts I learnt include...The key tools used include FastAPI (to build the REST API), Uvicorn (to run the ASGI web server), ChromaDB (a vector database to store and perform semantic searches on text embeddings), and Ollama (to run local AI models, specifically nomic-embed-text for embeddings and qwen2.5:0.5b as the LLM).

### Challenges and wins

This project took me approximately... The most challenging part was...This project took me approximately 45 minutes to complete.

The most challenging part was ensuring the local environment dependencies were properly set up and making sure the Ollama server was connected to ChromaDB correctly so the embedding model could convert the document chunks into vectors without error.

## Performing RAG Manually

In this step, I'm going to... RAG stands for...RAG stands for Retrieval-Augmented Generation, a technique that improves AI accuracy by retrieving relevant data from custom or private documents, augmenting the prompt with that retrieved information, and generating a grounded response.

![Image](https://nextwork.ai/radiant_indigo_wise_pony/uploads/99ec4595-3d7b-5584-a799-aafb9c373bbb_v3j7x5b9)

### Understanding the three parts of RAG

I performed RAG manually by... The three parts are... I gave about myself, I asked about it, AI answered in a positive right answer

### Comparing the two AI models

The key difference I noticed is...The key difference lies in their purpose and architecture within the RAG pipeline:

nomic-embed-text (Embedding Model): This model does not generate conversational responses or chat with users. Instead, it converts text chunks and query strings into numerical vectors (768-dimensional embeddings) to enable fast semantic search in ChromaDB by capturing the meaning of text.

qwen2.5:0.5b (Chat/Language Model): This is a Large Language Model (LLM) designed to understand natural language and generate human-like text responses. It takes the retrieved text context from ChromaDB along with the user's question to produce a grounded answer.

## Building a Personal Knowledge Base

In this step, I'm going to... Embeddings are...You will write a profile.txt document with personal details, build a Python script (build_knowledge_base.py) that loads and splits the document into smaller text chunks, generate 768-dimensional vector embeddings for each chunk using nomic-embed-text, and store both the text and vectors locally in a persistent ChromaDB database.

![Image](https://nextwork.ai/radiant_indigo_wise_pony/uploads/99ec4595-3d7b-5584-a799-aafb9c373bbb_g3h7m2r5)

### Creating the profile document

I included information about...It gives the AI access to specific facts about your career goals, background, skills, and interests that were not part of its original pre-training data.

### How semantic search finds relevant chunks

When I ask a question, ChromaDB...  That means each chunk of text is represented as a list of 768 numbers. Each number captures a different aspect of the text's meaning, like topic, tone, or context.

## Creating the RAG API with FastAPI

In this step, I'm going to build an API that... I'll test it using...You will write a Python script (main.py) using FastAPI to create a web application with a /ask endpoint. When a user submits a question, this endpoint queries your ChromaDB collection to retrieve relevant context chunks from your profile, augments a prompt with that context, and uses Ollama's local chat model (qwen2.5:0.5b) to generate a grounded response.

![Image](https://nextwork.ai/radiant_indigo_wise_pony/uploads/99ec4595-3d7b-5584-a799-aafb9c373bbb_j5m1r8t2)

### How the /ask endpoint works

When a question comes in, my endpoint...Retrieval: It queries ChromaDB with the user's question to find and retrieve the most relevant text chunks (context) from your profile.txt document using semantic similarity search via nomic-embed-text.

Augmentation: It constructs an updated prompt that embeds the retrieved context alongside the user's original question, explicitly instructing the AI to base its response on that information.

Generation: It sends the augmented prompt to the local language model (qwen2.5:0.5b) via Ollama, which generates an accurate, grounded answer based on the provided context.

### Testing with Swagger UI

I tested my API by asking... The AI answered with... The context used was...The AI used ChromaDB to retrieve relevant context chunks from my profile.txt document (which contained details about my goal to become a cloud architect/DevOps engineer). It augmented the prompt with this retrieved context and passed it to the local qwen2.5:0.5b model, allowing the AI to generate a grounded, accurate response stating my exact career goals without hallucinating or making generic guesses.

## Extending to a Multi-User AI Directory

### Adding the POST /documents endpoint

### Verifying multi-user filtering

## Wrapping Up

I did this project today to learn how to... Another skill I want to learn is...I did this project today to learn how to build a local Retrieval-Augmented Generation (RAG) API using FastAPI, ChromaDB, and Ollama to give grounded AI answers from personal data. Another skill I want to learn is containerizing and deploying AI applications using Docker and Kubernetes.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/99ec4595-3d7b-5584-a799-aafb9c373bbb)*

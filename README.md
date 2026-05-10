### Smart Git Commit Message Pipeline:

An automated, context-aware commit message generator that uses Retrieval-Augmented Generation (RAG). 
By combining semantic search (MiniLM) and lexical search (TF-IDF) with the Llama 3 model, this pipeline identifies 
historical coding patterns to suggest high-quality, professional commit messages for your code changes.

## 🚀 Overview:

The pipeline works in four stages:

1. Data Loading: Pulls the commitpackft dataset from Hugging Face.
2. Indexing: Creates a searchable index of code diffs using TF-IDF and Semantic Embeddings.
3. Hybrid Retrieval: Finds the most similar historical commits to your current work.
4. Generation: Uses the Groq API to "few-shot" prompt Llama 3 to write a commit message based on that context.

## 🛠 Prerequisites:

Before running the pipeline, you will need:

1. Google Account: To run the project in Google Colab.

2. Groq API Key: - Go to the Groq Cloud Console (https://console.groq.com/home)
  - Sign up for a free account.
  - Navigate to API Keys and click Create API Key.
  - Copy this key immediately; you will need it for the notebook.

## 💻 Setup Instructions:
1. Open the Notebook
  - Upload the .ipynb file to your Google Colab (https://colab.research.google.com/) or open it directly this GitHub repository.

2. Configure Hardware Acceleration
  - For faster embedding generation, enable the GPU:
    1. Go to Runtime -> Change runtime type.
    2. Select T4 GPU (or any available GPU).
    3. Click Save.
   
3. Securely Add Your API Key
  - To keep your Groq key safe, use Colab’s "Secrets" manager:
    1. Click the Key icon (Secrets) in the left-hand sidebar.
    2. Click + Add new secret.
    3. Set the Name to: GROQ_API_KEY
    4. Paste your key into the Value field.
    5. Toggle the Notebook access switch to ON.


## 🛠 Troubleshooting:
- RateLimitError: If you are using the free Groq tier, you may hit a rate limit if you run many generations in a row. Wait 60 seconds and try again.

- KeyError: GROQ_API_KEY: Ensure you have toggled "Notebook access" to ON in the Colab Secrets tab.

- Memory Issues: If the notebook crashes, go to Runtime > Restart Session and ensure you are only loading the necessary subset of the dataset.




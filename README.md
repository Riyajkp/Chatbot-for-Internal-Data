# Chatbot-for-Internal-Data
Chatbot for Internal Data

langchain library, which is a Python library for building conversational AI applications. It is responsible for setting up the language model, processing PDF documents into a format that can be used for conversation retrieval, and handling user prompts to generate responses based on the processed documents.

# set up the environment
pip3 install virtualenv 
virtualenv my_env # create a virtual environment my_env
source my_env/bin/activate # activate my_env

# Install requirements:
set up the environment
git clone https://github.com/sinanazeri/build_own_chatbot_without_open_ai.git
mv build_own_chatbot_without_open_ai build_chatbot_for_your_data
cd build_chatbot_for_your_data
pip install -r requirements.txt



    Initialization init_llm():
        Setting environment variables: The environment variable for the HuggingFace API token is set.
        Loading the language model: The WatsonX language model is initialized with specified parameters.
        Loading embeddings: Embeddings are initialized using a pre-trained model.

    Document processing process_document(document_path):
    This function is responsible for processing a given PDF document.
        Loading the document: The document is loaded using PyPDFLoader.
        Splitting text: The document is split into smaller chunks using RecursiveCharacterTextSplitter.
        Creating embeddings database: An embeddings database is created from the text chunks using Chroma.
        Setting Up the RetrievalQA chain: A RetrievalQA chain is set up to facilitate the question-answering process. This chain uses the initialized language model and the embeddings database to answer questions based on the processed document.

    User prompt processing process_prompt(prompt):
    This function processes a user's prompt or question.
        Receiving user prompt: The system receives a user prompt (question).
        Querying the model: The model is queried using the retrieval chain, and it generates a response based on the processed document and previous chat history.
        Updating chat history: The chat history is updated with the new prompt and response.

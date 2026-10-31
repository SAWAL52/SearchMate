# AI QnA Chatbot

A simple question-and-answer chatbot built using Python, Streamlit, LangChain, and Ollama. The chatbot uses the Llama 3.2 (3B) model to answer questions and keeps track of previous messages during a conversation.

## Features

- Simple chat interface using Streamlit
- Answers questions using the Llama 3.2 (3B) model
- Maintains conversation history during the current session
- Uses LangChain to manage chat messages
- Runs locally using Ollama

## Technologies Used

- Python
- Streamlit
- LangChain
- LangChain Ollama
- Ollama
- Llama 3.2 (3B)

## Requirements

Before running the project, install the following:

- Python 3.10 or later
- Ollama

## Installation

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <your-project-folder>
```

Replace the repository URL and folder name with your own.

### 2. Create a Virtual Environment

For macOS and Linux:

```bash
python3 -m venv env
source env/bin/activate
```

For Windows:

```bash
python -m venv env
env\Scripts\activate
```

### 3. Install the Required Packages

```bash
pip install streamlit langchain-ollama python-dotenv
```

### 4. Download the Model

Install Ollama and download the model by running:

```bash
ollama pull llama3.2:3b
```

Make sure Ollama is running before starting the chatbot.

### 5. Run the Application

Run the following command from the project directory:

```bash
streamlit run app.py
```

The application will open in your browser. If it does not open automatically, visit:

http://localhost:8501

## Project Structure

```text
AI-QnA-Chatbot/
├── app.py
├── README.md
└── .gitignore
```

## How It Works

The application takes questions through the Streamlit chat interface and sends them to the Llama 3.2 model through Ollama.

It stores user messages and chatbot responses in Streamlit session state. Before generating a new response, the previous messages are converted into LangChain message objects and passed to the model. This allows the chatbot to use the conversation history when answering follow-up questions.

The conversation remains available during the active session but is not saved permanently.

## Limitations

- Ollama must be installed and running locally.
- The Llama 3.2 (3B) model must be downloaded before use.
- Response speed depends on the computer's hardware.
- The chatbot does not store conversations after the session ends.
- Responses may not always be accurate.

## Future Improvements

- Add an option to clear the conversation.
- Display responses as they are generated.
- Allow users to select different models.
- Save chat history for later use.

## License

This project was developed for learning and practice purposes.
# Google Search AI Agent

A web-based chatbot built with Streamlit, LangChain, Groq, and Google Serper. The application uses Groq's `openai/gpt-oss-20b` model to generate responses and Google Search to retrieve information when needed. It also maintains conversation context during a chat session.

## Features

- Chat interface built with Streamlit.
- Integration with Groq for language model responses.
- Google Search integration through Serper API.
- Automatic tool selection for search queries.
- Streaming responses.
- Conversation memory using LangGraph.
- Response time measurement.
- Option to clear the conversation.

## Technologies

- Python
- Streamlit
- LangChain
- LangChain Groq
- LangChain Community
- LangGraph
- Google Serper API
- Groq API

## Requirements

- Python 3.10 or later
- Groq API key
- Serper API key

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/SAWAL52/Simple_AI_ChatBot.git
cd Simple_AI_ChatBot
```

### 2. Create and activate a virtual environment

```bash
python3 -m venv env
source env/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the project root directory and add your API keys:

```env
GROQ_API_KEY=your_groq_api_key
SERPER_API_KEY=your_serper_api_key
```

API keys can be obtained from:

- [Groq Console](https://console.groq.com/)
- [Serper](https://serper.dev/)

### 5. Run the application

```bash
streamlit run app.py
```

The application will be available at `http://localhost:8501`.

## How It Works

1. The user enters a question through the Streamlit interface.
2. The question is passed to the LangChain agent.
3. The agent determines whether external information is required.
4. If a search is needed, it uses Google Serper to retrieve relevant results.
5. Groq generates a response based on the available information.
6. LangGraph maintains conversation context using a thread ID.
7. The response is displayed incrementally, along with the response time.

## Project Structure

```text
Simple_AI_ChatBot/
├── app.py
├── README.md
├── requirements.txt
├── .env.example
└── .gitignore
```

## Limitations

- An active internet connection is required.
- Valid Groq and Serper API keys are required.
- Search functionality depends on Serper API availability.
- Response time varies depending on network conditions, search operations, and model processing.
- Conversation memory is stored in memory and is not retained after the application process restarts.
- Generated responses may contain inaccurate information.

## Future Improvements

- Display source links for search results.
- Support additional language models.
- Allow users to export conversations.
- Implement persistent conversation storage.
- Improve error handling and search result presentation.

## License

This project is intended for learning and development purposes.
# SearchMate

SearchMate is an AI-powered conversational assistant built using Python, Streamlit, LangChain, Groq, and LangGraph. It integrates a Groq-hosted large language model with Google Search through the Serper API, allowing the agent to retrieve external information when needed and generate responses based on the available context.

The application also implements conversational memory, real-time response streaming, and Streamlit session state management to provide an interactive chat experience.

## Features

- **LLM Integration with Groq:** Uses Groq to run the `openai/gpt-oss-20b` language model.
- **Google Search Integration:** Uses the Serper API through LangChain's GoogleSerperAPIWrapper to retrieve relevant web information.
- **Agent Creation with LangChain:** Implements an agent using `create_agent` that can decide when to invoke available tools.
- **Conversational Memory:** Uses LangGraph's `MemorySaver` checkpointer to maintain conversation context across interactions.
- **Real-Time Response Streaming:** Streams generated responses incrementally instead of waiting for the complete response.
- **Streamlit Interface:** Provides an interactive chat interface with separate user and assistant messages.
- **Session State Management:** Uses Streamlit session state to maintain chat history and manage conversation thread IDs.
- **Response Time Measurement:** Measures and displays the time taken to generate each response.
- **Chat Management:** Includes a Clear Chat feature to reset the conversation and start a new session.
- **Environment Variable Management:** Uses `python-dotenv` to load API credentials securely from a `.env` file.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Streamlit | Chat interface and session management |
| LangChain | Agent creation and tool integration |
| LangChain Groq | Groq LLM integration |
| LangChain Community | Google Serper search wrapper |
| LangGraph | Conversational memory and checkpointing |
| Groq | LLM inference |
| Google Serper | Web search API |
| python-dotenv | Environment variable management |

## Requirements

- Python 3.10 or later
- Groq API key
- Serper API key

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/SAWAL52/SearchMate.git
cd SearchMate
```

### 2. Create and activate a virtual environment

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

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root directory and add your API credentials:

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

The application will be available at:

`http://localhost:8501`

## How It Works

1. The user submits a question through the Streamlit chat interface.
2. Streamlit session state manages the displayed conversation history and the current thread ID.
3. The question is passed to the LangChain agent.
4. The agent processes the question using the Groq-hosted language model.
5. When external information is required, the agent invokes the Google Search tool through the Serper API.
6. The retrieved search results are passed back to the agent for response generation.
7. LangGraph's MemorySaver maintains conversation context using the thread ID.
8. The response is streamed incrementally to the Streamlit interface.
9. The application measures and displays the response time.

## Project Structure

```text
SearchMate/
├── app.py
├── README.md
├── requirements.txt
├── .env.example
└── .gitignore
```

## Limitations

- An active internet connection is required.
- Valid Groq and Serper API credentials are required.
- Search functionality depends on Serper API availability and usage limits.
- Response time varies depending on network conditions, search operations, and model processing.
- Conversational memory is maintained in memory and is not permanently stored. It is lost when the application process restarts.
- Generated responses may contain inaccurate or incomplete information.

## Future Improvements

- Display source links and references for retrieved search results.
- Support multiple LLM providers and models.
- Add persistent conversation storage.
- Allow users to export chat conversations.
- Improve search result presentation.
- Add configurable model parameters and agent settings.

## License

This project is intended for learning and development purposes.
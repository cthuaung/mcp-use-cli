# MCP Chat CLI

A simple interactive chat application using MCP (Model Context Protocol) that allows AI to access tools like web browsing.

## Features

- Interactive command-line chat interface
- Web browsing capability through Playwright MCP
- Conversation memory to maintain context
- Support for OpenAI and Groq models

## Prerequisites

- Python 3.11+
- uv package manager
- API keys for LLM providers (OpenAI/Groq)

## Installation

1. Clone this repository:
```bash
git clone https://github.com/cthuaung/mcpdemohttps://github.com/cthuaung/mcp-use-cli.git
cd mcp-use-cli
```

2. Set up a virtual environment with uv:
```bash
uv init
uv venv
```

3. Install dependencies using uv:
```bash
uv add python-dotenv langchain-groq langchain-openai mcp-use
```

4. Create a `.env` file with your API keys:
```
OPENAI_API_KEY=your_openai_api_key
GROQ_API_KEY=your_groq_api_key
```

5. Create a `browser_mcp.json` configuration file:
```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"],
      "env": {
        "DISPLAY": ":1"
      }
    }
  }
}
```

## Usage

Run the application:

```bash
uv run app.py
```

### Chat Commands

- Type your messages normally to chat with the AI
- Type `exit` or `quit` to end the conversation
- Type `clear` to clear the conversation history

## How It Works

This application uses the MCP-Use library to create an agent that can access tools through the Model Context Protocol. The agent uses LangChain and supports multiple LLM providers like OpenAI and Groq.

The main features include:
- Built-in conversation memory for contextual interactions
- Web browsing capabilities through Playwright MCP
- Simple command-line interface for easy interaction

## Customization

You can modify the LLM model by uncommenting and configuring different models in the `app.py` file:

```python
# Choose your preferred model
llm = ChatOpenAI(model="gpt-4o")
# llm = ChatGroq(model="llama-3.3-70b-versatile")
```

## License

MIT

## Credits

This project uses the [MCP-Use](https://github.com/pietrozullo/mcp-use) library by Pietro Zullo.

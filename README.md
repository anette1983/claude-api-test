# Claude API Test

Small Jupyter notebooks for learning the Anthropic Python SDK and building a basic multi-turn chatbot.

## Project Structure

- `multi_turn_chat_example.ipynb` - a simple example that sends an initial prompt, stores Claude's reply, and sends a follow-up message with conversation history.
- `chatbot.ipynb` - an interactive chatbot loop that keeps the message history, skips empty input, handles API errors, and exits when you type `quit`.
- `.env` - local environment variables such as `ANTHROPIC_API_KEY`.
- `.venv/` - local Python virtual environment.

## Requirements

- Python 3.11+
- An Anthropic API key

## Setup

1. Create and activate a virtual environment.
2. Install dependencies:

```bash
pip install anthropic python-dotenv
```

3. Create a `.env` file in the project root:

```env
ANTHROPIC_API_KEY=your_api_key_here
```

## How To Use

Open either notebook in VS Code or Jupyter and run the cells from top to bottom.

### `multi_turn_chat_example.ipynb`

This notebook shows the basic message flow:

- start with an empty `messages` list
- add a user message
- call Claude
- add the assistant reply back into the list
- send a follow-up message with full context

### `chatbot.ipynb`

This notebook turns the same helper functions into a looped chatbot:

- prompts for user input
- stores each user message
- sends the full message history to Claude
- stores Claude's reply
- prints the reply
- exits when you type `quit`

## Notes

- `.env` and `.venv/` are ignored by Git and should stay local.
- If you press Enter on an empty line in the chatbot, it asks you to type something instead of sending an invalid request.
- If the API request fails, the notebook prints the error and keeps the conversation history in a valid state.

# Smart Shop Assistant

A small Python chatbot that answers general questions and looks up prices for shop items. It uses OpenAI tool calling to decide when to run a local price lookup, and Gradio to provide a web chat interface.

## Features

- Answers conversational questions with `gpt-4o-mini`.
- Looks up prices for shoes, hats, bags, shorts, and pants using a Python dictionary.
- Provides both a command-line example and a Gradio chat app.

## Requirements

- Python 3.9 or newer
- An OpenAI API key

## Setup

1. Clone or download this project, then open a terminal in its folder.
2. Create and activate a virtual environment (recommended):

   ```bash
   python -m venv .venv
   source .venv/bin/activate     # macOS/Linux
   # .venv\Scripts\activate    # Windows PowerShell
   ```

3. Install the dependencies:

   ```bash
   pip install openai python-dotenv gradio
   ```

4. Create a `.env` file in the project folder and add your API key:

   ```env
   OPENAI_API_KEY=your_api_key_here
   ```

   Keep the `.env` file private; it is excluded from Git.

## Run the chat app

```bash
python app.py
```

This starts the Gradio interface. `app.py` currently launches with `share=True`, which creates a publicly accessible Gradio share link. Anyone with that link may be able to access the running app while it is available. Remove `share=True` in `app.py` to run it locally only.

## Run the command-line examples

```bash
python agent.py
```

The script asks the assistant about a shoe price and then sends a general greeting.

## Price list

Prices are stored in the `PRICES` dictionary in `agent.py` and can be edited there:

| Item | Price |
| --- | ---: |
| Shoes | ₹799 |
| Hat | ₹399 |
| Bag | ₹1,420 |
| Shorts | ₹1,299 |
| Pants | ₹1,699 |

For an item that is not in the dictionary, the lookup returns `unknown`.

## Project files

- `agent.py` — OpenAI client, price lookup tool, and agent loop.
- `app.py` — Gradio chat interface.
- `.env` — Local API key configuration (not committed to Git).

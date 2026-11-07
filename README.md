# AI Teaching Assistant

A lightweight Streamlit web app that answers questions in a clear, structured way using an AI model provider. The app is designed to feel like a simple teaching assistant: ask a question, get a direct answer, and keep the response complete instead of cutting off mid-sentence.

## Features

- Simple question-and-answer interface built with Streamlit
- Clear numbered responses for easier reading
- Built-in retry logic to continue incomplete answers
- Provider abstraction for switching between Groq and Hugging Face-based generation
- Easy setup with a Python virtual environment and `.env` file

## Tech Stack

- Python
- Streamlit
- Groq/OpenAI-compatible API client
- Hugging Face support (optional)
- python-dotenv

## Project Structure

```text
AIprompting-web/
├── main.py
├── groq.py
├── config.py
├── requirements.txt
├── .env.example (optional, add as needed)
└── README.md
```

## How it works

- `main.py` creates the Streamlit UI and asks the model for an answer.
- `groq.py` handles model calls to Groq using the OpenAI-compatible client.
- `config.py` loads environment variables from a `.env` file.
- The app checks whether the model output looks incomplete and asks the model to continue cleanly.

## Quick Start

1. Clone the repository:

```bash
git clone https://github.com/Harper-16/AIprompting-web.git
cd AIprompting-web
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

On Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Add your API key in a `.env` file:

```env
GROQ_API_KEY=your_groq_api_key_here
```

5. Run the app:

```bash
streamlit run main.py
```

6. Open the local Streamlit URL in your browser and start asking questions.

## Provider Setup

The app currently uses Groq by default.

In `main.py`, the app imports the response generator from `groq.py`:

```python
from groq import generate_response
```

If you want to switch providers in the future, update the import line and the relevant provider module.

## Example

```text
Question: Explain the difference between a list and a tuple in Python.

Answer:
1. Lists are mutable, meaning you can change their contents after creation.
2. Tuples are immutable, so they cannot be changed once created.
3. Lists use square brackets [] while tuples use parentheses ().
```

## Notes

- The app expects a valid API key to be available in your environment.
- If the model returns a response that appears cut off, the app attempts to finish it automatically.
- You may want to customize the prompt style or add more model providers later.

## License

This project currently does not include a license file. If you want to publish it publicly, consider adding an open-source license such as MIT.

## Author

Harper-16

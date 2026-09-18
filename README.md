# llm-lab

My practice of LLM Engineering: small experiments calling frontier LLM APIs from Python.

## Contents

| File | What it does |
|------|--------------|
| `day1.py` | First lab: calls the OpenAI Chat Completions API, then builds a website summarizer using system and user prompts. Also includes a stock-summary exercise that uses Yahoo Finance. |
| `scraper.py` | Helpers that use `requests` and BeautifulSoup to fetch a page's title and text (truncated to 2,000 characters) and its links. |

## Setup

Requires Python 3.10+ and an OpenAI API key.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Create a `.env` file in the project root:

```
OPENAI_API_KEY=sk-proj-...
```

`.env` is gitignored, so don't commit your key.

## Running

`day1.py` was converted from a Jupyter notebook and uses `IPython.display`, so it works best when run cell by cell in Jupyter or VS Code's interactive window:

```bash
python day1.py
```

## Notes

- The scraper only handles server-rendered HTML. Pages that are rendered with JavaScript, or that block bots (and return 403), won't return useful content.
- Models used: `gpt-5-nano`, `gpt-4.1-nano`, `gpt-4.1-mini`.

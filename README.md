# AGENT-EXAMPLE

A collection of Python scripts for web scraping, data processing, and Slack bot functionality.

## Setup

This project uses [uv](https://github.com/astral-sh/uv) for fast Python package management.

### Prerequisites

- Python 3.8 or higher
- uv (install with `curl -LsSf https://astral.sh/uv/install.sh | sh`)

### Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   uv sync
   ```
3. Activate the virtual environment:
   ```bash
   source .venv/bin/activate
   ```

## Project Components

### Web Scraping (`scrawler.py`)
Scrapes investment data from startuprecipe.co.kr and saves to CSV files.

### Data Processing (`merge.py`)
Merges multiple CSV files into a single dataset.

### Slack Bot (`bot/slackBot/app.py`)
A Slack bot that uses LangChain and OpenAI to draft email replies.

### ArXiv Search (`arxiv.py`)
Searches for papers on arXiv.

## Slack Bot Setup

To set up the Slack bot functionality:

1. Create a Slack app at https://api.slack.com/apps
2. Add the following environment variables to a `.env` file:
   ```
   SLACK_BOT_TOKEN=xoxb-your-bot-token
   SLACK_SIGNING_SECRET=your-signing-secret
   SLACK_BOT_USER_ID=your-bot-user-id
   OPENAI_API_KEY=your-openai-api-key
   ```
3. Run the bot:
   ```bash
   uv run python bot/slackBot/app.py
   ```

## Usage

Run any script with uv:
```bash
uv run python scrawler.py
uv run python merge.py
uv run python arxiv.py "search term"
```
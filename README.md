# TDS Data Analyst Agent

AI-driven data analyst that can answer complex questions by analyzing data from various sources. This agent can scrape websites, process uploaded files (like CSV), and execute SQL queries on remote datasets.

---

## Features

- **Multi-Modal Data Analysis**: Seamlessly handle three types of data analysis tasks:
  - **Web Scraping**: Scrapes data from a provided URL.
  - **File Analysis**: Analyzes data from uploaded files (e.g., `.csv`, `.parquet`).
  - **Remote Data Querying**: Executes SQL queries (such as DuckDB) on remote datasets.
- **AI-Powered Code Generation**: Utilizes OpenAI's `gpt-4o` to dynamically generate Python scripts for analysis.
- **Secure Execution Environment**: Runs generated code in an isolated, safe environment.
- **Integrated Web Interface**: Simple frontend for uploading files and submitting queries.
- **Deployment Ready**: Comes with a pre-configured Dockerfile—ideal for Render.

---

## Live Demo

Try it live:  
**[https://tds-data-analyst-agent-1.onrender.com/](https://tds-data-analyst-agent-6s1r.onrender.com/)**

---

## How It Works

1. **FastAPI Backend**: Receives your natural language query and any uploaded files.
2. **OpenAI Integration**: Sends your query to `gpt-4o` for AI-generated Python code.
3. **Secure Code Execution**: Executes code in isolation for safety.
4. **JSON Output**: Returns analysis results in a clean, structured format.

---

## Getting Started

### Prerequisites

- Python >= 3.10
- Docker Desktop (ensure it's running)

### Installation

```
git clone https://github.com/Anvi-a1/tds_data_analyst_agent.git
cd tds_data_analyst_agent
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Configuration

1. Create a `.env` file in the root of your project.
2. Add your OpenAI API key:

```
OPENAI_API_KEY="your-secret-api-key"
```

---

### Running Locally

```
uvicorn app:app --reload
```

Then, open your browser and go to:  
**http://127.0.0.1:8000**

---

## Usage

Use the web interface to upload a `questions.txt` file and any optional data files.

### Query Types

#### Web Scraping

```
Scrape the list of highest-grossing films from Wikipedia at:
https://en.wikipedia.org/wiki/List_of_highest-grossing_films
and create a plot of Rank vs. Peak.
```

#### File Analysis

```
Analyze sample-sales.csv and return the total sales and the top region by sales.
(Requires upload of sample-sales.csv)
```

#### Remote Data Querying

```
SELECT court, COUNT(*) 
FROM read_parquet('s3://...')
GROUP BY court;
```

---

## Project Structure

```
├── .env                # Environment Variables
├── app.py              # The main FastAPI application
├── Dockerfile          # Deployment container instructions
├── requirements.txt    # Python dependencies
└── README.md           # This file
```

---

# TL;DR News Digest 📰

An automated Python tool that scrapes top news stories (currently from Fox News), summarizes them using ChatGPT, and displays clean, Markdown-formatted digests. Built in a Jupyter notebook as part of an LLM Engineering project.

---

## 📦 Project Structure

tldr-news-digest/
├── .gitignore
├── notebooks/
│ └── tldr_news.ipynb # Main notebook: fetches, summarizes, and renders top stories
├── src/ # [Optionally for future modular scripts]
├── .env # Contains OPENAI_API_KEY (not checked into GitHub)
└── README.md

---

## 🚀 Features

- **Auto-fetch headlines** from Fox News
- **Scrape article content** via `requests` + BeautifulSoup  
- **Summarize with GPT-3.5-turbo**, formatted in Markdown  
- **Displays summaries** directly in Jupyter for easy reading

---

## 🔧 Setup & Usage

1. **Clone the repo**  

   git clone https://github.com/dennisbrody/tldr-news-digest.git
   cd tldr-news-digest

Install dependencies

pip install -r requirements.txt
If requirements.txt doesn’t exist yet, install manually:

pip install requests beautifulsoup4 python-dotenv openai
Create a .env file (in the repo root) containing:

OPENAI_API_KEY=sk-...
Run the notebook

Open notebooks/tldr_news.ipynb in Jupyter or VS Code

Restart the kernel and run all cells

Watch it fetch the top stories and display Markdown summaries

🧭 How It Works
get_top_fox_urls(limit=…) scrapes the homepage for a set number of news URLs.

summarize_url(url):

Extracts content via fetch_article(url)

Sends it to ChatGPT with summarize_text(text)

Returns a structured, Markdown-friendly summary

Summaries render nicely in Jupyter thanks to IPython.display.Markdown

🛠️ Next Steps (Stretch Goals)
Add support for RSS feeds or other news sites

Export summaries to .md, PDF, or email digests

Refactor into .py modules under src/

Build a lightweight UI with Streamlit or Flask

Add sentiment/keyword analysis, and categorize by topic

📚 Learnings So Far
Building a clean end-to-end pipeline: web scraping → LLM processing → formatted output

Using environment variables for secure API access

Rendering Jupyter output with Markdown for readability

Working with openai client version 1.x and debugging API schema changes

📬 Get Involved
If you find this tool helpful or want to expand it:

Fork the repo

Submit PRs with improvements

Open issues to share ideas or needs

Author: Brody Dennis
(Building portfolio-ready LLM projects — one notebook at a time.)


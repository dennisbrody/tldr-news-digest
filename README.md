# 📰 TL;DR News Digest

An automated Python tool that scrapes top news stories (currently from Fox News), summarizes them using ChatGPT (GPT-3.5), and displays clean, Markdown-formatted digests right inside a Jupyter notebook.

Built as part of my LLM Engineering learning journey — with plans to evolve it into a powerful AI-powered news summarization tool.

---

## 📦 Project Structure

```
tldr-news-digest/
├── .gitignore
├── .env                  # Contains OPENAI_API_KEY (NOT pushed to GitHub)
├── notebooks/
│   └── tldr_news.ipynb   # Main notebook with all functionality
└── README.md
```

---

## 🚀 Features

- ✅ Automatically pulls top articles from [foxnews.com](https://www.foxnews.com/)
- ✅ Extracts full article content using BeautifulSoup
- ✅ Summarizes each story using the OpenAI GPT-3.5-turbo model
- ✅ Displays output in clean, readable Markdown format inside the notebook
- ✅ Built entirely in Jupyter Notebook for transparency and experimentation

---

## 🔧 Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/dennisbrody/tldr-news-digest.git
cd tldr-news-digest
```

### 2. Install Dependencies

Create a virtual environment if you'd like, then install:

```bash
pip install requests beautifulsoup4 python-dotenv openai
```

### 3. Set Up Environment Variable

Create a `.env` file in the root of the repo:

```
OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

> ❗ **Important:** Never share or commit your API key!

### 4. Run the Notebook

Open the notebook:

```
notebooks/tldr_news.ipynb
```

Then restart the kernel and run all cells. You'll see:
- Top Fox News URLs
- Cleanly formatted summaries

---

## 🧠 How It Works

1. `get_top_fox_urls()` scrapes the homepage for the latest top stories.
2. `fetch_article()` pulls the text from each article.
3. `summarize_text()` sends the content to OpenAI and asks for a Markdown summary.
4. `summarize_url()` combines the above and renders the result.

---

## 🛠️ Next Features (Stretch Goals)

- ⏩ Pull from RSS feeds or multiple news sites (e.g., CNN, BBC, NYT)
- 🗂️ Group summaries by category (World, Politics, Tech)
- 📨 Export summaries to `.md`, `.pdf`, or daily email digest
- 🌐 Build a web app front-end using Streamlit
- 💬 Add sentiment or keyword analysis

---

## 📚 Skills Demonstrated

- Python scripting in Jupyter notebooks
- Web scraping with `requests` and `BeautifulSoup`
- OpenAI GPT-3.5 API integration using latest SDK (`openai >=1.0`)
- Secure API usage with `.env` + `python-dotenv`
- Markdown rendering inside Jupyter via `IPython.display.Markdown`
- GitHub version control and project publishing

---

## 👋 About

Created by **Brody Dennis**  
Currently learning LLM engineering, prompt design, and AI agent development.

> 🔥 “Real projects > tutorial loops.”  
> This is one of many experiments I’m using to build and showcase real-world AI applications.

---

## 🤝 Contributions Welcome

Feel free to fork this project and build on it. If you have improvements (multi-site support, better summarization prompts, output formatting), open a PR or issue!
=======
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

Author: Dennis Brody
(Building portfolio-ready LLM projects — one notebook at a time.)


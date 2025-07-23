
# 📧 Cold Email Generator using LangChain + Groq + Streamlit

This is a web-based application that scrapes job descriptions from company career pages, extracts structured job data using LLMs (LLaMA via Groq), and generates personalized cold emails with portfolio links from your projects.

---

## 🚀 Features

- 🌐 Extract job details from any job post URL
- 🤖 Uses LLaMA (via GroqCloud) for structured extraction and email generation
- 🧠 Matches job skills with your portfolio using ChromaDB
- 📧 Auto-generates cold emails tailored to each job
- 🧼 Cleans messy scraped content for better LLM understanding
- 🖥️ Streamlit-based web interface



## 🧰 Requirements

Install required Python packages:

```bash
pip install streamlit langchain langchain-community langchain-groq chromadb pandas python-dotenv beautifulsoup4
````

---

## 🔑 Setup `.env`

Create a `.env` file and add your Groq API key:

```bash
GROQ_API_KEY='your-groq-api-key-here'
```

---

## 🧪 How to Run

```bash
streamlit run main.py
```

---

## 🧠 How It Works

1. User pastes a job post URL.
2. `WebBaseLoader` scrapes and cleans the page.
3. LangChain + Groq LLaMA extracts:

   * `role`, `experience`, `skills`, `description`
4. Matches `skills` with projects in `my_portfolio.csv` using ChromaDB.
5. LangChain generates a cold email based on job + matching links.

---

## 📊 Portfolio CSV Format

`app/resource/my_portfolio.csv` should look like:

| Techstack              | Links                                                |
| ---------------------- | ---------------------------------------------------- |
| Python, LLM, LangChain | [https://yourproject1.com](https://yourproject1.com) |
| JavaScript, React      | [https://yourproject2.com](https://yourproject2.com) |

---

## 🧩 Models & Tools Used

* 🧠 **Groq LLaMA 3.1/4** (`meta-llama/llama-4-scout-17b-16e-instruct`)
* 🦜 **LangChain** for prompt chaining & parsing
* 🧠 **ChromaDB** for portfolio similarity matching
* 🧹 `re` module for text cleaning
* 🧾 `PromptTemplate`, `JsonOutputParser` for accurate LLM results

---

## 👨‍💻 Author

Built by **Kreshnaa Maddi**
Business Development Executive @ XYZ
AI + Automation Enthusiast

---

## 📬 Sample Output


Subject: Partnership Opportunity - AI Consulting Support

Hi [Hiring Manager],

I'm Kreshnaa, BDE at XYZ, a company specialized in AI and software automation. I noticed you're hiring for a "Software Engineer III, Google Cloud" role requiring skills like...

👉 Check similar work we've delivered:
- https://yourproject1.com
- https://yourproject2.com



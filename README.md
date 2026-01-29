# 📰 TL;DR News Article Summarizer

A fast, reliable, and production-ready NLP tool that generates concise **3-sentence summaries** from long news articles or raw text using **DistilBART**. Designed for speed, robustness, and real-world news websites.

---

## 🚀 Overview

Modern news articles are often long and time-consuming to read. This project solves that problem by allowing users to paste a **news article URL or raw article text** and instantly receive a **clear, accurate 3-sentence summary**.

The system is optimized for:
- **Speed** (using DistilBART instead of heavier models)
- **Robust article extraction** (works on sites like BBC, Reuters, Medium)
- **Clean summarization** (no repetition, no over-generation)
- **Production readiness** (safe chunking, dynamic length handling)

---

## 🎯 Why This Project Matters

### 📌 Information Overload

Readers today face an overwhelming volume of news. This tool enables:
- Faster decision-making
- Improved content consumption
- Efficient research and briefing workflows

### 📌 Real-World NLP Challenges Addressed

This project tackles multiple real-world NLP problems:
- Long-document summarization
- Token length constraints in Transformer models
- Noisy or blocked news website scraping
- Avoiding repetition and hallucination in summaries

---

## 🧠 How It Works

### 1️⃣ Input Handling
- Accepts either:
  - A **news article URL**
  - **Raw article text**

### 2️⃣ Article Extraction
- Uses **`trafilatura`** for web scraping
- Handles bot-protected sites better than traditional libraries
- Extracts only the main article content (no ads or clutter)

### 3️⃣ Chunking Strategy
- Long articles are split into safe word-based chunks
- Prevents Transformer token overflow
- Ensures summaries remain accurate

### 4️⃣ Summarization Engine
- Model: `sshleifer/distilbart-cnn-12-6`
- Chunks are summarized individually
- Partial summaries are merged and compressed again
- Dynamic length control prevents repetition

### 5️⃣ Final Output
- Exactly **3 sentences**
- Clean, concise, readable TL;DR

---

## 🧪 Example Output

**Input:** A 700+ word news article on semiconductor policy

**Output:**
> India has announced a new policy initiative to boost semiconductor manufacturing as part of its push for technological self-reliance. The initiative expands incentives, streamlines approvals, and strengthens collaboration with global technology leaders while investing in talent and research. Experts believe the move could position India as a reliable semiconductor hub amid global supply chain uncertainties.

---

## ⚙️ Tech Stack

| Component | Technology |
|-----------|------------|
| Language | Python |
| NLP Model | DistilBART (CNN-12-6) |
| Framework | Hugging Face Transformers |
| Web Extraction | Trafilatura |
| Tokenization | SentencePiece |
| Environment | Google Colab / Python 3.10+ |

---

## 📦 Installation (Google Colab)

```bash
pip install transformers torch trafilatura nltk sentencepiece
```

---

## ▶️ Usage

### Summarize a URL

```python
summary = summarize_article("https://www.bbc.com/news/...")
print(summary)
```

### Summarize Raw Text

```python
summary = summarize_article(long_text)
print(summary)
```

---

## 🛡️ Key Engineering Decisions

### ✅ Why DistilBART?
- 40% faster than BART-Large
- Minimal accuracy tradeoff
- Ideal for real-time summarization

### ✅ Why Trafilatura?
- Actively maintained
- Works on bot-protected news sites
- Cleaner article extraction

### ✅ Why Dynamic Length Control?
- Prevents over-generation warnings
- Avoids repeated phrases
- Adapts to short and long inputs automatically

---

## 🔒 Limitations

- Extracted summaries depend on article quality
- Highly technical or data-heavy articles may lose some nuance
- Model is extractive-abstractive, not fully factuality-guaranteed

---

## 🚀 Future Enhancements

- REST API using FastAPI
- Streamlit or Gradio web interface
- Batch summarization for multiple URLs
- Multilingual summarization
- Headline + TL;DR generation
- Chrome extension integration

---

## 🧑‍💻 Ideal Use Cases

- News aggregation platforms
- Research and policy analysis
- Student and academic reading assistance
- Journalists and editors
- Personal productivity tools

---

## 🏆 What This Project Demonstrates

- Practical NLP engineering
- Transformer model optimization
- Real-world data handling
- Clean and maintainable code design
- Production-focused thinking

---

## 📄 License

MIT License

---

## ⭐ Acknowledgements

- Hugging Face Transformers
- Trafilatura developers
- Facebook AI Research (BART)

---

**Built to make news consumption faster, smarter, and cleaner.**

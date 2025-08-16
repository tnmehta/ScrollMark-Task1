# Tree Hut Social Media Trends Analysis

This project analyzes ~18,000 Instagram comments from **Tree Hut** (March 2025) to identify **customer sentiment, trending flavours, and themes of discussion**.  
The goal is to provide **social media managers** and **product managers** with actionable insights into what customers are saying, and how these trends shift over time.

---

## 📂 Project Structure
```
.
├── Task1.ipynb                  # Main analysis notebook (ETL + EDA + insights + visuals)
├── Report_Presentation.pptx     # Slides summarizing findings (executive-ready)
├── Report_Presentation.pdf      # PDF version of slides
└── README.md                    # Documentation
```

---

## 🚀 Setup & Requirements

1. **Clone repo / unzip project**
   ```bash
   git clone <your-repo-link>
   cd <your-repo>
   ```

2. **Create virtual environment**
   ```bash
   conda create -n treehut python=3.11
   conda activate treehut
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

   Key packages used:
   - `pandas`, `numpy` — data processing
   - `matplotlib`, `seaborn`, `wordcloud` — visualization
   - `nltk`, `scikit-learn` — text preprocessing & clustering
   - `vaderSentiment` — sentiment analysis
   - `spacy` — NER (for country detection)
   - `ollama` (optional) — LLM-assisted theme extraction

4. **Download NLTK stopwords**
   ```python
   import nltk
   nltk.download("stopwords")
   ```

---

## 📊 Analysis Workflow

1. **Data Cleaning**
   - Removed emojis, hashtags, mentions, URLs, promo codes, and extra punctuation.
   - Normalized casing and stripped whitespace.

2. **Feature Engineering**
   - Extracted `day`, `month`, `quarter`, and `season` from `timestamp`.
   - Built `clean_comment` text field.
   - Classified `sentiment` (Positive / Negative / Neutral) using VADER.
   - Extracted `flavours` (LLM-based + keyword fallback).
   - Assigned `themes` across 10 categories (Fragrance, Availability, Packaging, etc.).

3. **Exploratory Analysis**
   - Sentiment distribution overall and by flavour.
   - Top flavours by mentions & positivity %.
   - Trend analysis across **day / month / season**.
   - Word clouds, n-grams, and bubble charts for key segments.
   - Network graph of co-occurring terms.

4. **Insights Extraction**
   - LLM-assisted top-10 insights per theme.
   - Highlighted **3 Key Takeaways**:
     - 🌸 Fragrance drives loyalty & complaints.  
     - 🏪 Retail distribution is a bottleneck.  
     - 📦 Packaging & usage friction hurts experience.  

---

## 📑 Deliverables

- **Notebook (`Task1.ipynb`)**: Full analysis pipeline with modular functions.
- **Slides (`Report_Presentation.pptx` / `.pdf`)**: Executive-ready summary of findings with visuals.
- **README.md**: Setup + documentation.

---

## 🔮 Extension Proposal

If extended to a full project:
1. **Real-time Trend Tracking** — ingest live comments via API + dashboards.
2. **Clustering + LLM Hybrid** — scalable theme detection without manual rules.
3. **Regional/Retail Segmentation** — US vs. Canada, Walmart vs. Target, etc.
4. **Product Roadmap Linkage** — connect demand signals (e.g., “bring back scents”) directly to PM planning.
5. **Influencer/UGC Monitoring** — detect when promotions or collabs drive spikes.

---

## 🤖 AI Tool Usage Disclosure
- **ChatGPT (OpenAI GPT-5)** was used to assist with:
  - Code scaffolding (data cleaning, visualization templates).
  - Drafting README and presentation outlines.
- **Ollama (gemma3:4b)** optionally used for **flavour extraction** and **insight summarization**.
- All insights were **cross-validated with manual inspection** to ensure accuracy.

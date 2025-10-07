# Policy Readability and Sentiment Analysis

### Project Overview
This project explores the relationship between the **readability** and **sentiment** of real-world privacy and policy documents. The goal was to understand whether the tone and emotional polarity of a policy are influenced by how readable it is.

By combining **linguistic readability metrics** and **sentiment analysis**, this project provides insights into how corporate policies communicate with the public — whether they are easy to understand, and how positive or complex their language tends to be.

---

### Dataset Description
- **Policy Texts**: Over 56,000 `.txt` files of policy documents.
- **Metadata**: A complementary CSV containing readability scores (`flesch`, `cl`, `smog`, etc.) and other text-level attributes.

Each text file represents one policy document scraped and archived from the web.  
The metadata file provides additional readability indices used for comparison and validation.

---

### Project Workflow

#### 1. Data Loading and Text Extraction
- Loaded policy documents and metadata from local directories.
- Used **BeautifulSoup** to extract clean text content from HTML.
- Extracted publication **year** using regular expressions.

#### 2. Readability Metrics Computation
For each policy document, calculated:
- Flesch Reading Ease  
- Flesch-Kincaid Grade  
- Coleman-Liau Index  
- Dale-Chall Score  
- SMOG Index  

Used the **`textstat`** library to automate linguistic complexity scoring.

#### 3. Sentiment Analysis
- Performed document-level sentiment analysis using **TextBlob**.
- Computed **polarity** (positivity/negativity) and **subjectivity** (emotional tone).
- Saved results for all documents in `sentiment_results.csv`.

#### 4. Exploratory Analysis & Visualization
- Visualized the distribution of polarity and subjectivity using boxplots.
- Tracked **median sentiment trends over years** to identify temporal patterns.
- Combined readability and sentiment data for **correlation analysis**.

#### 5. Correlation Analysis
Merged both datasets to examine relationships between sentiment and readability features.

| Metric | Correlation with Polarity | Correlation with Subjectivity |
|---------|----------------------------|-------------------------------|
| Flesch Reading Ease | +0.18 | +0.21 |
| Coleman-Liau Index | -0.08 | -0.19 |
| SMOG Index | -0.19 | -0.23 |

**Interpretation:**  
Policies that are easier to read (higher Flesch, lower SMOG) tend to have **slightly more positive sentiment** and **less emotional tone**, suggesting that clearer writing aligns with more neutral and professional communication.

---

### Key Results
- **Number of Policies Analyzed:** 56,416  
- **Average Polarity:** 0.078  
- **Average Subjectivity:** 0.395  
- **Correlation Trends:** Negative correlation between text complexity and positivity.  
- **Visualization:** A heatmap clearly illustrates these relationships.

---

### Tech Stack
- **Language:** Python  
- **Libraries:** `pandas`, `textstat`, `textblob`, `seaborn`, `matplotlib`, `beautifulsoup4`, `re`, `numpy`  
- **Visualization Tools:** Matplotlib & Seaborn  
- **Output Files:**  
  - `sentiment_results.csv` – sentiment scores per document  
  - Visualizations – distribution plots and heatmaps  

---

### Insights and Learnings
- Demonstrated end-to-end **text analytics workflow** — from raw document parsing to visualization.
- Understood how **linguistic readability** can affect **perceived tone**.
- Strengthened understanding of **data merging, correlation, and exploratory analysis**.
- Improved familiarity with real-world NLP preprocessing and evaluation methods.

---

### Future Enhancements
- Integrate transformer-based models (e.g., `BERT`, `RoBERTa`) for more nuanced sentiment detection.
- Extend the analysis to include **topic modeling** (LDA) for identifying key policy themes.
- Create a **dashboard** in Power BI or Tableau to visualize readability vs. sentiment interactively.

---

### Conclusion
This project bridges **Natural Language Processing (NLP)** and **Readability Analysis** to uncover linguistic and emotional patterns in real policy texts.  
It reflects practical skills in **text mining, sentiment analysis, data merging, and statistical interpretation**, making it a strong and research-aligned data science project.


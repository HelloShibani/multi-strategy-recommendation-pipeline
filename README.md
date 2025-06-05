![Python Version](https://img.shields.io/badge/python-3.10-blue)  
![License](https://img.shields.io/badge/license-MIT-green)  
![Last Commit](https://img.shields.io/github/last-commit/HelloShibani/multi-strategy-recommendation-pipeline)  
![Repo Size](https://img.shields.io/github/repo-size/HelloShibani/multi-strategy-recommendation-pipeline)  

# 🧠 Modular & Explainable Product Recommendation Engine

A robust, hybrid recommendation engine that uses multiple strategies—collaborative filtering, product embeddings, and fallback logic—to serve personalized product recommendations even in sparse data scenarios. Designed with explainability and real-world applicability in mind.

---

<details>
  <summary>📑 Table of Contents</summary>

  - [Project Overview](#-project-overview)
  - [Techniques Used](#-techniques-used)
  - [Evaluation Summary](#-evaluation-summary)
  - [Dataset](#-dataset)
  - [Repository Structure](#-repository-structure)
  - [How to Run](#-how-to-run)
  - [Summary](#-Summary Slide)
  - [Future Enhancements](#-future-enhancements)

</details>

---

## 📌 Project Overview

This system addresses three core objectives:

- ✅ Deliver accurate, personalized recommendations for active users  
- 🔁 Ensure robust fallback logic for sparse and cold-start users  
- 🧾 Provide explainability metadata to trace why a product was recommended  

Built for practical deployment and system transparency across diverse user personas.

---

## ⚙️ Techniques Used

| Strategy Type      | Method                                |
|--------------------|----------------------------------------|
| Personalized       | SVD, Item-Item Similarity, Node2Vec    |
| Fallback           | Co-Purchase, Co-Search, Category Popularity
|
| Evaluation         | Precision@5, Recall@5, F1@5, Hit@5     |
| Explainability     | Strategy tags + fallback trace logic   |

---

## 📊 Evaluation Summary

- 📌 Evaluated on 500 diverse users (active + cold-start)
- ✅ Strategy layering increased user coverage
- 💡 Revealed gap for cold-start user personalization (future roadmap)

| Strategy                        | F1@5   | User Count |
|----------------------------------|--------|-------------|
| ✅ Personalized via Embedding     | 0.0322 | 76          |
| 🔁 Fallback (Co-Purchase, etc.)   | 0.0000 | 47          |¹

---

¹ *Fallback strategies returned recommendations but failed to match any ground-truth in evaluation, highlighting a gap in effectiveness for cold-start users.*


### 📊 Visual Insights  
Visuals generated in the notebook and stored under `/visuals/`:

- 📈 F1@5 by strategy type  
- 👥 Strategy-wise user coverage  
- 🧩 Strategy distribution pie chart 

---

## 🗃️ Dataset

Filtered subset of Amazon Reviews dataset:

- **15,747** users  
- **2,142** products  
- **18,263** interactions (after filtering for helpfulness, recency, etc.)


📦 [Amazon Fine Food Reviews – Kaggle](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)

Due to file size constraints, the original dataset (`Reviews.csv`) is **not included** in this repository.

### How to Use
To run the full pipeline:

1. Download `Reviews.csv` from the [Kaggle link](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
2. Place the file inside the `/data/` folder
3. Run the notebook `product_recommender_analysis.ipynb` from start to end

📌 _The file `Reviews.csv` is excluded via `.gitignore` for repository cleanliness._


---

## 📂 Repository Structure

```bash
.
├── notebook/
│   └── IntelliRec+End+to+End+Product+Recommendation+Systemder_analysis.ipynb   # Core logic & evaluation
├── data/
│   ├── interaction_df.csv                   # Engine-ready filtered data
│   ├── evaluation_results.csv               # Output metrics
│   └── Reviews.csv                          # Original reviews (sample)
├── visuals/
│   ├── strategy_f1_score.png
│   ├── strategy_user_count.png
│   └── strategy_user_distribution_pie.png
└── README.md

---

## 🚀 How to Run

```bash
# Clone the repo and navigate to the folder
git clone <repo_url>
cd recommendation-engine

# Install dependencies (adjust as needed)
pip install -r requirements.txt

# Run the core notebook
Open notebook/IntelliRec+End+to+End+Product+Recommendation+Systemder_analysis.ipynb

# Outputs
→ Recommendations per user with explainability  
→ Evaluation metrics and visualizations  
→ All results saved in /visuals and /data folders


## 📄 Summary Slide
For a quick visual overview of the system architecture, methods, and evaluation insights:

📄 [View Project Summary Slide (PDF)](./Topline%20Summary%20-%20Recommendation%20System%20Evaluation.pdf)


```markdown
## 🛠️ Future Enhancements

- 🔄 Implement cross-product category relevance for more nuanced recall evaluation  
- 💬 Integrate sentiment-based personalization for experienced users  
- ❄️ Strengthen cold-start recommendations via user intent clustering or onboarding forms  
- 📦 Package engine into modular pipeline for any tabular recommendation dataset  




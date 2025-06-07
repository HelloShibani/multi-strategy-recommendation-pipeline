
````markdown
![Python Version](https://img.shields.io/badge/python-3.10-blue)  
![License](https://img.shields.io/badge/license-MIT-green)  
![Last Commit](https://img.shields.io/github/last-commit/HelloShibani/multi-strategy-recommendation-pipeline)  
![Repo Size](https://img.shields.io/github/repo-size/HelloShibani/multi-strategy-recommendation-pipeline)

# 🧠 Modular & Explainable Product Recommendation Engine

A robust, real-world-ready recommendation system that blends **personalization**, **fallback logic**, and **explainability** to deliver product suggestions even in sparse or cold-start scenarios. Built with transparency and modularity in mind.

---

<details>
  <summary>📑 Table of Contents</summary>

- [Project Overview](#-project-overview)  
- [Techniques Used](#-techniques-used)  
- [Evaluation Summary](#-evaluation-summary)  
- [Dataset](#-dataset)  
- [Repository Structure](#-repository-structure)  
- [How to Run](#-how-to-run)  
- [Summary Slide](#-summary-slide)  
- [Future Enhancements](#-future-enhancements)  

</details>

---

## 📌 Project Overview

This project solves for three core objectives:

- ✅ Deliver accurate, personalized product recommendations  
- 🔁 Ensure layered fallback when personalization is limited  
- 🧾 Provide metadata-based explanations for each recommendation  

It’s designed to be **modular**, **transparent**, and **transferable** across domains.

---

## ⚙️ Techniques Used

| Strategy Type  | Methodologies                          |
|----------------|----------------------------------------|
| Personalized   | SVD, Item-Item Similarity, Node2Vec    |
| Fallback       | Co-Purchase, Co-Search, Popularity     |
| Evaluation     | Precision@5, Recall@5, F1@5, Hit@5     |
| Explainability | Strategy tagging, Fallback trace logic |

---

## 📊 Evaluation Summary

- Evaluated across 500 diverse users (active + cold-start)  
- Multi-strategy layering significantly increased user coverage  
- Highlighted opportunity to improve cold-start recommendations

| Strategy                        | F1@5   | Users Covered |
|--------------------------------|--------|----------------|
| ✅ Personalized via Embedding   | 0.0322 | 76             |
| 🔁 Fallback (Co-Purchase, etc.) | 0.0000 | 47¹            |

¹ *Recommendations were returned but didn’t match ground-truth items — useful for diagnostics and roadmap prioritization.*

### 📈 Visual Insights  
Stored in `/visuals/`:
- F1@5 by strategy  
- Strategy-wise user count  
- Strategy distribution (pie)

---

## 🗃️ Dataset

A filtered subset of the **Amazon Reviews** dataset with applied constraints on helpfulness, recency, and activity.

- 🧑‍🤝‍🧑 **15,747 users**  
- 📚 **2,142 products**  
- ✍️ **18,263 interactions**

📥 Download from: [Kaggle – Amazon Fine Food Reviews](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)

> **Note**: `Reviews.csv` must be manually downloaded and placed in the `/data/` folder. It is excluded from the repo for size and licensing reasons.

---

## 📂 Repository Structure

```bash
.
├── notebook/
│   └── IntelliRec+End+to+End+Product+Recommendation+Systemder_analysis.ipynb
├── data/
│   ├── interaction_df.csv
│   ├── evaluation_results.csv
│   └── Reviews.csv  # (local use only)
├── visuals/
│   ├── strategy_f1_score.png
│   ├── strategy_user_count.png
│   └── strategy_user_distribution_pie.png
└── README.md
````

---

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/HelloShibani/multi-strategy-recommendation-pipeline
cd multi-strategy-recommendation-pipeline

# 2. Install dependencies
pip install -r requirements.txt

# 3. Open the notebook
notebook/IntelliRec+End+to+End+Product+Recommendation+Systemder_analysis.ipynb
```

✅ Outputs:

* Strategy-wise recommendations with traceable explanations
* Visual evaluation charts
* All outputs stored in `/visuals` and `/data`

---

## 📄 Summary Slide

📥 [Click here to view the visual summary (PDF)](./Topline%20Summary%20-%20Recommendation%20System%20Evaluation.pdf)
Includes architecture, strategies, evaluation, and key learnings.

---

## 🛠️ Future Enhancements

* 🔄 Cross-category similarity for smarter recall
* 💬 Sentiment-aware personalization
* ❄️ Enhanced cold-start onboarding
* 📦 Wrap logic into plug-and-play pipeline for other datasets

```



# Yelp Review Intelligence using Generative AI and AWS

This project aims to build a smart review response system for businesses using the Yelp dataset. The goal is to generate category-specific, professional GPT responses for customer reviews and lay the foundation for a future chatbot system powered by Retrieval-Augmented Generation (RAG) and Knowledge Graphs.

---

## 📌 Project Goals

- ✅ Auto-generate personalized business responses to reviews using OpenAI GPT.
- ✅ Process and organize reviews for multiple business categories.
- ✅ Implement a full pipeline using AWS (Athena, S3, SageMaker).
- 🧠 Prepare structured data for future LLM-based chatbot using RAG & Knowledge Graphs.

---

## 📂 Dataset

Used the **Yelp Open Dataset**, containing:
- `business.json`: Business details, location, category
- `review.json`: Customer reviews with star ratings
- `user.json`: Reviewer metadata

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Amazon S3** | Store raw and processed data files |
| **Amazon Athena** | SQL querying over JSON datasets |
| **Amazon SageMaker** | GPT response generation, scalable compute |
| **OpenAI API** | GPT-3.5 Turbo for review responses |
| **Python / Pandas** | Data processing & transformations |
| **SQL** | Category-based filtering, sampling, joining data |

---

## ⚙️ Pipeline Overview

1. **Data Preparation**
   - Split `business`, `review`, and `user` data
   - Upload to S3 and query using Athena

2. **Category & Review Sampling**
   - Identify top 50 categories by number of reviews
   - Extract 100 balanced reviews per category with priority to 1–3 star reviews

3. **GPT Response Generation**
   - Load review CSVs from S3
   - Use OpenAI GPT-3.5 to generate polite business responses
   - Save output files (`gpt_<category>.csv`) to S3

4. **Output**
   - Clean CSVs for each category with review + GPT response
   - Data ready for chatbot integration

---

## 📊 Example Use Case

> Review: "The food was great but the service was slow."
>
> GPT Response (for a restaurant):
> "Thank you for your feedback! We're thrilled you enjoyed the food and apologize for the service delay. We're working on improving our wait times."

---

## 🔮 What's Next

- Implement chatbot for Q&A using RAG or Knowledge Graphs
- Compare response quality & speed between GPT-only, RAG, and KG approaches
- Deploy Streamlit frontend for demo use

---

## 📁 Repo Structure

```
yelp-review-intelligence/
├── scripts/
│   └── gpt_review_responder.py
├── sql/
│   └── athena_queries.sql
├── data/
│   └── sample_category_reviews.csv
├── README.md
```

---

## 🧑‍💻 Author
**Kiran Ranganalli**  
Graduate Student | Business Analytics  
Passionate about AI-driven data products and automation

---

## 📬 Contact
For inquiries or collaborations, feel free to reach out via GitHub or LinkedIn.

---

## 🏷️ Tags
`Generative AI` `OpenAI` `AWS Athena` `Yelp Dataset` `GPT-3.5` `LLM` `Review Analysis` `Data Pipeline` `Business Intelligence`


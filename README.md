# Log Classification with Hybrid Framework

This project presents a **hybrid log classification system** designed to handle real-world, large-scale log data with varying complexities. By integrating **Regex**, **BERT-based models**, and **LLMs**, the framework achieves flexible, robust, and accurate classification.

---

## Problem Statement

Log messages vary in structure and complexity. Traditional models fail when:
- Patterns are too rigid or dynamic
- Labeled data is sparse
- Complex semantic understanding is required

**Our hybrid system dynamically chooses the right tool for each type of pattern.**
## 🧠 Classification Strategy

![Classification Flowchart]("C:\Users\Santhosh\Downloads\flowchartLOGCLASSification.png")


## ⚙️ Hybrid Components

### ✅ 1. **Regex-Based Classification**
- Best suited for **predictable** patterns
- Rule-based and lightweight
- Classifies simple logs immediately

### ✅ 2. **BERT + Logistic Regression**
- For **complex logs** with **sufficient training data**
- Uses **SentenceTransformer** for embeddings
- Clusters logs using **DBSCAN**
- Applies **Logistic Regression** to assign labels

### ✅ 3. **LLM (Large Language Model)**
- Used when **training data is insufficient**
- Provides generalization for complex, rare log entries
- Fallback for hard-to-classify logs

---

project-root/
│
├── training/              # Code for Regex, SentenceTransformer, and Logistic Regression
│   ├── regex_classifier.py
│   ├── bert_classifier.py
│   └── clustering.py
│
├── exported_models/       # Saved embeddings and logistic regression model
│   ├── model.joblib
│   └── sentence_embeddings/
│
├── resources/             # CSV datasets, outputs, images, and logs
│   ├── input.csv
│   └── output.csv
│
├── server.py              # FastAPI server
└── requirements.txt       # List of dependencies

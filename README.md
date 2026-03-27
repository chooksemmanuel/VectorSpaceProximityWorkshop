# 🧠 Vector Space Proximity Workshop
## PROG 8245 — Machine Learning Programming | Lab 7 | Group 6

---

## 👥 Team Members
- Emmanuel Ihejiamaizu (Chooks)
- Liggia Elena Taboada Cruz
- Chao-Chung Liu (Thomas)

---

## 📦 Dataset

**Name:** CISA Known Exploited Vulnerabilities (KEV) Catalog  
**Source:** https://www.cisa.gov/sites/default/files/csv/known_exploited_vulnerabilities.csv  
**License:** U.S. Government Open Data — Public Domain  
**Records:** 1,551 CVE entries (200 sampled for this workshop)  
**Domain:** Cybersecurity — real vulnerability records published by the U.S. Cybersecurity and Infrastructure Security Agency  

**Why we chose it:**
- Real government-verified data — no synthetic corpus
- Built-in relevance labels: `knownRansomwareCampaignUse == 'Known'` = Relevant
- Rich cybersecurity vocabulary ideal for TF-IDF and IR evaluation
- Directly relevant to our team's specialisation in AI + Cybersecurity

---

## 🔍 Retrieval Approach Summary

We built a complete Information Retrieval pipeline over 200 CISA CVE vulnerability descriptions:

1. **Preprocessing** — Tokenization → Stop-word removal → Porter Stemming
2. **Vector Space Construction** — Term-Document Incidence Matrix, TF, Log TF, DF, IDF, TF-IDF
3. **Retrieval** — Cosine Similarity over TF-IDF vectors (sklearn `TfidfVectorizer`)
4. **5 Information Needs** — Remote Code Execution, Buffer Overflow, SQL Injection, Ransomware Campaign, Authentication Bypass
5. **Representation Comparison** — Binary Incidence vs TF-IDF
6. **Evaluation** — Confusion Matrix, Precision, Recall, F1, Accuracy, Kappa, Precision@K, AP, MRR

**Key finding:** TF-IDF outperforms Binary representation for short vulnerability descriptions. MRR confirms the system reliably surfaces at least one relevant document in the top 3 results for all queries.

---

## 📁 Repository Contents

| File | Description |
|---|---|
| `VectorSpaceProximityWorkshop.ipynb` | Main workshop notebook — full IR pipeline + evaluation |
| `known_exploited_vulnerabilities.csv` | CISA KEV dataset (download from source URL above) |
| `README.md` | This file |

---

## 🚀 How to Run

```bash
python -m venv venv
venv\Scripts\activate        # Windows
pip install numpy pandas scikit-learn matplotlib nltk jupyter
jupyter notebook VectorSpaceProximityWorkshop.ipynb
```

Place `known_exploited_vulnerabilities.csv` in the same folder before running.

---

## 🔗 GitHub Repository

`VectorSpaceProximityWorkshop`

---

*Conestoga College | Graduate Diploma in Applied AI & Machine Learning*

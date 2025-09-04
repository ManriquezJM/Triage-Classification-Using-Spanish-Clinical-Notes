# Triage-Classification-Using-Spanish-Clinical-Notes
This repository presenting a comparative study of classical machine learning algorithms and deep learning approaches (ALBERT) for automated triage classification in Spanish-language emergency department notes.

# Automated Triage Classification in Emergency Services Using Spanish Clinical Notes


---

## 📌 Motivation
Triage in emergency departments often relies on nursing notes. Traditional methods are **subjective** and prone to **undertriage/overtriage**.  
Natural language processing (NLP) offers a path to more **accurate and consistent** triage support systems.  

Most prior work has focused on **English clinical text**.  
This study addresses that gap by focusing on **Spanish clinical notes** in a Chilean healthcare setting.  

---

## 📊 Dataset
- **Source**: Emergency department in Chile  
- **Triage categories**:  
  - **C1**: Vital emergency  
  - **C2**: Severe emergency  
  - **C3**: Moderate emergency  
  - **C4**: Minor emergency  
  - **C5**: Non-emergency  
- **Preprocessing**:
  - Text standardization  
  - Domain-specific abbreviation dictionary  
  - Tokenization with **SentencePiece** (31k vocabulary)  

---

## ⚙️ Methodology
Three experimental setups were evaluated:  

1. **Structured data only**  
   - Features: vital signs, age, blood pressure, etc.  
   - Models: CatBoost, XGBoost, Random Forest, MLP, Extra Trees, Logistic Regression  

2. **NLP with ALBERT**  
   - Input: Spanish clinical notes  
   - Approach: Fine-tuned ALBERT embeddings  

3. **Hybrid model**  
   - Combines structured features + ALBERT embeddings from notes  

**Data split**: 80/20 stratified sampling  
**Metrics**: Accuracy, F1-score, AUROC  

---

## 🏆 Results
| Experiment | Accuracy | F1-score | AUROC |
|------------|----------|----------|-------|
| Structured only | 59% | 56% | 0.88 |
| Clinical notes (ALBERT) | 75% | 74% | 0.89 |
| Hybrid (Structured + Notes) | **77%** | **76%** | **0.96** |

- **Best critical case detection (C2, C3): Hybrid + XGBoost**  
  - C2 → Accuracy: 83%, F1: 83%  
  - C3 → Accuracy: 77%, F1: 78%  

🔹 The AUROC of 0.96 exceeds the **0.91 average** reported in Matos (2024) for English-based models.  

---

## 📚 References
- Chang, Y.-H. et al. (2024). *Using machine learning and natural language processing in triage for prediction of clinical disposition in the emergency department.* BMC Emergency Medicine, 24(1).  
- Matos, B. (2024). *Improving triage performance in emergency departments using machine learning and natural language processing: a systematic review.* BMC Emergency Medicine, 24(1).  

---

## 🚀 Future Work
- Expansion of dataset  
- Integration of contextual variables  
- Further exploration of hybrid models  
- Prospective validation before clinical deployment  

---


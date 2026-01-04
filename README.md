# Fine-tuning Pre-trained Models

Detect symptoms from clinical notes using **two complementary approaches**:

---

## 1️⃣ Fine-tuning Pre-trained Models
- Use **BERT / ClinicalBERT** to fine-tune on labeled clinical text.
- Captures deep semantic patterns in clinical notes.
- Pros: high accuracy on medium/large datasets.  
- Cons: needs more compute, small datasets may overfit.

**Workflow:**  
Clinical notes → Tokenizer → BERT input → Fine-tune → Classifier → Prediction
---

## 2️⃣ Rule-based + ML
- Combine **negation-aware rules** (e.g., "no pain") + **dictionaries** with ML classifiers (Logistic Regression / SVM).
- Pros: works on small data, interpretable.  
- Cons: may miss unseen expressions.

**Workflow:**  
Clinical notes → Negation & Dictionary → TF-IDF / BERT Embeddings → ML Classifier → Prediction
---

## Key Points
- **Negation detection** is crucial in clinical text.  
- **Small datasets:** use Rule-based + ML or frozen embeddings.  
- **Medium/Large datasets:** fine-tune BERT.  
- Hybrid approach: combine rules + ML + optional fine-tuning for robust predictions.

---

## Tools
- Transformers (BERT / ClinicalBERT)  
- SpaCy / scispaCy (NER)  
- scikit-learn (Logistic Regression, SVM)  
- PyTorch, NumPy

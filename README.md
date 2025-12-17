# 🧠 Multimodal Fake News Verification System

A **Multimodal misinformation detection system** that verifies news claims using **text**, **images**, **external evidence**, and **text–image consistency**.

This project is designed to be **academically strong**, **practically deployable**, and **resource‑conscious**, making it suitable for whatsapp fake messages detection

(NOTE:- app.py is actually google collab code downloadeed in .py formate)
---
### Example 1: TRUE Claim

**Input Text:**
> The Indian Constitution came into effect on January 26, 1950.

**Output:**
```
Verdict: REAL ✅
Credibility Score: 0.92
```

**Evidence Retrieved:**
- Constitution of India – historical fact

---

---

## 🚀 What Does This Project Do?

Given:
- 📝 A **news claim or paragraph** (required)
- 🖼️ An **optional image**

The system:
1. Verifies the **text claim** using a fine‑tuned BERT model
2. Classifies the **image** using a Vision Transformer (ViT)
3. Retrieves **supporting evidence** from a factual database using FAISS
4. Checks **text–image consistency** using CLIP
5. Combines everything using **dynamic weighted fusion**

👉 Outputs a **final credibility score** and **REAL / FAKE verdict**, along with retrieved evidence.

---
## 🚀 Project Features

- **Multimodal Misinformation Detection**  
  Verifies claims using **text, images, and external evidence** instead of relying on a single modality.

- **CPU-Optimized Architecture**  
  Fully runnable on **CPU-only environments** (Google Colab / local machine) without requiring a GPU.

- **Text-Based Claim Verification**  
  Uses a transformer-based language model to analyze semantic correctness and detect suspicious claims.

- **Image Authenticity Analysis**  
  Evaluates whether attached images are consistent and credible using a vision transformer.

- **Evidence Retrieval & Verification**  
  Retrieves top-K related facts using **FAISS + sentence embeddings** and scores evidence support.

- **Text–Image Consistency Checking**  
  Applies CLIP-based similarity to detect mismatches between textual claims and images.

- **Dynamic Multimodal Fusion**  
  Combines text, image, and evidence signals into a single **credibility score** using weighted logic.

- **Data-Driven Threshold Tuning**  
  Automatically tunes decision thresholds to maximize **F1-score** instead of using fixed heuristics.

- **Paragraph-Level Evaluation**  
  Handles long news articles by evaluating sentence-level claims and aggregating results.

- **Ablation Study Support**  
  Built-in evaluation for:
  - Text only  
  - Image only  
  - Evidence only  
  - Text + Image  
  - Text + Evidence  
  - Full multimodal system  

- **Explainable Predictions**  
  Returns per-component probabilities (text, image, evidence) alongside the final decision.

- **Robust Evaluation Metrics**  
  Reports **Precision, Recall, and F1-score** for each modality and combined system.

- **Scalable Design**  
  Modular components allow easy replacement or upgrading of models.

- **Research & Resume Ready**  
  Includes:
  - Threshold tuning
  - Ablation experiments
  - Multimodal reasoning
  - Clear evaluation pipeline

- **Production-Friendly Structure**  
  Clean project layout suitable for deployment, demos, and further research extensions.

---

## 🧩 System Architecture

```
User Input (Text / Image)
        │
        ├── Text Model (BERT)
        │
        ├── Image Model (ViT)
        │
        ├── Evidence Retrieval (Sentence‑BERT + FAISS)
        │
        ├── Text–Image Check (CLIP)
        │
        ▼
Dynamic Weighted Fusion + Thresholding
        ▼
 Final Credibility Score + Verdict
```

---

## 🧠 Models & Techniques Used

| Component | Model / Method |
|---------|---------------|
| Text Classification | **BERT (bert‑base‑uncased)** |
| Image Classification | **Vision Transformer (ViT‑Tiny)** |
| Evidence Retrieval | **Sentence‑BERT + FAISS** |
| Text–Image Consistency | **CLIP (ViT‑B/32)** |
| Fusion Strategy | Dynamic weighted averaging |
| Metrics | Precision, Recall, F1, Ablation |

All models are run **on CPU** (with reduced dataset sizes for feasibility).

---
---

## 🖥️ Gradio Web Interface

The project includes a **Gradio UI**:

- Enter a text claim
- Upload an optional image
- Get:
  - Final verdict
  - Credibility score
  - Evidence snippets
  - CLIP similarity score

---

## 🧠 Limitations 

- Thresholds tuned on small validation sets due to cpu limitations 

---

## 🔮 Future Improvements

- Cross‑attention multimodal transformer
- Better image dataset
- Online fact‑checking APIs
- Knowledge‑graph‑based evidence
- GPU scaling

---



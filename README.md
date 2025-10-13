<!-- PROJECT LOGO -->
<p align="center">
  <img src="image\logo_1.png" alt="MindMeal Logo" width="650"/>
</p>

<h1 align="center">MindMeal 🍽️ — AI Assistant for Understanding and Recovery from Eating Disorders</h1>

<p align="center">
  An intelligent and empathetic assistant designed to detect early signs of eating disorders (TCA), 
  understand emotional patterns, guide users toward recovery, and provide continuous personalized support.
</p>

---

## 🧭 Overview

**MindMeal** is an AI-driven platform that combines psychology, nutrition, and data science to help users:
- Detect and classify potential eating disorders through validated questionnaires.
- Express emotions through conversation and receive empathetic AI feedback.
- Receive personalized and adaptive recommendations to encourage recovery.
- Estimate calories from meal pictures and track progress.
- Monitor emotional and behavioral evolution to detect early relapse risks.

---

## 🩺 1. Diagnosis & Classification

### **Goal**
Determine whether the user shows signs of an eating disorder and identify its type (e.g., anorexia, bulimia, binge eating).

### **Data**
- Structured questionnaire data (EDE-Q, SCOFF, BITE, EAT-26)
- Demographic and lifestyle information
- Optional free-text inputs

### **Models**
- Logistic Regression, Random Forest, or XGBoost for structured form data  
- BERT-based text classifier for open-ended responses  

### **Example Datasets**
- [EDE-Q dataset (Open Science Framework)](https://osf.io/)
- [NIMH Data Archive - Eating Disorders](https://nda.nih.gov/)

---

## 💬 2. Emotion-Aware Chat Assistant

### **Goal**
Enable users to chat freely and express emotions during meals or stress episodes. The assistant detects tone, emotions, and patterns influencing eating behavior.

### **Data**
- Conversational text datasets labeled with emotion and mental health states

### **Models**
- Transformer-based emotion detection (BERT, RoBERTa)
- Empathetic dialogue system (Retrieval-based + fine-tuned LLM)

### **Example Datasets**
- [DAIC-WOZ Depression Dataset](https://dcapswoz.ict.usc.edu/)
- [EmpatheticDialogues Dataset](https://github.com/facebookresearch/EmpatheticDialogues)
- [Reddit Mental Health Dataset (CLPsych)](https://zenodo.org/record/4919049)

---

## 🧭 3. Personalized Recommendation System

### **Goal**
Provide adaptive daily recommendations (balanced meals, emotional exercises, mindful routines) that evolve with the user’s progress and feedback.

### **Data**
- User history (diagnosis results, engagement, emotional states)
- Food intake and lifestyle logs
- Interaction feedback (which recommendations were followed)

### **Models**
- Content-based filtering
- Neural Collaborative Filtering (NCF)
- Contextual Bandits / Reinforcement Learning for adaptive personalization

### **Example Datasets**
- Synthetic data from user logs
- [Open Food Facts](https://world.openfoodfacts.org/) for nutritional data
- [MyFoodRepo API](https://www.myfoodrepo.org/)

---

## 🍱 4. Food Image Analysis & Calorie Estimation

### **Goal**
Estimate calories and nutrients from pictures of meals taken by the user.

### **Data**
- Food image datasets with labeled nutritional values

### **Models**
- CNN-based models (EfficientNet, ResNet, or MobileNet)
- Optional regression layer for calorie estimation

### **Example Datasets**
- [Food-101](https://data.vision.ee.ethz.ch/cvl/food-101.tar.gz)
- [UEC-Food256](http://foodcam.mobi/dataset256.html)
- [Nutrition5k (Google)](https://research.google/pubs/pub49363/)

---

## 📈 5. User History & Relapse Detection

### **Goal**
Track user’s emotional and dietary evolution to detect early signs of relapse or risky behavior patterns.

### **Data**
- Historical logs (emotions, calories, chat data)
- Derived metrics (average mood, skipped meals, activity trends)

### **Models**
- Time Series Models (LSTM, GRU)
- Anomaly detection (Isolation Forest, Autoencoder)
- Explainable AI (SHAP, LIME)

### **Example Datasets**
- Synthetic time-series data generated from logs
- [MIMIC-IV Waveform](https://physionet.org/) for physiological signal integration (optional)

---

## 🧩 System Architecture (Simplified)

```mermaid
flowchart TD
    A[User App] --> B[Diagnosis Form]
    A --> C[Emotion Chat Assistant]
    A --> D[Food Image Analysis]
    A --> E[Daily Logs]
    B --> F[Database]
    C --> F
    D --> F
    E --> F
    F --> G[Recommendation Engine]
    G --> H[User Dashboard & Progress]

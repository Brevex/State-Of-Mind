# State-Of-Mind

This project explores the evolution of Natural Language Processing (NLP) by implementing and comparing two distinct approaches to Sentiment Analysis using the IMDB dataset.
We contrast a classical statistical method (Hidden Markov Models) against a modern deep learning approach (Large Language Models via BERT). The goal is to classify movie reviews as either Positive or Negative.

## 🔍 Approaches Implemented

### 1. Hidden Markov Model (HMM)

* **Library:** hmmlearn
* **Feature Engineering:** Uses GloVe (Global Vectors) 300-dimensional word embeddings to represent words.
* **Logic:** We train two separate Gaussian HMMs—one on positive reviews and one on negative reviews. Prediction is based on the log-likelihood difference between the two models (selecting the model that "best fits" the sequence).
* **Preprocessing:** Custom stop-word removal (preserving negation words like "no", "not").

### 2. Large Language Model (LLM) - BERT

* **Library:** transformers (Hugging Face) & tensorflow
* **Model:** bert-base-uncased
* **Logic:** Fine-tuning a pre-trained BERT model for sequence classification.
* **Preprocessing:** Standard BERT tokenization with padding and truncation (Max Length: 128).

## 📊 Results

The comparison highlights the massive leap in performance provided by Transformer-based architectures.

<br><div align="center"> 
  
  | Model | Type | Accuracy | Performance Note | 
  |:-----:|:----:|:--------:|:----------------:|
  |HMM|Statistical / Probabilistic|~70%|Efficient baseline, but struggles with long-range dependencies and context.|
  |LLM|Transformer|~99%|State-of-the-art performance; excellent at capturing deep contextual nuances.|
  
</div>


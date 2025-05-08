# Posting-Sanitized-Comments-On-Social-Networks-Using-Differential-Privacy

This repository contains code for generating privacy-preserving versions of social media posts (comments and tweets) using differential privacy techniques. The goal is to sanitize user-generated content to prevent attribute inference attacks while maintaining semantic integrity.

---

## Repository Structure

The project is organized into two main directories:

### `/Comments`

Contains all experimental files and models related to comments.

### `/Tweets`

Contains all experimental files and models related to tweets.

Each of these folders includes the following subdirectories:

---

###  Models

Includes trained machine learning models for attribute inference and privacy transformation:

* **BERT**
  Fine-tuned BERT models used to infer sensitive attributes from comments or tweets.

* **CNN**
  Convolutional neural network models trained for comparison and inference tasks.
* **RNN**
  Recurrent neural network models trained for comparison and inference tasks.

---

### Check Similarity

* Python scripts for comparing the semantic similarity between original and privacy preserving text.
* Helps ensure that sanitized versions retain the meanin of the original posts.

---

### Replaced Words (Generating comments or Tweets)

* Scripts for replacing sensitive or high-risk words with safer alternatives.
* Uses GloVe Wiki Giga Word word embeddings to find semantically similar, non-sensitive substitutes.
* Outputs differential privacy-compliant text for both comments and tweets.

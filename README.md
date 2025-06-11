# Posting-Sanitized-Comments-On-Social-Networks-Using-Differential-Privacy

## **Research Paper Title: Posting Sanitized Comments On Social Networks Using Differential Privacy** 

--- 

## Overview

This repository accompanies the research paper titled "_Posting Sanitized Comments on Social Networks Using Differential Privacy_". which addresses privacy concerns on social media by developing a method to obscure sensitive user data within comments and tweets. The approach uses Differential Privacy (DP) to replace sensitive words, misleading inference models while preserving the overall meaning. We evaluate our method on real social media datasets, achieving reduced classifier accuracy on sensitive attributes such as gender and political affiliation while maintaining high semantic similarity between the original and differentially private text

---

## Repository Structure

The project is organized into two main directories:

+ **`Comments`**
: Contains all experimental files related to comments.

+ **`Tweets`**
: Contains all experimental files and models related to tweets.

Each of these folders includes the following subdirectories:


###  Models

Includes trained machine learning models for attribute inference and privacy transformation:

* **BERT**
  Fine-tuned BERT models used to infer sensitive attributes from comments or tweets.
* **CNN**
  Convolutional neural network models trained for comparison and inference tasks.
* **RNN**
  Recurrent neural network models trained for comparison and inference tasks.


### Check Similarity

* Python scripts for comparing the semantic similarity between original and privacy preserving text.
* Helps ensure that sanitized versions retain the meanin of the original posts.


### Replaced Words (Generating comments or Tweets)

* Scripts for replacing sensitive or high-risk words with safer alternatives.
* Uses GloVe Wiki Giga Word word embeddings to find semantically similar, non-sensitive substitutes.
* Outputs differential privacy-compliant text for both comments and tweets.

---

## Methodology

1. **Extracting Strong Features** : Using LIME, we identify sensitive words within comments or tweets. These "strong words" are integral to classifier inference and are targeted for substitution.

2. **Generating Differentially Private Text** : Sensitive words are substituted with semantically similar alternatives using the GloVe embedding database. Our approach utilizes Utility-Optimized Metric Local Differential Privacy (UMLDP) to ensure that replacements maintain semantic relevance while providing privacy.

3. **Similarity Checking** : We employ sentence embedding models (BERT, Sentence BERT, DistilBERT) to quantify similarity between original and differentially private texts, with cosine similarity scores to measure semantic preservation.

---

## Experiment Results

Four scenarios were tested for sensitive word replacement (top 2 or 3 words with top 10 or 15 similar words), showing a significant reduction in classifier accuracy across all models while retaining high similarity scores. For instance, replacing the top 3 sensitive words in comments with top 15 similar words reduced BERT's accuracy from 79.99% to 35.21%, CNN's accuracy from 76.93% to 37.83% and RNN's accuracy from 76.15% to 39.25%.

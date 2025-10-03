# SMS Spam Classification

This repository contains a **from-scratch** implementation of a Multinomial Naive Bayes classifier for detecting spam in SMS messages. The project covers the full machine learning pipeline: data loading, preprocessing, feature engineering, model training, evaluation, and prediction.

---

## Table of Contents

- [Live Demo](#live-demo)
- [Dataset](#dataset)  
- [Preprocessing](#preprocessing)  
- [Model Implementation](#model-implementation)  
- [Results](#results)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [Insights & Observations](#insights--observations)  
- [License](#license)  

---

## Live Demo

- **Explore the project, methodology, and a mock classifier interface on the dedicated showcase website:**

<div align="center">
<a href="https://pickase.github.io/SMSSpamDetection/" target="_blank">
<img src="https://www.google.com/search?q=https://placehold.co/300x50/3b82f6/ffffff%3Ftext%3DView%2BLive%2BProject%2BShowcase" alt="Live Demo Button" />
</a>
</div>

## Dataset

- **Source:** SMS Spam Collection  
- **Total Messages:** 5,572  
- **Labels:** `ham` (legitimate), `spam` (fraudulent/promotional)  

Split:  
- **Training Set:** 4,458 messages (80%)  
- **Test Set:** 1,114 messages (20%)  

---

## Preprocessing

1. **Text Cleaning**  
   - Remove non-word characters (`\W`), convert to spaces  
2. **Case Normalization**  
   - Convert all text to lowercase  
3. **Tokenization**  
   - Split each message into word tokens  
4. **Vocabulary Creation**  
   - Build a set of unique tokens from the training set  
5. **Feature Extraction**  
   - Bag-of-Words: count occurrences of each vocabulary word in each message  

---

## Model Implementation

- **Algorithm:** Multinomial Naive Bayes  
- **Smoothing:** Laplace (add-alpha) smoothing to handle unseen words  
- **Probability Computation:**  
  - \(P(\text{spam} \mid \text{message})\)  
  - \(P(\text{ham} \mid \text{message})\)  
- **Decision Rule:** Assign the label with the higher posterior probability  

---

## Results

| Metric                | Value               |
|-----------------------|---------------------|
| Accuracy              | 98.74%              |
| Correct Predictions   | 1,100 / 1,114       |
| Incorrect Predictions | 14 / 1,114          |
| Error Rate            | 1.26%               |

<figure>
  <img src="charts/sms_spam_model_performance.png" alt="Model Performance" />
  <figcaption>Model performance: 1100 correct vs 14 incorrect predictions (98.74% accuracy).</figcaption>
</figure>

<figure>
  <img src="charts/dataset_split_sms_spam.png" alt="Dataset Split" />
  <figcaption>Dataset split: 80% training, 20% testing.</figcaption>
</figure>

---

## Usage

1. **Clone the repository**  

git clone https://github.com/your-username/sms-spam-classification.git
cd sms-spam-classification

text

2. **Install dependencies**  

pip install -r requirements.txt

text

3. **Run the Notebook**  
Open `SMSSpamDetection.ipynb` to explore data processing, model training, and evaluation.

4. **Predict New Messages**  

from classifier import classify
print(classify("Congratulations! You have won a free ticket..."))



## Insights & Observations

- **Class Distribution:** Imbalanced, with ham messages being the majority class.  
- **Preprocessing:** Effective text normalization and Bag-of-Words representation lead to robust feature extraction.  
- **Model Performance:** Achieved 98.74% accuracy, demonstrating Naive Bayes suitability for SMS spam detection.  
- **Smoothing Effect:** Laplace smoothing handles unseen vocabulary gracefully, avoiding zero probabilities.  
- **Edge Cases:** Short casual texts and longer promotional messages both classified with high confidence.# SMS Spam Classification

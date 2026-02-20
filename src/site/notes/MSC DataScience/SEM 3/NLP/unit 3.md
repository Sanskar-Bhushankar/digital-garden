---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 3/NLP/unit 3/","created":"2026-02-20T05:06:47.566+05:30"}
---


# Overview of Text Classification Tasks

## 1. What is Text Classification
Text Classification is the process of automatically assigning text documents to predefined categories.

In simple words, it means a computer reads text and decides which group it belongs to.

Example:  
Email → Spam / Not Spam  
Review → Positive / Negative

---

## 2. Why Text Classification is Needed
Today there is a huge amount of digital text such as emails, reviews, messages, and articles.  
It is not possible for humans to manually classify all this data.

So, machines are used to classify text automatically.

---

## 3. Basic Example
Message: "Win money now"  
Category: Spam

Message: "Meeting at 5 pm"  
Category: Not Spam

The computer learns from such examples and classifies new messages.
## 4. Steps in Text Classification
Step 1: Data Collection  
Collect labeled text data.

Example: Spam and non-spam emails.

Step 2: Text Preprocessing  
Clean the text.

Includes:  
Removing symbols  
Removing extra spaces  
Converting to lowercase  
Removing common words

Example:  
"I Love AI!!!" → "love ai"

Step 3: Feature Extraction  
Convert text into numbers.

Methods:  
Bag of Words  
TF-IDF  
Word Embeddings

Step 4: Model Training  
Train machine learning algorithms.

Examples:  
Naive Bayes  
Logistic Regression  
SVM  
Neural Networks

Step 5: Prediction  
New text is given to the model.  
The model predicts the category.

---

## 5. Common Algorithms Used
    

Naive Bayes: Fast and simple, good for spam detection  
Logistic Regression: Easy to understand, good accuracy  
SVM: High accuracy for complex data  

---

## 6. Applications of Text Classification
    

Used in:

Email filtering  
Product reviews  
News categorization  
Chatbots  
Search engines  
Social media monitoring

---

# Naive Bayes for Text Classification

## Basic Idea

Naive Bayes is a probability-based classifier.

It uses past data to calculate the probability of a document belonging to a class.

It assumes that all words in a document are independent of each other.

This assumption is called the naive assumption.

---

## Bayes Formula (Using a and b)

Let:

a = Class (Spam, Positive, etc.)  
b = Document

Main formula:

P(a | b) = ( P(b | a) × P(a) ) / P(b)

Meaning:

Probability of class a when document b is given.

In practice, P(b) is same for all classes, so we use:

P(a | b) ∝ P(b | a) × P(a)

---

## Word Independence Formula

If document b has words w1, w2, w3:

P(b | a) = P(w1 | a) × P(w2 | a) × P(w3 | a)

Final formula:

P(a | b) ∝ P(a) × ∏ P(wi | a)

---

## Decision Rule

The class with highest probability is selected:

Class = max [ P(a) × ∏ P(wi | a) ]

---

## Advantages and Limitations

Advantages:

- Very fast
    
- Works well for text
    
- Easy to implement
    

Limitations:

- Assumes words are independent
    
- Zero probability problem
    
- Lower accuracy for complex data
    

---

# Support Vector Machine (SVM) for Text Classification

## Basic Idea

SVM is a margin-based classifier.

It draws a boundary between two classes such that the distance from both classes is maximum.

This distance is called margin.

Only the closest points decide the boundary.

These points are called support vectors.

---

## Hyperplane Formula

The separating line or plane is:

w · x + b = 0

Where:

- w = weight vector
    
- x = document vector
    
- b = bias
    

---

## Classification Formula

For a new document x:

f(x) = sign(w · x + b)

If value is positive → Class 1  
If value is negative → Class 0

---

## Optimization Formula

SVM tries to minimize:

(1/2) ||w||²

With condition:

y (w · x + b) ≥ 1

For noisy data:

(1/2)||w||² + C Σ ξ

---

## Advantages and Limitations

Advantages:

- High accuracy
    
- Works well with high-dimensional text
    
- Effective with TF-IDF
    

Limitations:

- Slow for large datasets
    
- Hard to choose kernel
    
- Less interpretable
    

---

# Logistic Regression for Text Classification

## Basic Idea

Logistic Regression is a probability-based linear classifier.

It first finds probability, then converts it into class.

It is mainly used for binary classification.

---

## Linear Formula

First, a linear value is calculated:

z = w · x + b

---

## Sigmoid Formula

Sigmoid converts z into probability:

P = 1 / (1 + e⁻ᶻ)

So final formula is:

P = 1 / (1 + e⁻(w·x + b))

---

## Decision Rule

If P ≥ 0.5 → Class = 1  
If P < 0.5 → Class = 0

---

## Loss Formula

Logistic Regression uses log loss:

L = −[ y log(p) + (1 − y) log(1 − p) ]

---

## Advantages and Limitations

Advantages:

- Simple and easy to understand
    
- Gives probability output
    
- Works well for sparse data
    

Limitations:

- Only linear boundaries
    
- Not good for complex patterns
    
- Sensitive to outliers
    

---

# Comparison of Three Algorithms

## Key Differences

|Feature|Naive Bayes|SVM|Logistic Regression|
|---|---|---|---|
|Method|Probability|Margin|Probability|
|Speed|Very Fast|Medium|Fast|
|Accuracy|Medium|High|High|
|Boundary|Simple|Complex|Linear|
|Output|Class|Class|Probability|

---

# Evaluation Metrics for Classification

In classification tasks, we measure how well a model is performing using specific metrics. These metrics help assess the **quality of predictions** and compare models. ([Google for Developers](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall?utm_source=chatgpt.com "Classification: Accuracy, recall, precision, and related metrics"))

## Confusion Matrix

Before defining metrics, the **confusion matrix** is fundamental. It shows counts of correct and incorrect predictions. ([GeeksforGeeks](https://www.geeksforgeeks.org/machine-learning/confusion-matrix-machine-learning/?utm_source=chatgpt.com "Understanding the Confusion Matrix in Machine Learning"))

The matrix has four components for binary classification:

- **TP (True Positive)**: Model predicts positive and it is actually positive
    
- **TN (True Negative)**: Model predicts negative and it is actually negative
    
- **FP (False Positive)**: Model predicts positive but it is actually negative
    
- **FN (False Negative)**: Model predicts negative but it is actually positive
    

---

## Accuracy

Accuracy measures **overall correctness** of the model. It is the proportion of all correct predictions. ([Wikipedia](https://en.wikipedia.org/wiki/Accuracy_and_precision?utm_source=chatgpt.com "Accuracy and precision"))

Formula:

```
Accuracy = (TP + TN) / (TP + TN + FP + FN)
```

Accuracy is intuitive but can be misleading when classes are imbalanced. ([Wikipedia](https://en.wikipedia.org/wiki/Accuracy_paradox?utm_source=chatgpt.com "Accuracy paradox"))

---

## Precision

Precision measures how many of the positive predictions are actually correct. It focuses on **positive predictions**. ([Wikipedia](https://en.wikipedia.org/wiki/Precision_and_recall?utm_source=chatgpt.com "Precision and recall"))

Formula:

```
Precision = TP / (TP + FP)
```

High precision means the model’s positive predictions are reliable.

---

## Recall

Recall measures how many of the actual positive cases the model correctly identifies. It focuses on **true positive cases**. ([Wikipedia](https://en.wikipedia.org/wiki/Precision_and_recall?utm_source=chatgpt.com "Precision and recall"))

Formula:

```
Recall = TP / (TP + FN)
```

High recall means the model finds most of the positive cases.

---

## F1 Score

F1 score balances precision and recall into a single metric. It is useful when you want a trade-off between these two metrics, especially in imbalanced datasets. ([Google for Developers](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall?utm_source=chatgpt.com "Classification: Accuracy, recall, precision, and related metrics"))

Formula:

```
F1 = 2 × (Precision × Recall) / (Precision + Recall)
```

F1 score ranges from 0 to 1. Higher values mean better performance.

---

## When to Use Which Metric

- **Accuracy** is useful when classes are balanced and errors cost the same. ([Google for Developers](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall?utm_source=chatgpt.com "Classification: Accuracy, recall, precision, and related metrics"))
    
- **Precision** is important when false positives are costly (e.g., spam detection). ([Google for Developers](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall?utm_source=chatgpt.com "Classification: Accuracy, recall, precision, and related metrics"))
    
- **Recall** is important when missing positive cases is costly (e.g., disease detection). ([Google for Developers](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall?utm_source=chatgpt.com "Classification: Accuracy, recall, precision, and related metrics"))
    
- **F1 Score** is preferred when you want a balance between precision and recall, especially with imbalanced datasets. ([Google for Developers](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall?utm_source=chatgpt.com "Classification: Accuracy, recall, precision, and related metrics"))
    

---

## Multi-Class Classification

For more than two classes, precision and recall can be averaged across classes using **macro** or **micro** averaging. ([evidentlyai.com](https://www.evidentlyai.com/classification-metrics/multi-class-metrics?utm_source=chatgpt.com "Accuracy, precision, and recall in multi-class classification"))

- **Macro-averaging**: Average metric across all classes equally
    
- **Micro-averaging**: Average metric weighted by class frequency
    

---

## Summary of Formulas

```
Accuracy = (TP + TN) / Total
Precision = TP / (TP + FP)
Recall = TP / (TP + FN)
F1 = 2 × (Precision × Recall) / (Precision + Recall)
```

---
# Introduction to Topic Modeling

## What is Topic Modeling

Topic Modeling is a technique used to automatically discover hidden topics in a collection of documents.

In simple words:

It helps a computer find  
“What is this document mainly about?”

without reading it manually.

Example:

From many articles, the model may find topics like:

- Sports
    
- Politics
    
- Technology
    
- Health
    

---

## Why Topic Modeling is Needed

Large amounts of text are generated every day:

- News
    
- Blogs
    
- Reviews
    
- Research papers
    

Reading all manually is not possible.

So topic modeling helps to:

- Organize documents
    
- Summarize content
    
- Find patterns
    
- Improve search systems
    

---

## Basic Idea of Topic Modeling

Topic modeling assumes that:

- Each document contains multiple topics
    
- Each topic contains multiple words
    

Example:

A document about “Cricket World Cup” may have:

Topic 1: Sports  
Topic 2: Team  
Topic 3: Tournament

So one document can belong to many topics.

---

# Latent Dirichlet Allocation (LDA)

## What is LDA

LDA stands for Latent Dirichlet Allocation.

It is the most popular algorithm for topic modeling.

LDA is a probabilistic model that finds topics from text data.

“Latent” means hidden  
“Dirichlet” is a probability distribution  
“Allocation” means assigning topics

So:

LDA finds hidden topics and assigns them to documents.

---

## Main Idea of LDA

LDA assumes that:

1. Each document is a mixture of topics
    
2. Each topic is a mixture of words
    

In simple words:

- Document = combination of topics
    
- Topic = combination of words
    

Example:

Document: “AI and Data Science”

Topic 1 (AI): model, learning, neural  
Topic 2 (Data): data, analysis, mining

Document = 60% Topic 1 + 40% Topic 2

---

## Probabilistic View of LDA

LDA works using probability.

It tries to find:

- Probability of topic in a document
    
- Probability of word in a topic
    

So it learns:

P(Topic | Document)  
P(Word | Topic)

---

## Generative Process of LDA (How LDA Thinks)

LDA assumes that documents are created like this:

Step 1: Choose topic distribution for document  
Step 2: Choose a topic from that distribution  
Step 3: Choose a word from that topic  
Step 4: Repeat for all words

This is called the generative process.

It means LDA imagines how text was generated.

---

## Important Terms in LDA

### Document-Topic Distribution (θ)

Shows how much each topic appears in a document.

Example:

Document 1:

- Topic 1: 0.5
    
- Topic 2: 0.3
    
- Topic 3: 0.2
    

---

### Topic-Word Distribution (φ)

Shows how much each word belongs to a topic.

Example:

Topic: Sports

cricket: 0.2  
match: 0.15  
player: 0.1

---

### Dirichlet Distribution

Used to control topic and word probabilities.

Two parameters:

α (alpha): controls topic distribution  
β (beta): controls word distribution

High value → more spread  
Low value → more focused


---

# Applications of LDA

LDA is used in:

- News classification
    
- Research paper analysis
    
- Recommendation systems
    
- Customer feedback analysis
    
- Search engines
    
- Social media analysis
    

---

# Advantages of LDA

Advantages:

- Automatic topic discovery
    
- Works on large text data
    
- No need for manual labeling
    
- Easy to interpret topics
    

---

# Limitations of LDA

Limitations:

- Needs good preprocessing
    
- Number of topics must be chosen manually
    
- Topics may be unclear
    
- Not good for very short text
    

---

# Comparison: Topic Modeling vs Text Classification

## Key Differences

|Feature|Topic Modeling (LDA)|Text Classification|
|---|---|---|
|Labels|Not required|Required|
|Type|Unsupervised|Supervised|
|Output|Topics|Classes|
|Purpose|Discover themes|Predict category|


---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 3/NLP/Unit 1 & 2/","created":"2026-02-19T21:52:04.270+05:30"}
---



## 1. Text Mining — 5 Marks Answer
**Definition**  
Text Mining (also known as Text Data Mining or Text Analytics) is the process of extracting meaningful information, patterns, and insights from large volumes of unstructured text data using techniques from Natural Language Processing (NLP), Machine Learning, and Statistics.
It enables computers to analyze textual content such as reviews, emails, social media posts, and documents automatically.
### Key Steps in Text Mining Process
1. **Text Collection**  
    Gathering raw text data from sources like websites, reviews, social media, emails, etc.
2. **Text Preprocessing**  
    Cleaning the text by removing stop words, punctuation, special characters, and converting text to lowercase.
3. **Tokenization**  
    Breaking text into smaller units such as words or sentences.
4. **Stemming / Lemmatization**  
    Reducing words to root form  
    Example: _Running → Run_
5. **Feature Extraction**  
    Converting text into numerical form using techniques like Bag-of-Words or TF-IDF.
6. **Modeling / Analysis**  
    Applying algorithms such as sentiment analysis, classification, clustering, or topic modeling.
7. **Visualization & Interpretation**  
    Presenting insights using charts, dashboards, or reports.

### Applications of Text Mining
- Customer sentiment analysis (Amazon, Flipkart reviews)
- Resume screening in recruitment
- Healthcare research analysis
- Financial market prediction
- Legal document analysis

---
### Key Challenges
- Unstructured and noisy text data
- Context ambiguity (e.g., “bank”)
- Multilingual / code-mixed language
- Sarcasm detection
- Privacy and ethical issues

---
## 2. Natural Language Processing (NLP) — 5 Marks Answer

**Definition**  
Natural Language Processing (NLP) is a subfield of Artificial Intelligence (AI) that focuses on enabling computers to read, understand, interpret, and generate human language in a meaningful way.  
It combines linguistics, computer science, and machine learning to process large volumes of natural language data.

---
### Key Tasks in NLP

1. **Tokenization**  
    Breaking text into words or sentences.  
    _Example:_ “I love NLP” → [I, love, NLP]
    
2. **Part-of-Speech (POS) Tagging**  
    Identifying grammatical roles such as noun, verb, adjective.
    
3. **Named Entity Recognition (NER)**  
    Detecting entities like person names, locations, organizations.
    
4. **Sentiment Analysis**  
    Determining opinion polarity (positive / negative / neutral).
    
5. **Machine Translation**  
    Converting text from one language to another.
    
6. **Speech Recognition**  
    Converting spoken language into text.
    

---

### Applications of NLP

- Chatbots and Virtual Assistants
- Spam Email Filtering
- Language Translation
- Text Summarization
- Social Media Sentiment Analysis
- Search Engines / Information Retrieval

---

### Advantages
- Automates language processing tasks
- Improves customer service (chatbots)
- Enables multilingual communication
- Analyzes large unstructured datasets

---

### Limitations
- Difficulty understanding context & sarcasm 
- Language ambiguity
- Data privacy concerns
- Computationally expensive models

---

**Conclusion**  
NLP bridges the gap between human communication and computer understanding, enabling intelligent language-based applications across industries.

---

## 3. Applications of NLP in Various Domains — 5 Marks Answer
Natural Language Processing (NLP) is a subfield of Artificial Intelligence (AI) that focuses on enabling computers to read, understand, interpret, and generate human language in a meaningful way.  

Natural Language Processing (NLP) is widely used across multiple domains to process, analyze, and generate human language data efficiently.
### 1. Healthcare
* Analyzes clinical notes, medical records, and research papers.
* Assists in disease diagnosis and treatment recommendations.
* Example: Extracting symptoms from patient reports.
### 2. Banking & Finance
* Performs sentiment analysis on financial news and social media.
* Detects fraud and monitors customer communications.
* Supports automated report analysis and risk assessment.
### 3. E-Commerce & Marketing
* Analyzes customer reviews and feedback.
* Powers product recommendations and chatbots.
* Helps in brand sentiment tracking.
### 4. Education
* Enables automated grading and feedback systems.
* Supports language translation and learning apps.
* Provides text summarization for study materials.
### 5. Customer Service / Business Operations
* Chatbots and virtual assistants handle customer queries 24/7.
* Automates email classification and response generation.
* Improves service efficiency and response time.

### 6. Legal Domain
* Reviews contracts and legal documents.
* Extracts clauses, case references, and legal risks.
* Reduces manual document analysis time.
### Conclusion
NLP applications span healthcare, finance, education, e-commerce, legal, and customer service sectors, improving automation, decision-making, and user experience.

---
## 4. Key Challenges in Text Mining — 5 Marks (Simple Answer)

### 1. Unstructured and Noisy Data

Text data does not follow a fixed format. 
It may contain typos, slang, emojis, and abbreviations.  
_Example:_ “Prodct is gr8!!! 🔥” → Hard for systems to interpret directly.

---
### 2. Language Ambiguity
Words can have multiple meanings depending on context.  
_Example:_ “Bank” can mean a financial institution or riverbank.

---
### 3. Multilingual and Code-Mixed Text
Text may contain multiple languages in one sentence.  
_Example:_ “Aaj meeting boring thi” (Hindi + English).  
This complicates analysis.

---
### 4. High Dimensionality
Each unique word becomes a feature, creating thousands of variables, which increases computational complexity and may affect model performance.

---
### 5. Sarcasm and Sentiment Misinterpretation
Sarcastic text is difficult to analyze correctly.  
_Example:_ “Great, another delay 🙄” → Negative sentiment despite positive word.
### Conclusion

Handling unstructured data, ambiguity, multilingual text, high dimensionality, and sarcasm are major challenges that make text mining complex.


# ## 5. Introduction to Python Libraries for NLP — NLTK & spaCy (5 Marks)

Python provides powerful libraries for Natural Language Processing. Two of the most commonly used are **NLTK** and **spaCy**.

---

# 1. NLTK (Natural Language Toolkit)

**Definition**
NLTK is one of the oldest and most widely used Python libraries for NLP. It is mainly used for **education, research, and prototyping**.

**Key Features**

**• Text Preprocessing (Tokenization, Stopword Removal):**  Cleaning and preparing raw text by splitting it into words and removing common unnecessary words.

**• Stemming and Lemmatization:**  Reducing words to their root or base form to standardize text.

**• POS Tagging (Part-of-Speech Tagging):**  Identifying the grammatical role of each word in a sentence (noun, verb, adjective, etc.).

**• Sentiment Analysis:** Determining whether the expressed opinion in text is positive, negative, or neutral.

**• Access to Linguistic Datasets (WordNet, Corpora):**  Providing prebuilt language databases for vocabulary, meanings, and text analysis.

**Advantages**
* Beginner-friendly
* Large number of tutorials
* Rich linguistic resources

**Limitation**
* Slower for large-scale / production workloads

**Simple Example (Tokenization in NLTK)**

```python
import nltk
from nltk.tokenize import word_tokenize

text = "I love learning NLP"
tokens = word_tokenize(text)

print(tokens)
```

**Output:**
`['I', 'love', 'learning', 'NLP']`

---

# 2. spaCy
**Definition**
spaCy is a modern, industrial-strength NLP library designed for **high performance and production use**.
**Key Features**
**Fast tokenization** – Quickly splitting text into words or sentences with high processing speed.

**POS tagging** – Assigning grammatical labels (noun, verb, adjective, etc.) to each word.

**Dependency parsing** – Analyzing grammatical relationships between words in a sentence.

**Word vectors** – Representing words as numerical vectors based on their meanings and context.

**Pretrained deep learning models** – Ready-made NLP models trained on large datasets for tasks like NER, tagging, and classification.

**Advantages**
* Very fast and efficient
* Accurate pretrained models
* Suitable for real-time apps

**Limitation**
* Less beginner teaching material than NLTK
* Fewer built-in linguistic datasets

**Simple Example (Tokenization in spaCy)**

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("I love learning NLP")

for token in doc:
    print(token.text)
```

**Output:**
I
love
learning
NLP

---

# Difference Between NLTK and spaCy

| Feature              | NLTK                  | spaCy                      |
| -------------------- | --------------------- | -------------------------- |
| Purpose              | Education & research  | Production & industry      |
| Speed                | Slower                | Faster                     |
| Ease for beginners   | Very easy             | Moderate                   |
| Pretrained models    | Limited               | Strong                     |
| Linguistic resources | Extensive             | Limited                    |
| Use case             | Learning NLP concepts | Building real applications |

---

# Simple Practical Distinction Example

**Task:** Named Entity Recognition

**Sentence:**
“Apple is hiring in Mumbai.”

* **NLTK:** Requires multiple steps and manual setup.
* **spaCy:** Detects entities directly.

spaCy output:

* Apple → Organization
* Mumbai → Location

---

## Conclusion

* **NLTK** → Best for learning, experimentation, and academic work.
* **spaCy** → Best for fast, scalable, real-world NLP systems.

---

# Unit 2

## 1. Tokenization in NLP — 5 Marks Answer (Simple)

**Definition**  
Tokenization is a basic preprocessing step in Natural Language Processing (NLP) that involves breaking down text into smaller units called **tokens**.  
Tokens can be words, sentences, or characters, which help machines understand and analyze text easily.

---

### Types of Tokenization

**1. Word Tokenization**  
Splits text into individual words.  
_Example:_  
Input: “NLP is interesting”  
Output: [NLP, is, interesting]

**2. Sentence Tokenization**  
Divides text into sentences.  
_Example:_  
Input: “NLP is fun. It is useful.”  
Output: [“NLP is fun.”, “It is useful.”]

**3. Character Tokenization**  
Breaks text into characters.  
_Example:_  
Input: “Hello” → [H, e, l, l, o]

**4. Subword Tokenization**  
Splits words into smaller meaningful units.  
_Example:_  
“unhappiness” → [un, happiness]

---

### Importance of Tokenization
- Converts raw text into structured format
- Helps in word frequency analysis
- Prepares input for NLP models
---

### Simple Code Snippet Example (Word Tokenization — Python NLTK)

```python
from nltk.tokenize import word_tokenize

text = "NLP is interesting"
tokens = word_tokenize(text)

print(tokens)
```

**Output:**  
`['NLP', 'is', 'interesting']`

---

**Conclusion**  
Tokenization is the first and essential step in NLP that converts text into smaller units for further processing and analysis.

---

## 2. Stemming in NLP — Strict 5 Marks Answer (Simple)

**Definition**  
Stemming is a text normalization technique in Natural Language Processing (NLP) that reduces words to their root or base form by removing prefixes and suffixes.

The root word produced may not always be a valid dictionary word but represents the core meaning.

---

### Examples
- Running → Run
- Jumps → Jump
- Happiness → Happi

### Common Stemming Algorithms
1. **Porter Stemmer** – Most widely used rule-based stemmer.
2. **Lancaster Stemmer** – More aggressive; produces shorter roots.
3. **Snowball Stemmer** – Improved and faster version of Porter.
---

### Importance of Stemming

- Reduces vocabulary size
- Groups similar word forms together
- Improves search and information retrieval
- Enhances text classification and sentiment analysis

---
### Limitation
- Root word may be incorrect or meaningless  
    Example: _Happiness → Happi_
---

**Conclusion**  
Stemming simplifies text by converting word variations into a common root form, improving efficiency in NLP tasks.

---
## 3. Lemmatization in NLP — Strict 5 Marks Answer (Simple)

**Definition**  
Lemmatization is a text normalization technique in Natural Language Processing (NLP) that reduces words to their base or dictionary form called a **lemma**.

Unlike stemming, lemmatization returns a **valid meaningful word** based on context and part of speech (POS).

---

### Examples
- Running → Run
- Cats → Cat
- Better → Good
- Are → Be

---
### Key Features
- **Context-aware** — Considers word meaning
- **Uses POS tagging** for accuracy
- Produces valid dictionary words
- More accurate but slower than stemming
---
### Lemmatization Process
1. Identify the word’s Part of Speech (noun, verb, etc.)
2. Apply dictionary / WordNet rules
3. Return base form (lemma)

---
### Applications
- Search engines
- Sentiment analysis
- Text classification
- Machine translation
---

### Simple Code Snippet (NLTK)

```python
from nltk.stem import WordNetLemmatizer

lemmatizer = WordNetLemmatizer()
print(lemmatizer.lemmatize("running", "v"))
```

**Output:**  
`run`

---

**Conclusion**  
Lemmatization converts words into meaningful base forms while preserving context, making it more accurate for NLP analysis.

---

## Distinguish Between Stemming and Lemmatization — 5 Marks

| Basis                 | Stemming                                                 | Lemmatization                                 |
| --------------------- | -------------------------------------------------------- | --------------------------------------------- |
| Definition            | Reduces words to root form by removing prefixes/suffixes | Reduces words to dictionary base form (lemma) |
| Root Word             | May not be a valid word                                  | Always a meaningful valid word                |
| Method Used           | Rule-based cutting                                       | Uses vocabulary + POS tagging                 |
| Context Consideration | Does not consider context                                | Considers context & meaning                   |
| Accuracy              | Less accurate                                            | More accurate                                 |
| Speed                 | Faster                                                   | Slower                                        |
| Example 1             | Running → Run                                            | Running → Run                                 |
| Example 2             | Happiness → Happi                                        | Happiness → Happy                             |
| Example 3             | Better → Better                                          | Better → Good                                 |
| Complexity            | Simple process                                           | Computationally complex                       |

---

## 4. Python Libraries for NLP — 5 Marks Answer (Simple)

Python provides several libraries that help computers process and analyze human language efficiently.

### 1. NLTK (Natural Language Toolkit)
Used for learning and research in NLP.  
Supports tokenization, stopword removal, stemming, and POS tagging.

### 2. spaCy
An industrial-level NLP library used for real-time applications.  
Provides fast tokenization, Named Entity Recognition (NER), and dependency parsing.

### 3. TextBlob
A simple library for beginners.  
Used for sentiment analysis, translation, and basic text processing.

### 4. Transformers (Hugging Face)
Provides pretrained deep learning models like BERT and GPT.  
Used for text classification, summarization, and question answering.

### 5. Gensim

Mainly used for topic modeling and document similarity.  
Supports Word2Vec and Doc2Vec embeddings.

### 6. TF-IDF Vectorizer (Scikit-learn)

Converts text into numerical feature vectors.  
Widely used in machine learning models for text classification.

### Conclusion

These libraries simplify NLP tasks such as preprocessing, analysis, modeling, and feature extraction, enabling efficient language processing.

---
Understood. You want **exam-ready theory answers** for _Python NLP libraries_ — keeping:

- Key features
    
- Very basic code snippet
    
- Simple language
    
- Strict 5-mark length
    

Below is a clean, theory-paper format answer.

---

# 5. Python Libraries for NLP (Natural Language Processing)

## 1. NLTK (Natural Language Toolkit) — (5 Marks)

**Definition:**  
NLTK is one of the oldest and most widely used Python libraries for Natural Language Processing. It is mainly used for learning, research, and text preprocessing tasks.

**Key Features:**

- Tokenization (word/sentence splitting)
    
- Stopword removal
    
- Part-of-Speech (POS) tagging
    
- Named Entity Recognition (basic)
    
- Stemming and Lemmatization
    
- Large text corpora support
    

**Basic Example:**

```python
import nltk
from nltk.tokenize import word_tokenize

nltk.download('punkt')

text = "Text mining is amazing!"
tokens = word_tokenize(text)

print(tokens)
# Output: ['Text', 'mining', 'is', 'amazing', '!']
```

**Use Case:** Academic projects, preprocessing pipelines.

---

## 2. spaCy — (5 Marks)

**Definition:**  
spaCy is an industry-ready NLP library designed for fast and efficient text processing with pretrained models.

**Key Features:**

- Pretrained language models
    
- Fast tokenization
    
- POS tagging
    
- Dependency parsing
    
- Named Entity Recognition (NER)
    
- Production-grade pipelines
    

**Basic Example:**

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("Apple is looking at buying a U.K. startup")

for ent in doc.ents:
    print(ent.text, ent.label_)
```

**Output Example:**  
Apple – ORG  
U.K. – GPE

**Use Case:** Chatbots, production NLP systems.

---

## 3. TextBlob — (5 Marks)

**Definition:**  
TextBlob is a simple NLP library built on top of NLTK and Pattern, mainly used for quick NLP tasks.

**Key Features:**

- Easy API
    
- Sentiment analysis
    
- Language translation
    
- POS tagging
    
- Noun phrase extraction
    

**Basic Example:**

```python
from textblob import TextBlob

blob = TextBlob("I love natural language processing!")
print(blob.sentiment)
```

**Output:**  
Sentiment(polarity=0.5, subjectivity=0.6)

**Use Case:** Quick sentiment analysis, prototypes.

---

## 4. Transformers (Hugging Face) — (5 Marks)

**Definition:**  
Transformers is a deep-learning NLP library providing access to pretrained transformer models like BERT, GPT, RoBERTa.

**Key Features:**

- State-of-the-art models
    
- Text classification
    
- Question answering
    
- Summarization
    
- Translation
    
- Hugging Face model hub
    

**Basic Example:**

```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")
result = classifier("Text mining is revolutionizing data analysis!")

print(result)
```

**Output Example:**  
[{'label': 'POSITIVE', 'score': 0.999}]

**Use Case:** Advanced AI applications, deep learning NLP.

---

## 5. Gensim — (5 Marks)

**Definition:**  
Gensim is a library used for topic modeling, document similarity, and word embeddings.

**Key Features:**

- Word2Vec, Doc2Vec
    
- Topic modeling (LDA)
    
- TF-IDF modeling
    
- Large corpus processing
    
- Semantic similarity
    

**Basic Example:**

```python
from gensim.models import Word2Vec

sentences = [["text", "mining", "is", "cool"],
             ["nlp", "is", "fun"]]

model = Word2Vec(sentences, vector_size=50, min_count=1)

print(model.wv["mining"])
```

**Output:** Vector representation of word “mining”.

**Use Case:** Topic discovery, similarity analysis.

---

## 6. TF-IDF Vectorizer (Scikit-learn) — (5 Marks)

**Definition:**  
TF-IDF Vectorizer converts text into numerical feature vectors for machine learning models.

**Key Features:**

- Text → numeric vectors
    
- Weighs important words higher
    
- Used in classification & clustering
    
- Removes common word bias
    

**Basic Example:**

```python
from sklearn.feature_extraction.text import TfidfVectorizer

corpus = ["Text mining is fun",
          "NLP is powerful"]

vectorizer = TfidfVectorizer()
X = vectorizer.fit_transform(corpus)

print(vectorizer.get_feature_names_out())
```

**Output:**  
['fun' 'is' 'mining' 'nlp' 'powerful' 'text']

**Use Case:** Spam detection, document classification.

---

## Quick Revision Table (Exam Use)

|Library|Best For|Key Strength|
|---|---|---|
|NLTK|Learning & preprocessing|Linguistic tools|
|spaCy|Production NLP|Speed + pipelines|
|TextBlob|Quick tasks|Sentiment & translation|
|Transformers|Deep learning NLP|BERT, GPT models|
|Gensim|Topic modeling|Word embeddings|
|TF-IDF|Feature extraction|Text → vectors|

---
# 7. Stop Word Removal in NLP — (5 Marks)

**Definition:**  
Stop words are very common words that occur frequently in text but carry little meaningful information. Examples include: _the, is, and, at, on, which_. They usually do not help models understand the core meaning of a sentence.

---

**Why Stop Word Removal is Done:**

1. **Reduces Noise** — Removes irrelevant words.
    
2. **Improves Processing Speed** — Less text to process.
    
3. **Shrinks Vocabulary Size** — Fewer unique words.
    
4. **Better Feature Quality** — Helps TF-IDF, Word2Vec focus on important terms.
    

_Note:_ Stop words should not always be removed. Example:  
“The movie was **not** good.” → Removing _not_ changes sentiment.

---

**Example:**

Sentence: “The quick brown fox jumps over the lazy dog.”

After tokenization:  
[The, quick, brown, fox, jumps, over, the, lazy, dog]

After stop word removal:  
[quick, brown, fox, jumps, over, lazy, dog]

---

**How Libraries Remove Stop Words:**

**1. NLTK**

```python
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

stop_words = set(stopwords.words("english"))
words = word_tokenize("The quick brown fox jumps over the lazy dog")

filtered = [w for w in words if w.lower() not in stop_words]
print(filtered)
```

---

**2. spaCy**

```python
import spacy
nlp = spacy.load("en_core_web_sm")

doc = nlp("The quick brown fox jumps over the lazy dog")
filtered = [token.text for token in doc if not token.is_stop]
print(filtered)
```

---

**Conclusion:**  
Stop word removal cleans text by removing frequent low-value words, improving efficiency and model performance, but must be applied carefully depending on the NLP task.

---
Here is your **Text Normalization in NLP** rewritten into a **strict 5-marks, simple, exam-ready theory answer** (with key techniques + small snippet).

---

# 8. Text Normalization in NLP — (5 Marks)

**Definition:**  
Text normalization is the process of converting raw, inconsistent text into a standard and uniform format so that machines can understand and process it effectively. It reduces variation in words such as “USA”, “U.S.A.”, and “United States”.

---

**Why Text Normalization is Important:**

1. Reduces vocabulary size
    
2. Removes redundancy in text
    
3. Improves model accuracy
    
4. Helps in sentiment analysis, classification, translation
    
5. Handles noisy data (social media, speech text)
    

---

**Key Techniques of Text Normalization:**

1. **Lowercasing:**  
    “HELLO World” → “hello world”
    
2. **Expanding Contractions:**  
    “I’m happy” → “I am happy”
    
3. **Removing Punctuation/Special Characters:**  
    “NLP is fun!!!” → “NLP is fun”
    
4. **Stop Word Removal:**  
    Removes words like is, the, of
    
5. **Stemming:**  
    “connecting” → “connect”
    
6. **Lemmatization:**  
    “running” → “run” (valid root word)
    
7. **Whitespace Normalization:**  
    Removes extra spaces
    
8. **Numbers & Date Standardization:**  
    “5th Jan 2025” → “2025-01-05”
    
9. **Unicode/Accent Handling:**  
    “café” → “cafe”
    
10. **Slang & Microtext Normalization:**  
    “Thx brooo” → “Thanks bro”
    

---

**Benefits:**

- Improves model performance
    
- Speeds up training
    
- Ensures consistency
    
- Works better on multilingual/noisy data
    

**Limitation:**  
Over-normalization may remove useful meaning (e.g., “not”, “!!!”).

---

**Basic Python Example:**

```python
import re
text = "Dogs are RUNNING quickly!!!"

# Lowercase
text = text.lower()

# Remove special characters
text = re.sub(r'[^a-z\s]', '', text)

print(text)
# Output: dogs are running quickly
```

---

**Conclusion:**  
Text normalization standardizes and cleans raw text, making NLP models more accurate, efficient, and easier to train.


Here is **Text Cleaning in NLP** converted into a **strict 5-marks, simple, exam-ready theory answer** with key points + small snippet.

---

# 9. Text Cleaning in NLP — (5 Marks)

**Definition:**  
Text cleaning is the process of removing errors, noise, and inconsistencies from raw text to make it suitable for Natural Language Processing (NLP) tasks.

Raw text may contain spelling mistakes, symbols, mixed cases, and unwanted characters which reduce model performance.

---

## Importance of Text Cleaning

1. Improves model accuracy
    
2. Reduces noise in datasets
    
3. Standardizes text format
    
4. Enhances processing efficiency
    
5. Helps machines interpret text correctly
    

---

## Key Components of Text Cleaning

### 1. Handling Misspellings

Misspelled words create different tokens (e.g., _enviroment_ vs _environment_).

**Techniques:**

- **Dictionary-based correction:** teh → the
    
- **Edit Distance (Levenshtein):** measures character edits
    
- **Phonetic algorithms:** Soundex, Metaphone
    
- **Contextual correction:** ML models (e.g., BERT)
    

Example: “I like to reed books” → “read”

---

### 2. Handling Special Characters

Text may contain symbols, emojis, HTML tags, etc.

**Techniques:**

- Remove punctuation & symbols
    
- Remove HTML/XML tags
    
- Preserve useful symbols (#AI, @user, emojis)
    
- Use Regex for pattern cleaning
    

Example regex:  
`re.sub(r'[^a-zA-Z0-9 ]','', text)`

---

### 3. Case Normalization

Different cases create different tokens.

Example: Apple ≠ apple

**Techniques:**

- Lowercasing (most common)
    
- Uppercasing (rare)
    
- Truecasing (restore original case when needed)
    

Example: “NLP is FUN” → “nlp is fun”

---

## Best Practices

- Combine spelling correction + symbol cleaning + case normalization
    
- Customize cleaning per task:
    
    - Sentiment → keep emojis
        
    - NER → preserve case
        
    - Classification → lowercase text
        

---

## Basic Python Example

```python
import re
from textblob import TextBlob

text = "Thiss is a smaple! Textt with SPECIAL char$."

# Lowercase
text = text.lower()

# Remove special characters
text = re.sub(r'[^a-zA-Z0-9\s]', '', text)

# Spell correction
text = str(TextBlob(text).correct())

print(text)
```

**Output:**  
“this is a sample text with special char”

---

**Conclusion:**  
Text cleaning removes spelling errors, unwanted symbols, and case inconsistencies, producing clean and standardized text for better NLP model performance.

---
# 11. Bag of Words (BoW) Model in NLP — (5 Marks)

**Definition:**  
Bag of Words (BoW) is a text representation technique in NLP that converts text into numerical vectors by counting the frequency of words. It treats text as a “bag” of words, ignoring grammar and word order.

Example:  
“I love programming” = “Programming I love” (same BoW representation)

---

## Steps to Build BoW

1. **Tokenization:**  
    Split sentences into words.  
    Example: “I love coding” → [I, love, coding]
    
2. **Create Vocabulary:**  
    Collect all unique words from documents.
    
3. **Vectorization:**  
    Convert each document into a frequency vector based on vocabulary.
    

---

## Basic Python Example

```python
from sklearn.feature_extraction.text import CountVectorizer

corpus = [
    "I love data",
    "I love coding",
    "data is fun"
]

vectorizer = CountVectorizer()
X = vectorizer.fit_transform(corpus)

print(vectorizer.get_feature_names_out())
print(X.toarray())
```

---

## Advantages

1. Simple and easy to implement
    
2. Works well for text classification
    
3. Interpretable word frequencies
    

---

## Limitations

1. Ignores word order
    
2. Produces high-dimensional sparse vectors
    
3. Cannot capture meaning or synonyms
    

---

## Applications

- Spam detection
    
- Sentiment analysis
    
- Document classification
    
- Information retrieval
    

---

**Conclusion:**  
BoW is a foundational NLP technique that converts text into word-frequency vectors. Though simple, it is effective for many basic NLP tasks and forms the base for advanced methods like TF-IDF and embeddings.

---
Understood. Below are **all three answers** written in **strict 5-marks format**, simple language, theory-paper ready, with key points + very basic snippet where useful.

---

# 1. TF-IDF (Term Frequency – Inverse Document Frequency) — (5 Marks)

**Definition:**  
TF-IDF is a text feature extraction technique that measures how important a word is in a document relative to a collection of documents (corpus).

It improves Bag of Words by reducing the weight of very common words and increasing the weight of rare, meaningful words.

---

## Components

1. **Term Frequency (TF):**  
   Number of times a word appears in a document.

2. **Inverse Document Frequency (IDF):**  
   Measures how rare the word is across all documents.

Formula (concept):  
TF-IDF = TF × IDF

---

## Importance

- Reduces importance of common words (the, is)  
- Highlights discriminative terms  
- Improves classification accuracy  

---

## Basic Python Example

```python
from sklearn.feature_extraction.text import TfidfVectorizer

corpus = ["NLP is fun", "NLP is powerful"]

vectorizer = TfidfVectorizer()
X = vectorizer.fit_transform(corpus)

print(vectorizer.get_feature_names_out())
```

---

**Conclusion:**  
TF-IDF converts text into weighted numerical vectors, emphasizing important words and improving machine learning performance.

---

# 2. Word Embeddings — (5 Marks)

**Definition:**  
Word embeddings are dense vector representations of words where similar words have similar numerical representations based on context.

Unlike BoW, embeddings capture semantic meaning and relationships.

Example:  
“King – Man + Woman ≈ Queen”

---

## Key Characteristics

1. Dense low-dimensional vectors  
2. Capture semantic similarity  
3. Context-based representation  
4. Learned using neural networks  

---

## Popular Models

- Word2Vec  
- GloVe  
- FastText  

---

## Basic Python Example

```python
from gensim.models import Word2Vec

sentences = [["nlp", "is", "fun"], ["machine", "learning", "fun"]]

model = Word2Vec(sentences, vector_size=50, min_count=1)
print(model.wv["nlp"])
```

---

**Advantages:**

- Captures meaning and synonyms  
- Better than BoW/TF-IDF for semantics  

**Conclusion:**  
Word embeddings represent words as meaningful vectors, enabling machines to understand relationships and context.

---

# 3. Document & Sentence Embeddings — (5 Marks)

**Definition:**  
Document and sentence embeddings extend word embeddings by representing an entire sentence or document as a single dense vector capturing overall meaning.

---

## Purpose

- Compare similarity between texts  
- Clustering and classification  
- Search and recommendation systems  

---

## How They Are Created

1. **Averaging word embeddings**  
2. **Doc2Vec model**  
3. **Transformer models (BERT, SBERT)**  

---

## Characteristics

- Dense vectors  
- Capture context and semantics  
- Represent full text meaning  

---

## Basic Example (Conceptual)

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer('all-MiniLM-L6-v2')

emb = model.encode("NLP is interesting")
print(emb)
```

---

**Applications:**

- Semantic search  
- Document clustering  
- Text similarity  

---

**Conclusion:**  
Sentence and document embeddings provide holistic vector representations of text, enabling advanced NLP tasks based on meaning rather than just word counts.

---

If you want, I can compile:

- **BoW vs TF-IDF vs Embeddings — comparison (5/10 marks)**  
- **Full Feature Extraction unit revision notes**  
- **Important diagrams to draw in exam**
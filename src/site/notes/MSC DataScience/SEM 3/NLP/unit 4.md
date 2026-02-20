---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 3/NLP/unit 4/","created":"2026-02-20T06:31:45.231+05:30"}
---


# Unit 4: Advanced NLP Techniques and Transformer Models

# Recurrent Neural Networks (RNNs)

## What is RNN

Recurrent Neural Network (RNN) is a type of neural network designed to work with **sequence data**.

Sequence data means data where order matters.

Examples:

- Sentences
    
- Speech
    
- Time-series data
    

RNN remembers previous information while processing new input.

So, it is useful for language tasks.

---

## Main Idea of RNN

RNN processes data step by step.

At each step, it uses:

- Current input
    
- Previous memory
    

This helps RNN understand context.

Example:

In sentence  
"I am learning AI"

To understand "AI", the model remembers "I am learning".

---

## Working of RNN

RNN has a loop structure.

Output depends on:

- Current word
    
- Previous hidden state
    

So information flows from past to present.

---

## Advantages and Limitations

Advantages:

- Handles sequential data
    
- Remembers past information
    
- Useful for language modeling
    

Limitations:

- Cannot remember long sentences well
    
- Suffers from vanishing gradient problem
    
- Training is slow
    

---

# Long Short-Term Memory (LSTM)

## What is LSTM

Long Short-Term Memory (LSTM) is a special type of RNN.

It is designed to solve the memory problem of RNN.

LSTM can remember important information for a long time.

---

## Why LSTM is Needed

Normal RNN forgets old information quickly.

Example:

In a long paragraph, RNN may forget the starting words.

LSTM solves this by using memory cells and gates.

---

## Main Components of LSTM

LSTM has three main gates:

1. Forget Gate  
    Decides what information to remove
    
2. Input Gate  
    Decides what new information to store
    
3. Output Gate  
    Decides what information to send out
    

These gates control memory flow.

---

## Working of LSTM

LSTM keeps a memory cell.

It updates this memory using gates.

Important information is kept.  
Unimportant information is removed.

This makes LSTM powerful for long texts.

---

## Advantages and Limitations

Advantages:

- Remembers long sequences
    
- Better than RNN
    
- High accuracy in NLP tasks
    

Limitations:

- More complex
    
- Slower than RNN
    
- Needs more computation
    

---

# Implementation using Keras and TensorFlow

## Keras and TensorFlow

TensorFlow is a deep learning framework.

Keras is a high-level library built on TensorFlow.

They are used to build neural networks easily.

---

## Purpose of Using Keras and TensorFlow

They help to:

- Build models quickly
    
- Train large datasets
    
- Test and deploy models
    
- Reduce coding complexity
    

---

## Basic Steps of Implementation

1. Import libraries
    
2. Prepare text data
    
3. Convert text to numbers (tokenization)
    
4. Build RNN/LSTM model
    
5. Compile model
    
6. Train model
    
7. Test model
    

---

## Example Use

Using Keras, we can easily create:

- RNN for text prediction
    
- LSTM for sentiment analysis
    
- Language translation models
    

---

# Introduction to Transformers (BERT, GPT)


## What is Transformer

Transformer is a modern deep learning model used in NLP.

It does not use RNN or LSTM.

Instead, it uses **attention mechanism**.

Attention helps the model focus on important words.

---

## Main Idea of Transformers

Transformers process all words at the same time.

They find relationships between words using attention.

So they are:

- Faster
    
- More accurate
    
- Better at understanding context
    

---

## Attention Mechanism

Attention tells the model:

“Which words are important for this word?”

Example:

"I went to bank to deposit money"

Attention helps understand that "bank" means financial bank.

---

## BERT and GPT

BERT:

- Reads text from both sides (left and right)
    
- Good for understanding meaning
    

GPT:

- Reads text from left to right
    
- Good for generating text
    

Both are based on transformers.

---

## Advantages of Transformers

- Handle long text easily
    
- High accuracy
    
- Parallel processing
    
- Better context understanding
    

---

# Pre-trained Models and Fine-Tuning

## Pre-trained Models

Pre-trained models are models trained on huge datasets.

They already know:

- Grammar
    
- Vocabulary
    
- Language patterns
    

Examples:

- BERT
    
- GPT
    
- RoBERTa
    

---

## Why Pre-trained Models are Used

Training from scratch needs:

- Huge data
    
- High cost
    
- Long time
    

Pre-trained models save time and money.

---

## Fine-Tuning

Fine-tuning means:

Using a pre-trained model and training it again on your own data.

Only small changes are made.

So the model learns your specific task.

---

## Process of Fine-Tuning

1. Load pre-trained model
    
2. Add task-specific layer
    
3. Train on new dataset
    
4. Adjust weights slightly
    
5. Test performance
    

---

## Advantages of Fine-Tuning

- Requires less data
    
- Faster training
    
- Better accuracy
    
- Easy implementation
    

---

# Comparison of RNN, LSTM, and Transformers

## Key Differences

|Feature|RNN|LSTM|Transformer|
|---|---|---|---|
|Memory|Short|Long|Very Long|
|Speed|Slow|Slower|Fast|
|Structure|Sequential|Sequential|Parallel|
|Accuracy|Medium|High|Very High|
|Used Today|Rare|Limited|Very Common|

---

# One-Line Summary for Exam

RNN processes sequential data using memory, LSTM improves RNN by storing long-term information, transformers use attention for better context understanding, and pre-trained models with fine-tuning provide high accuracy with less data.

---

# Memory Shortcut

RNN → Basic memory  
LSTM → Strong memory  
Transformer → Attention power  
Pre-trained → Ready model  
Fine-tuning → Customize model

---
# BERT and GPT in Detail (Transformer-Based Models)

Both **BERT** and **GPT** are advanced NLP models based on the **Transformer architecture**.  
They are called **Large Language Models** because they are trained on very large text data.

They understand language using **attention mechanism** instead of RNN or LSTM.

---

# BERT (Bidirectional Encoder Representations from Transformers)

## What is BERT

BERT is a **Transformer-based model** designed mainly for **understanding text**.

Full form:  
Bidirectional Encoder Representations from Transformers

Meaning:

- Bidirectional → reads text from both sides
    
- Encoder → uses only encoder part of transformer
    
- Representations → creates meaning-based vectors
    

So, BERT understands words using **left and right context together**.

---

## Key Idea of BERT (Bidirectional Reading)

Traditional models read text in one direction.

Example sentence:

"I went to the bank to deposit money"

Unidirectional model:  
Reads only from left side.

BERT:  
Reads from both sides.

So it knows:

"bank" is related to "deposit" and "money"

This gives better understanding.

---

## Architecture of BERT

BERT uses:

- Transformer Encoder blocks
    
- Multi-head attention
    
- Feed-forward layers
    

Structure:

Input → Embedding → Encoder Layers → Output

It does not use decoder.

So BERT is mainly for **analysis and understanding**, not generation.

---

## Input Format of BERT

Before sending text to BERT, it is converted into special format.

Example:

[CLS] I love machine learning [SEP]

Where:

[CLS] → Classification token  
[SEP] → Separator token

BERT uses these tokens internally.

---

## Pre-Training of BERT

BERT is trained using two main tasks.

### 1. Masked Language Model (MLM)

Some words are hidden.

Example:

"I love [MASK] learning"

Model predicts missing word.

Output:  
"machine"

This helps BERT learn deep meaning.

---

### 2. Next Sentence Prediction (NSP)

Two sentences are given.

Model predicts:  
Are they related or not?

Example:

Sentence A: I am studying NLP  
Sentence B: It is very interesting

Related → Yes

This helps in question answering and reasoning.

---

## Working Principle of BERT

1. Input sentence is tokenized
    
2. Converted into embeddings
    
3. Passed through encoder layers
    
4. Attention connects related words
    
5. Final vectors represent meaning
    

Each word gets a context-aware vector.

---

## Applications of BERT

BERT is mainly used for:

- Question Answering
    
- Text Classification
    
- Named Entity Recognition
    
- Sentiment Analysis
    
- Document Search
    
- Text Similarity
    

It is best for tasks where **understanding is important**.

---

## Advantages of BERT

- Deep understanding of context
    
- Reads both sides
    
- High accuracy
    
- Works well for analysis tasks
    

---

## Limitations of BERT

- Cannot generate long text well
    
- Large size
    
- High memory usage
    
- Slower than GPT in generation
    

---

# GPT (Generative Pre-trained Transformer)

## What is GPT

GPT is a **Transformer-based model** designed mainly for **text generation**.

Full form:  
Generative Pre-trained Transformer

Meaning:

- Generative → creates text
    
- Pre-trained → trained on huge data
    
- Transformer → uses transformer architecture
    

So GPT is mainly used for **writing and generating language**.

---

## Key Idea of GPT (Unidirectional Reading)

GPT reads text from **left to right only**.

Example:

"I am learning artificial intelligence"

GPT predicts:

"I" → "am" → "learning" → "artificial" → "intelligence"

One word at a time.

This is called **autoregressive modeling**.

---

## Architecture of GPT

GPT uses:

- Transformer Decoder blocks
    
- Self-attention layers
    
- Feed-forward layers
    

Structure:

Input → Embedding → Decoder Layers → Output

It does not use encoder.

So GPT focuses on **generation**.

---

## Working Principle of GPT

GPT learns:

Given previous words, predict next word.

Example:

Input: "India is a"

Output: "country"

Then:

"India is a country"

Next prediction: "in"

This continues.

---

## Pre-Training of GPT

GPT is trained using:

Language Modeling Task

Formula:

Predict next word:

P(wₙ | w₁, w₂, ..., wₙ₋₁)

Meaning:  
Probability of next word depends on previous words.

It reads billions of sentences and learns patterns.

---

## Training Method of GPT

Step 1: Read huge text data  
Step 2: Learn grammar and structure  
Step 3: Learn writing style  
Step 4: Learn reasoning patterns

This makes GPT a general-purpose model.

---

## Fine-Tuning of GPT

After pre-training, GPT is fine-tuned for:

- Chatbots
    
- Coding
    
- Essay writing
    
- Question answering
    
- Translation
    

Fine-tuning adapts GPT to specific tasks.

---

## Applications of GPT

GPT is used for:

- Chat systems
    
- Content writing
    
- Story generation
    
- Code generation
    
- Summarization
    
- Virtual assistants
    

It is best for **creative and interactive tasks**.

---

## Advantages of GPT

- Generates human-like text
    
- Good at conversation
    
- Flexible usage
    
- Works for many tasks
    

---

## Limitations of GPT

- Can generate wrong information
    
- May be biased
    
- Needs large resources
    
- Not always reliable
    

---

# Comparison of BERT and GPT

## Key Differences

|Feature|BERT|GPT|
|---|---|---|
|Direction|Both sides|Left to right|
|Architecture|Encoder|Decoder|
|Main Use|Understanding|Generation|
|Best For|Analysis tasks|Writing tasks|
|Output|Labels, answers|Text|

---

# BERT vs GPT in Simple Words

BERT is good at:

Reading and understanding

GPT is good at:

Writing and generating

BERT = Reader  
GPT = Writer

---

# Role in Modern NLP

Today, most advanced NLP systems use:

- BERT-type models for analysis
    
- GPT-type models for generation
    

Many hybrid models combine both ideas.

Example:  
T5, BART, PaLM

---

# One-Line Summary for Exam

BERT is a bidirectional transformer model used for understanding text, while GPT is a unidirectional transformer model used for generating human-like language.

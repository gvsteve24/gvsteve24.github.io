---
layout: post
use_math: true
---
# Goal of This Course
* Natural language processing (NLP), which aims at properly understanding and generating human languages, emrges as a crucial application of artificial intelligence, with the advancements of deep neural networks.
* This course will cover various deep learning approaches as well as their applications such as language modeling, machine translation, question answering, document classification, and dialog systems.

# Academic Disciplines related to NLP

### **Natural language processing (major conferences: ACL, EMNLP, NAACL)**
- Includes state-of-the-art deep learning-based models and tasks
- Low-level parsing
    - Tokenization, stemming
- Word and phrase level
    - Named entity recognition(NER), part-of-speech(POS) tagging, noun-phrase chunking, dependency parsing, conference resolution
- Sentence level
    - Sentiment analysis, machine translation
- Multi-sentence and paragraph level
    -Entailment prediction, question answering, dialog systems, summrization

### **Text mining(major conferences: KDD, The WebConf (formerly,WWW), WSDM, CIKM, ICWSM)**
- Extract useful information and insights from text and document data
    - e.g., analyzing the trends of AI-related keywords from massive news data
- Document clustering (e.g., topic modeling)
    - e.g., clustering news data and grouping into different subjects
- Highly related to computational social science
    - e.g., analyzing the evolution of people's political tendency based on social media data
### **Information retrieval (major conference: SIGIR, WSDM, CIKM, RecSys)**
- **Highly related to computational social science**
    - This area is not actively studied now
    - It has evolved into a recommendation system, which is still an active area of research.

---

## Trend of NLP
- Text data can basically be viewd as a sequence of words, and **each word can be represented as a vector** through a techinque such as Word2Vec or GloVe.
- **RNN-family models**(LSTMs and GRUs), which take the sequence of these vectors of words as input, are the main architecture of NLP tasks.
- Overall performance of NLP tasks has been improved since attenttion modules and Transformer models, which replaced RNNs with self-attention, have been introduced a few years ago.
- As is the case for Transformer models, most of the advanced NLP models have been originally developed for improving machine translation tasks.
- In the early days, **customized models for different NLP tasks had developed separately.
- Since Transformer was introduced, huge models were released by stacking its basic module, self-attention, and these models are trained with large-sized datasets through language modeling tasks, one of the **self-supervised training setting that does not require additional labels** for a paricular task.
    - e.g., BERT, GPT-3,$\cdots$
- Afterwards, above models were applied to other tasks through **transfer learning**, and they outperformed all other customized models in each task.
- Currently, these models has now become essential part in numerous NLP tasks, so **NLP research become difficult with limited GPU resources**, since they are too large to train.

---
# Bag-of-Words

### Bag-of-Words Representation
* Step 1. Constructing the vocabulary containing unique words
    * Example sentences: "John really really loves this movie", "Jane really likes this song"
    * Vocabulary: {"John", "really", "loves", "this", "movie", "Jane", "likes", "song"}

* Step 2. Encoding unique words to one-hot vectors
    * Vocabulary: {"John", "really", "loves", "this", "movie", "Jane", "likes", "song"}
        * John: [1, 0, 0, 0, 0, 0, 0, 0]
        * really: [0, 1, 0, 0, 0, 0, 0, 0]
        * loves: [0, 0, 1, 0, 0, 0, 0, 0]
        * this: [0, 0, 0, 1, 0, 0, 0, 0]
        * movie: [0, 0, 0, 0, 1, 0, 0, 0]
        * Jane: [0, 0, 0, 0, 0, 1, 0, 0]
        * likes: [0, 0, 0, 0, 0, 0, 1, 0]
        * song: [0, 0, 0, 0, 0, 0, 0, 1]
    * For any pair of words, the distance is $\sqrt{2}$.
    * For any pair of words, cosine similarity is 0.

### Bag-of-Words Representation
---
* **A sentence/document can be represented as the sum of one-hot vectors**
    * Sentence 1: "John really really loves this movie"
        * John + really + really + loves + this + movie: [1 2 1 1 0 0 0]
    * Sentence 2: "Jane really likes this song"
        * Jane + really + likes + this + song:[0 1 0 1 0 1 1 1]

### NaiveBayes Classifier for Document Classification
---
### **Bag-of-Words for Document Classification**
![NaiveBayes](../images/NaiveBayes.png)

### **Bayes' Rule Applied to Documents and Classes**
![NaiveBayes-2](../images/NaiveBayes-2.png)

* For a document *d*, which consists of a sequence of words *w*, and a class *c*.
* The probability of a document can be represented by multiplying the probability of each word appearing
* $P(d\|c)P(c)=P(w_1, w_2,\dots w_n\|c)P(c) \to P(c)\Pi_{w_i \in W}P(w_i\|c)$(by conditional independence assumption)

* ### **Example**
    * For a document *d*, which consists of sequence of words *w*, and a class *c*. 

    ![NaiveBayes-3](../images/NaiveBayes-3.png)

    * For each word $w_i$ we can calculate conditional probability for class $c$
        * $P(w_k\|c_i)=\frac{n_k}{n}$, where n_k is occurrences of w_k in documents of topic c_i.

        ![NaiveBayes-4](../images/NaiveBayes-4.png)

    * ### **For a test document $d_5 = \text{"Classification task uses transformer"}$**
        * We calculate the conditional probability of the document for each class
        * We can choose a class that has the highest probability for the document
        - $P(c_{CV}\|d_5) = P(c_{CV})\Pi_{w_i \in W}P(w\|c_{CV}) = \frac{1}{2}\times \frac{1}{14}\times \frac{1}{14}\times \frac{1}{14}\times \frac{1}{14}\times = 0.00005$
        - $P(c_{NLP}\|d_5) = P(c_{NLP})\Pi_{w_i \in W}P(w\|c_{NLP}) = \frac{1}{2}\times \frac{1}{10}\times \frac{2}{10}\times \frac{1}{10}\times \frac{1}{10}\times \approx 0.00003$

        ![NaiveBayes-4](../images/NaiveBayes-4.png)
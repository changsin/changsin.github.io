---
layout: post
title: "What is Word Embedding?"
subtitle: "How to represent words for AI"
categories: ai
tags: nlp
comments: true
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# What is word embedding?
Word embedding refers to the process of converting words to numbers
 so that they can be used for machine learning.

## Word encoding
A simple idea is to simply represent the whole vocabulary indexing each word as a position in an array.
The result is a vector representation of each word.

| word | encoding |
|------|----------|
| king | [1, 0, 0, 0] |
| man  | [0, 1, 0, 0] |
| queen | [0, 0, 1, 0] |
| woman | [0, 0, 0, 0] |

A problem with this simple approach is that there is no similarity among related words.
For instance, king and queen are similar in terms of kingship but they are simply
separate points in the Euclidean space.
We need a representation that somehow preserves similarity measures among words.

## Word embedding
Word embedding is the hidden layer's representation of a word and its context after training.

### Embedding over encoding
* Embedding is dense vector with similarity
* Similarity comes from neighboring words

| word | encoding | embedding |
|------|----------|-----------|
| king | [1, 0, 0, 0] | [1, 2] |
| man  | [0, 1, 0, 0] | [1, 3] |
| queen | [0, 0, 1, 0] | [5, 1] |
| woman | [0, 0, 0, 0] | [5, 3] |

* Word2Vec data generation (skip gram)
  * windows size = 1


## How to represent words?
* Discrete representation: The vast majority of rule-based and statistical NLP work
regards words as atomic symbols: hotel, conference, etc.
  * WordNet? - subjective, requires human labor to create and adapt
  * Simple idea: "One-hot encoded vectors" - very sparse vectors
  * Build a vector for a large vocabulary of words
  * Turn on the corresponding element for the word in the vector
  * The problem is that there is no similarity among related words:
   e.g., Seattle motel vs. Seattle hotel
  * localist representation

* Distributional similarity based representations
  * You can get a lot of value by representing a word by means of its neighbors.
  * One of the most successful ideas of modern statistical NLP.

    ```markdown
    You shall know a word by the company it keeps.
      --J. R. Firth (1957)
    ```
    
    ```markdown
    Words that occur in similar context tend to have similar meanings.
        -- Harris (1954)
    ```
    
    word embeddings = distributional semantic model, distrubuted representation
    = semantic vector space = vector space model    
    
    Similar to later Wittgenstein

* Applications
    * compute similarities between words
    * create groups of related words
    * use as features in text classification
    * document clustering
    * NLP tasks:
        * Part-of-Speech tagging
        * Sentiment Analysis
        * Syntactic parsing
        
* Steps
1. Summarize the occurrence statistics for each word in a large document set
2. Apply some transformation to the counts: e.g., dimensionality reduction (SVD) 
to obtain dense real-valued vectors
3. Compute similarity between words as vector similarity:
cosine similarity between words = angle between vectors

* Predict methods
1. In one setup, the goal is to predict a word given its context.


#### Limitations
1. Compositionality: multi-word or sentee
2. Words with multiple senses
3. Tailed to a specific similarity measure: only synonyms
4. Topical similarity: usually captured using topic models

* Word meaning is defined in terms of vectors:
  * We will build a dense vector for each word type, chosen so that
    it is good at predicting other words appearing in its context...
    those other words also being represented by vectors...it all gets a bit recursive
    
distributed representation != distributional similarity

#### Basic idea of learning neural network word embeddings
We define a model that aims to predict between a center word w<sub>t</sub>
and context words in terms of word vectors.

> p(context\|w<sub>t</sub>)

which has a loss function, e.g.,
> J = 1 - p(w<sub>-t</sub>|w<sub>t</sub>)
* -t means all other context words
* We look at many positions t in a big language corpus.
* We keep adjusting the vector representations of words to minimize this loss.

#### Directly learning low-dimensional word vectors
* Learning representations by back-propagating errors (Rumelhart et al. 1986)
* A neural probabilistic language model (Bengio et al., 2003)
* NLP (almost) from Scratch (Collobert & Weston, 2008)
* A recent, even simpler and faster model: word2vec (Mikolov et al. 2013) --> intro now

### Main idea of word2vec
predict between every word and its context

Two algorithms
1. Skip grams: Predict context words given target (position independent)
2. Continuous Bag of Words (CBOW): Predict target word from bag-of-words context

Two (moderately efficient) training methods
1. Hierarchical softmax
2. Negative sampling

* For each word t = 1 ... T, predict surrounding words in a window of
"radius" m of every word.

Objective function: Maximize the probability of context word
given the current center word:

$$
J'(\theta) = \prod_{T}^{t=1}
$$

* Minsuk Heo's [word2vec tensorflow](https://github.com/minsuk-heo/python_tutorial/blob/master/data_science/nlp/word2vec_tensorflow.ipynb)
tutorial
## Word Similarity
* Minsuk Heo [자연어처리의 유사도 측정 방법(거리측정, 코사인 유사도)](https://www.youtube.com/watch?v=if6tjHAT6iM)
* Euclidean distance - using Pythagorean theorem
* Cosine similarity - based on the angles - ignoring vector magnitude

$$
similarity = cos(\theta) = \frac{A \cdot B}{||A|| \; ||B||}
$$
  * $$||A||$$ is the distance of A
  * The angle between two terms cannot be greater than $$90^{\circ}$$
  because a word count being a negative number doesn't make any sense.
  (if you plot word frequencies between two words as x & y coordinates)

## TF Hub Word2Vec
* Minsuk Heo [TF Hub Word2Vec](https://www.youtube.com/watch?v=p1ETojsnXYk)
  * [github](https://github.com/minsuk-heo/tf2/blob/master/jupyter_notebooks/09.Word2Vec.ipynb)

1. Train a model to predict neighbor words from the current word and vice versa.
2. Use trained model's hidden layer as word embedding. 

## Word2Vec by Jordan Boyd-Graber
* Jordan Boyd-Graber [Understanding Word2Vec](https://www.youtube.com/watch?v=QyrUentbkvw)

* similarity is calculated using _cosine similarity_:
    $$
        sim(d\overrightarrow{o}g, c\overrightarrow{a}t) =
        \frac{d\overrightarrow{o}g \cdot c\overrightarrow{a}t}
        {||d\overrightarrow{o}g|| \; ||c\overrightarrow{a}t||}
    $$

* Finding the most similar words to $$d\overrightarrow{o}g$$
  * Compute the similarity from word $$\overrightarrow{v}$$ to all other words
  * This is a single matrix-vector product:
   $$ W \cdot \overrightarrow^{T} $$
  * Result is a \|V\| sized vector of similarities
  * Take the indices of the k-highest values
  * FAST! for 180k words, d=300: ~30sm
  
* Similarity to a group of words
  * Find me words most similar to cat, dog and cow".
  * Calculate the pairwise similarities and rum them:
    $$ W \cdot c\overrightarrow{a}t + W \cdot c\overrightarrow{a}t $$
  * Now find the indices of the highest values as before
  * Matrix-vector products are wasteful. Better option:
    $$ W \cdot (c\overrightarrow{a}t + d\overrightarrow{o}g + c\overrightarrow{o}w) $$
  
## Reference

* [Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/abs/1301.3781)
  (Tomas Mikolov, Kai Chen, Greg Corrado, Jeffrey Dean)
  
* Stanford [NLP with Deep Learning](https://www.youtube.com/watch?v=ERibwqs9p38)

* Udacity TensorFlow [word2vec](https://github.com/tensorflow/examples/blob/master/courses/udacity_deep_learning/5_word2vec.ipynb)

* [tmikolov](https://github.com/tmikolov/word2vec)
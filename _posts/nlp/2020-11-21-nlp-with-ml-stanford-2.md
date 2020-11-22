---
layout: post
title: "Stanford: NLP with Machine Learning (2)"
subtitle: "Lecture 2: Stanford CS224N by Chris Manning"
categories: ai
tags: nlp
comments: true
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Lecture 2: Word Vectors 2 and Word Senses
* [2019 Winter](https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1194/)
 |  [video](https://stanford-pilot.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=68213ef7-af13-4e96-b154-ab25012bda54)
 | [slides](http://web.stanford.edu/class/cs224n/slides/cs224n-2020-lecture02-wordvecs2.pdf)
 | [notes](http://web.stanford.edu/class/cs224n/readings/cs224n-2019-notes02-wordvecs2.pdf)

#### Lecture Plan
Lecture 2: Introduction and Word Vectors

### Main idea of word2vec
* Iterate through each word of the whole corpus
* Predict surrounding words using word vectors
* The probability distribution is found by
 the dot product of the word vectors by the softmax function

$$
\theta = \left[ \begin{array}
..... \\
..... \\
..... \\
..... \\
..... \\
..... \\
\end{array}
\right]_{U (outside)}

\left[ \begin{array}
..... \\
..... \\
..... \\
..... \\
..... \\
..... \\
\end{array}
\right]_{V (center)}

\left[ \begin{array}
. \\
. \\
. \\
. \\
. \\
. \\
\end{array}
\right]_{U.{v_{4}}^T}

\left[ \begin{array}
. \\
. \\
. \\
. \\
. \\
. \\
\end{array}
\right]_{softmax(U.{v_{4}}^T) probabilities}
$$

* Same predictions at each position.
* We want a model that gives a reasonably high probability estimate to
all words that occur in the context.


* Word2vec maximizes objective function by putting similar words
nearby in space.

### 2. Optimization: Gradient Descent
* We have a cost function $$J(\theta)$$ to minimize
* Gradient Descent is an algorithm to minimize $$J(\theta)$$
* Idea: for current value of $$\theta$$, calculate gradient of $$J(\theta)$$,
then take a small step in the direction of negative gradient & repeat.

#### Gradient Descent - updated equation
* (in matrix rotation)

$$
\theta^{new} = \theta^{old} -
\alpha{\nabla}_\theta J(\theta)
$$
  * $$\alpha$$ = step size or learning rate

* (for a single parameter)

$$
\theta_j^{new} = \theta_j^{old} -
\alpha\frac{\alpha}{\alpha\theta_j^{old}} J(\theta)
$$

* Algorithm
```python
while True:
  theta_grad = evaluate_gradient(J, corpus, theta)
  theta = theta - alpha * theta_grad
```
* Problem: $$J(\theta)$$ is a function of all windows in the corpus (potentially billions!)
So $$\nabla_{\theta} J(\theta)$$ is very expensive to compute.

* Solution: Stochastic gradient descent (SGD)
  * Repeatedly sample windows and update after each one

* Algorithm:
```python
while True:
  window = sample_window(corpus)
  theta_grad = evaludate_gradient(J, window, theta)
  theta = theta - alpha * theta_grad
``` 

* Iteratively take gradients at each such window for SGD
* But in each window, we only have at most 2m + 1 words so
$$\nabla_{\theta} J_t(\theta)$$ is very sparse!
* We might only update the word vector that actually appear!

* Solution: either you need sparse matrix update operations to
only update certain rows of full embedding matrices U and V,
or you need to keep around a hash for word vectors
* If you have millions of word vectors and do distributed computing,
it is important to not have to send gigantic updates around!

* Why two vectors? --> Easier optimization. Average both at the end
  * But can do algorithm with just one vector per word

* Two models
1. Skip-grams: Predict context (outside) words (position independent) given a center word
2. Continuous Bag of Words (CBOW): Predict center word from (bag of) context words

* For additional efficiency: negative sampling
Train binary logistic regressions for a true pair (center word and word in its context window)
versus several noise pairs (the center word paired with a random word)



# Reference
* Stanford [NLP with Deep Learning](http://web.stanford.edu/class/cs224n/index.html#schedule) by Chris Manning
  * [videos](https://online.stanford.edu/artificial-intelligence/free-content?category=All&course=6097)
  * [New online certificate course in 2021](https://online.stanford.edu/courses/xcs224n-natural-language-processing-deep-learning)
  * Chris Manning's github [Text Analysis for Humanities Research](https://github.com/manning/Text-Analysis-for-Humanities-Research/tree/master/01-Intro%20to%20NLTK)
* [Distributed Representations of Words and Phrases
and their Compositionality](https://papers.nips.cc/paper/2013/file/9aa42b31882ec039965f3c4923ce901b-Paper.pdf) (Mikolov, et al. 2013) NeuIPS
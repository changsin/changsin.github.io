---
layout: post
title: "How to calculate the number of parameters in a neural network"
subtitle: "parameter counting in "
categories: ai
tags: deep learning
comments: true
---
* num_params
  = connections between layers + biases in every layer
  = (i×h + h×o) + (h+o)
  = (3×5 + 5×2) + (5+2)
  = 32

i = 3
h = 5
o = 2

[Counting no. of parameters in deep learning models](https://towardsdatascience.com/counting-no-of-parameters-in-deep-learning-models-by-hand-8f1716241889)
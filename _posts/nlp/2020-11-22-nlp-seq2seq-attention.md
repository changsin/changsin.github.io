---
layout: post
title: "Seq2Seq + Attention (Minsuk Heo)"
subtitle: "Deep Learning Machine Translation"
categories: ai
tags: nlp
comments: true
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

* [딥러닝 기계번역] 시퀀스 투 시퀀스 + 어텐션 모델 [youtube](https://www.youtube.com/watch?v=WsQLdu2JMgI)

## Problem
 How to translate a sequence of words to a target language
 
 For instance, 'I love you' => '난 널 사랑해'
 
 Note that the order of tokens is different.
 The problem is now how can you build a model
  that will translate in the correct order of the target language
  all without explicit rules. 

## Sequence to sequence

To apply it in translation tasks, you can use RNN to build the context vector
that will output target language sequence.
The Encoder-Decoder architecture can be used where the encoder packs
 the source sentence information into the context vector
 from which the decoder extracts the target sentence. 

=> Problem with a fixed size context vector

For a long sequence, the context vector window size is not enough

## Attention mechanism 
We can use encoder's each state with current state to generate dynamic context vector.

1. Encode info into a sequence of vectors not in a single context vector
2. Chooses a subset of the vectors adaptively while decoding the translation

## Teacher forcing
When the prediction is wrong, 
force the target word (ground truth) as the next input to the decoder
- results in a faster and more stable model

Reference
* [Neural Machine Translation](https://arxiv.org/pdf/1409.0473.pdf)
 by Jointly Learning to Align and Translate 
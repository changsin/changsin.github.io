---
layout: post
title: "ML Conference EU 2020"
subtitle: "The practical machine learning conference"
categories: ai
tags: event
comments: true
---
# Overview
* Homepage: [The Practical Machine Learning Conference](https://mlconf.eu/)
  * [schedule](https://mlconf.eu/#schedule)
  * [youtube: Day 1](https://www.youtube.com/watch?v=x16gSOx7KEU)
  * [youtube: Day 2](https://www.youtube.com/watch?v=wM3cYjQ8Pcg)


# Day 1 (Nov. 5, 2020)
## An Introduction to Transfer Learning in NLP and HuggingFace
### [Thomas Wolf](https://mlconf.eu/#person-thomas-wolf)
In this talk I'll start by introducing the recent breakthroughs in NLP that resulted from the combination of Transfer Learning schemes and Transformer architectures.
 The second part of the talk will be dedicated to an introduction of the open-source tools released by HuggingFace, in particular our Transformers, Tokenizers and Datasets libraries and our models.

## Computer Vision Using OpenCV
### [Beril Sirmacek](https://mlconf.eu/#person-beril-sirmacek)
As an AI scientist and a developer, I have been engaged with AI-applications for many years especially focusing on object detection and recognition purposes.
 I love thinking that we can get creative in designing neural networks.
 We can train them supervised, unsupervised, semi or self-supervised, and this gives possibilities to mimic the human brain in a narrow domain.
  However, in vision applications, there are still things where AI is lacking and will be lacking without computer vision knowledge.
   Computer vision has been solving detection and recognition problems for many years. However, in the last decade, it seems like AI is seen as a replacement of computer vision.
    AI can find the optimal model for a specific type of data set and it might achieve generalization better.
     AI can be designed in a way that it can learn life-long which also brings possibilities of creating models which serve better when they are used longer.
      However, an AI vision system will be lacking capabilities without computer vision knowledge.
       First of all, it will require a very big data set to train the model what can be expensive or even not possible.
       On the other hand, computer vision systems can be modeled only by using a hand-drawn template image. Training AI models also requires GPUs.
        Nevertheless, I do not want to encourage everyone to train AI models for solving any simple problem which could be solved easily by computer vision.
         Last but not least, knowing computer vision, machine learning and especially feature engineering methods helps to design hybrid models that might be more robust to adversarial attacks or changing conditions.

In this lecture, I will briefly introduce how computer vision (especially using the OpenCV library) and machine learning can be used for creating detection and recognition models.
 Some experience with python, jupyter notebook and some machine learning background would be useful to get more benefits from this lecture.

## The Evolution Revolution
### [Robert Plummer](https://mlconf.eu/#person-robert-plummer)
Elegant and graceful mathematics make a cool textbook cover,
 but the inside of those same books are usually dry cold engineering.
  It's important to mix the theory of innovation with the excitement of practicality,
   and through the composition of these elements we find innovation.
    In this talk, I'll show you from an engineering perspective how to explore
     balance, and ultimately bottle machined success.

## How to Machine Learn-ify any Product
### [Shivani Poddar](https://mlconf.eu/#person-shivani-poddar) Facebook
This talk will be a walkthrough of utilizing machine learning to replace a rule based system for consumers.
 We will discuss when is it okay to use ML, how to build these models with intelligent data,
  evaluate these offline and finally how to validate this evaluation to land these models in production systems.
   Furthermore, we will illustrate various self-learning/interactive-learning strategies
    that can be used for production systems to automate how models teach themselves to become better.


## Teaching ML and AI to Coders
### [Laurence Moroney](https://mlconf.eu/#person-laurence-moroney) Google
Often it's thought that to be able to succeed with Machine Learning and Deep Learning,
 as an onramp to Artificial Intelligence, that you need a deep background in mathematics and calculus,
  as well as some form of PhD. But you don't.
   With modern APIs like TensorFlow, much of the complexity is abstracted away in pre-built libraries,
    so you can focus on learning.
     In this session, Laurence Moroney, from Google, will explain
      how he has used this to create courses with hundreds of thousands of students, and from there,
       how a certificate program was created.

#### Notes
1. 30 million developers
2. 300,000 AI practitioners

The goal is to increase it by a factor 10.
Train millions of developers to reach billions of people.
The mission: Make AI Easy

* Book on Amazon: [AI and Machine Learning for Coders](https://amzn.to/2FRnm9Y)

## TensorFlow.js 101: ML in the Browser and Beyond
### [Jason Mayes](https://mlconf.eu/#person-jason-mayes)
Discover how to embrace machine learning in JavaScript using TensorFlow.js in the browser and beyond in this speedy talk.
 Get inspired through a whole bunch of creative prototypes that push the boundaries of what is possible in the modern web browser
  (things have come a long way) and then take your own first steps with machine learning in minutes.
   By the end of the talk everyone will understand how to recognize an object of their choice
    which could then be used in any creative way you can imagine.
     Familiarity with JavaScript is assumed, but no background in machine learning is required.
      Come take your first steps with TensorFlow.js!
      
# Day 2 (Nov. 6th, 2020)
## Boost Productivity with Keras Ecosystem
### [Haifeng Jin](https://mlconf.eu/#person-haifeng-jin) Keras Team at Google
TensorFlow has built a solid foundation for various machine learning applications,
 on top of which the Keras ecosystem can really boost the productivity of the developers in building machine learning solutions.
  Keras has a simple and arbitrarily flexible API for building and training models.
   However, we still need a lot of manual work to tune the hyperparameters.
    Fortunately, with Keras Tuner, we can automate the hyperparameter tuning process with minor modifications to the code for building and training the models.
     To further boost the productivity, we introduce AutoKeras, which fully automates the model building, training, and hyperparameter tuning process.
      It dramatically reduces the amount of prior knowledge needed of using machine learning for some common tasks. All you need is to define the task and to provide the training data.

## Never Have an Unmaintainable Jupyter Notebook Again!
### [Marco Gorelli](https://mlconf.eu/#person-marco-gorelli)
Data visualisation is a fundamental part of Data Science.
 The talk will start with a practical demonstration (using pandas, scikit-learn, and matplotlib)
  of how relying on summary statistics and predictions alone can leave you blind to the true nature of your datasets.
   I will make the point that visualisations are crucial in every step of the Data Science process
    and therefore that Jupyter Notebooks definitely do belong in Data Science.
     We will then look at how maintainability is a real challenge for Jupyter Notebooks,
      especially when trying to keep them under version control with git.
       Although there exists a plethora of code quality tools for Python scripts (flake8, black, mypy, etc.),
        most of them don't work on Jupyter Notebooks. To this end I will present nbQA,
         which allows any standard Python code quality tool to be run on a Jupyter Notebook.
          Finally, I will demonstrate how to use it within a workflow which lets practitioners keep the interactivity of their Jupyter Notebooks without having to sacrifice their maintainability.

* [github](https://github.com/MarcoGorelli/mlconfeu-2020-talk)
* nbdime
* nbQA - 
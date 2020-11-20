---
layout: post
title: "Markdown Tips and Tricks"
subtitle: "Useful markdown syntax and tips"
categories: coding
tags: web
comments: true
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## How to create the table of contents
This cannot be done automatically unfortunately, but you can do manually by adding hyperlinks for each section
and use the section ids to create a table of contents.

```markdown
# Table of Contents
1. [Introduction](#introduction)

```

Then in the corresponding section, add an embedded hyperlink:
```markdown
# Introduction <a name="introduction"></a>

```

## subscript and superscript
Add the tags sub or sup tags
x<sub>t</sub><sup>2</sup>


```markdown
x<sub>t</sub><sup>2</sup>
```

## bold,  italics, and bold italics
Either use surrounding underscores or asterisks

_italics_
__bold__
___bold italics___

*italics*
**bold**
***bold italics***

````markdown
_italics_
__bold__
___bold italics___

*italics*
**bold**
***bold italics***
````

## Math formulae
There are different ways of displaying math formulae.
* NB: Use an online math editor like [Upmath](https://upmath.me/) to check
markdown and latex syntax.


### 1. Use mathjax header (preferred)
Add a script header at the top of the markdown file
```markdown
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```

Then write your formula like these:

```markdown
$$
M = \left( \begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ldots \\
\end{array} \right)
$$


$$x_{1,2} = \frac{-b \pm \sqrt{b^2-4ac}}{2b}.$$

```

They are rendered separately as:

$$
M = \left( \begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ldots \\
\end{array} \right)
$$

$$x_{1,2} = \frac{-b \pm \sqrt{b^2-4ac}}{2b}.$$

### 2. Latex image tags

Inserting an img html tag with the formula
```markdown
<img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1">

```
will be rendered as:

<img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1">

A similar method is:

```markdown
![\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}](https://latex.codecogs.com/svg.latex?x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D)
```

![\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}](https://latex.codecogs.com/svg.latex?x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D)

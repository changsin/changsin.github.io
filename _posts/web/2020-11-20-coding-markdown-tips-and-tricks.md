---
layout: post
title: "Markdown Tips and Tricks"
subtitle: "Useful markdown syntax and tips"
categories: coding
tags: web
comments: true
---

## How to create a table of contents
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

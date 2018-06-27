---
layout: post
title:  "Demo of CLT(Central Limit Theorem) in Python"
subtitle: "Or how to port Jupyter Notebooks to Jekyll"
date:   2018-06-07 10:00:00 +0200
category: [ python ]
tags: [ jupyter, notebook ]
---

Most of the modern data analysis work in done with Python and Jupyter notebooks.

Notebook documents (or “notebooks”, all lower case) are documents produced by the Jupyter
 Notebook App, which contain both computer code (e.g. python) and rich text elements
  (paragraph, equations, figures, links, etc.). Notebook documents are both human-readable
   documents containing the analysis description and the results (figures, tables, etc.)
    as well as executable documents which can be run to perform data analysis. 

So why not combine such great tools together. As an example, I'll adopt one of my iPython
 notebooks, made by me during Statistics course in 2016.

---
**Problem instructions**

In this task we have to check the work of the central limit theorem, and also work with
 the generation of random numbers and the construction of graphs in Python.
 
We will choose a certain continuous distribution (the less it looks like a normal one,
 the more interesting). Generate a sample of 1000 from it, construct a sample histogram and
  draw on it the theoretical distribution density of a random variable.

For several values ​​of n (for example, 5, 10, 50), we generate 1000 samples of volume n
 and construct the histograms of the distributions of their sample means. Using information
  on the mean and variance of the original distribution (it can be easily found in Wikipedia),
   calculate the values ​​of the parameters of the normal distributions, which, according to the
    central limit theorem, approximate the distribution of sample means. Pay attention: to calculate
     the values ​​of these parameters you need to use the theoretical mean and variance of your random
      variable, rather than their sample estimates. Over each histogram, draw the density of the
       corresponding normal distribution.

Describe the difference between the distributions obtained for different values of n. Our main task
 will be to determine how the accuracy of the approximation of the distribution of sample means is
  normal with increasing n.

**Solution:**

$$a^2 + b^2 = c^2$$

```python
%matplotlib inline

import numpy as np
from scipy.stats import chi2, norm
import matplotlib.pyplot as plt
import itertools
```

Для данного задания было выбрано распределение $$\chi ^{2}$$(хи-квадрат) с $$k$$ степенями свободы.<br>
Функция плотности вероятности имеет вид: $$\frac{(1/2)^{k/2}}{\Gamma (k/2)}x^{k/2-1}e^{-x/2}$$


### References:
1. [Project Jupyter website](https://jupyter.org/)
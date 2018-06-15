---
layout: post
title:  "Central limit theorem demo"
subtitle: "or how to port Jupyter Notebooks"
date:   2018-06-07 10:00:00 +0200
category: [ python ]
tags: [ jupyter, notebook ]
---

Most of the modern data analysis work in done with Python and Jupyter notebooks.

Notebook documents (or “notebooks”, all lower case) are documents produced by the Jupyter
 Notebook App, which contain both computer code (e.g. python) and rich text elements
  (paragraph, equations, figures, links, etc…). Notebook documents are both human-readable
   documents containing the analysis description and the results (figures, tables, etc..)
    as well as executable documents which can be run to perform data analysis. 


$$a^2 + b^2 = c^2$$

## Central limit theorem
### by Egor Makhov. Coursera 2016 

---
*Instructions*

В этом задании вам предстоит проверить работу центральной предельной теоремы, а также поработать с генерацией случайных чисел и построением графиков в Питоне.

Выберите ваше любимое непрерывное распределение (чем меньше оно будет похоже на нормальное, тем интереснее; попробуйте выбрать какое-нибудь распределение из тех, что мы не обсуждали в курсе). Сгенерируйте из него выборку объёма 1000, постройте гистограмму выборки и нарисуйте поверх неё теоретическую плотность распределения вашей случайной величины.

Для нескольких значений n (например, 5, 10, 50) сгенерируйте 1000 выборок объёма n и постройте гистограммы распределений их выборочных средних. Используя информацию о среднем и дисперсии исходного распределения (её можно без труда найти в википедии), посчитайте значения параметров нормальных распределений, которыми, согласно центральной предельной теореме, приближается распределение выборочных средних. Обратите внимание: для подсчёта значений этих параметров нужно использовать именно теоретические среднее и дисперсию вашей случайной величины, а не их выборочные оценки. Поверх каждой гистограммы нарисуйте плотность соответствующего нормального распределения.

Опишите разницу между полученными распределениями при различных значениях n. Как меняется точность аппроксимации распределения выборочных средних нормальным с ростом n?

---

**Решение:**


```python
# подключим все необходимые модули и пропишим мэджики
%matplotlib inline

import numpy as np
from scipy.stats import chi2, norm
import matplotlib.pyplot as plt
import itertools
```

Для данного задания было выбрано распределение $\chi ^{2}$(хи-квадрат) с $k$ степенями свободы.<br>
Функция плотности вероятности имеет вид: $\frac{(1/2)^{k/2}}{\Gamma (k/2)}x^{k/2-1}e^{-x/2}$


### References:
1. [Project Jupyter website](https://jupyter.org/)
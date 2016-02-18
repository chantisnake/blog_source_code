---
title: test
date: 2016-02-16 21:24:49
category: computer
tags: English Blog
---
testing file

<a name="#bookmark1"> this is text is bookmark1(used for bookmark test) <a>

## math test

### block math test

$$\dfrac{\cos(a) - \Delta p}{\alpha}$$

{% math %}
\begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix}
{% endmath %}

* you have to enclose the math expresstion in
```js
{% math %}
{% endmath %}
```
 not `$ $`

### inline math test

this is a inline math statment: $\dfrac{\partial \ln(x) - y}{\partial \sin(x)}$

## nested list test

### star

* item 1
* item 2
  * subitem 1
  * subitem 2
* item 3

### number

1. number 1
2. number 2
    1. sub number 1
    2. sub number 2
3. number 3

### mix it up

* item 1
* item 2
  1. sub number 1
  2. sub number 2
* item 3

**not a good idea:**

1. number 1
2. number 2
  * sub item 1
  * sub item 2
3. number 3

## table test

| Header One     | Header Two     |
| :------------- | :------------- |
| Item One       | Item Two       |
| this is a test of the table | see if it is working correctly |

## bookmark test
[link to bookmark1](#bookmark1)


# Everything Works Perfectly! Hexo Rocks!

I have the following plugin:
* [hexo-math](https://github.com/akfish/hexo-math)
* [hexo-renderer-markdown-it ](https://github.com/celsomiranda/hexo-renderer-markdown-it)

I use the following theme:
* [Icarus](https://github.com/ppoffice/hexo-theme-icarus)

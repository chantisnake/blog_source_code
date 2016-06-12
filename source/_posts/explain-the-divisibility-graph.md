---
title: explain the divisibility graph
date: 2016-05-22 19:06:57
tags: 
  - mathematics 
  - graph theory
categories: English Blog
---

# explain the divisibility graph

## introduction

This is the topic of my summer research, so I want to explain the concept of divisibility graph to the reader of my blog.

Divisibility graph is introduced by mathematician David Wilson on his blog post 
[Divisibility by 7 is a Walk on a Graph, by David Wilson](http://blog.tanyakhovanova.com/2009/08/divisibility-by-7-is-a-walk-on-a-graph-by-david-wilson/).
This explanation is not clear at all, later he put up another post,
[Divisibility by 7 is a Walk on a Graph. II](http://blog.tanyakhovanova.com/2010/08/divisibility-by-7-is-a-walk-on-a-graph-ii-2/).
Well, this post did not explain how divisibility graph works, but this post does make the understanding of divisibility graph easier.

Here is the divisibility graph of 7 with base 10:

![](/images/divisibilty_graph/graph_7_base_10.png)

This can be used to calculate the result of $a \mod 7$, given $a$ is in base 10. 

In the next section **the black arrow graph and white(red) arrow graph** I will explain the graph property of this graph,
and I will explain why it can give you the result of  $a \mod 7$, in the next next section **how this graph works**



## the black arrow graph and white(red) arrow graph

### black arrow graph

We can see this graph consists of two directed graph, one denoted as black arrows, and the other denoted as white arrows.

Therefore we will call the graph with black arrows: black arrow graph.

The black arrow graph of 7 with base 10 are like this:

![](/images/divisibilty_graph/black_arrow_graph_7_base_10.png)

Which is not interesting at all, each arrow takes a number and increase it by 1 in mod 7 space.

This is used to calculate the result of a number mod 7.
I will explain there further in the next section: **How this graph works**


### white(red) arrow graph

I will some time refer to this graph as red arrow graph, because drawing a white arrow on white paper is... hard...

The red arrow graph of 7 with base 10 are like this:

![](/images/divisibilty_graph/red_arrow_graph_7_base_10.png)

This is a little more interesting than black arrow graph.
Each arrow takes a number $a$ and goes to $(a \times Base) \mod 7$ 

One easy conclusion we can reach from here is that every node has exactly one out degree, because modular is well defined.

In fact, my research are mainly focused on the graph property of red arrow graphs. I will post more blog about this soon.

## how do this graph work

Here is the description that the original blog gives:

> Write down a number n. Start at the small white node at the bottom of the graph. For each digit d in n, follow d black arrows in a succession, and as you move from one digit to the next, follow 1 white arrow.
> 
> For example, if n = 325, follow 3 black arrows, then 1 white arrow, then 2 black arrows, then 1 white arrow, and finally 5 black arrows.
> 
> If you end up back at the white node, n is divisible by 7. 

Then why do this works?

Recall that how black arrow graph and white arrow graph is defined:

  * black arrow graph: takes a number and increment this number by 1 in mod 7 space.
    Basically given $a$ and the arrow outputs $a + 1 mod 7$.

  * red arrow graph: takes a number and multiply it by 

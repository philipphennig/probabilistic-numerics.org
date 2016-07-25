---
layout:     post
title:      "Probabilistic Numerics for Computer Scientists"
date:       2016-05-18 10:00:00
published:  true
comments: true
author:     misc
categories: general
---

*This post is the first of a series originating in a PhD student meeting
 in Tübingen in April 2016.*

*It has been two years since the inaugural probabilistic numerics roundtable
 meeting. While the field has started to generate some momentum, it is growing
 more important to explain the concept of probabilistic numerics to all relevant
 parties. This post will attempt to explain the basic ideas, research goals and
 obstacles to a trained computer scientist.*

Probabilistic numerics is an emerging research area with goals, problems and
tools from both applied mathematics -- numerical analysis and probability theory
-- and theoretical computer science -- mostly algorithms and data structures.
Numerical algorithms are tools for solving equations that either are too big to
be solved manually or don't possess a closed-form solution at all. In both
cases, an iterative procedure is implemented in a computer which is then proven
to converge to the correct solution. Common problems are finding optimal values
of some function, evaluating tricky integrals or solving differential equations.

However, in many cases even these algorithms are too expensive to be evaluated
to very high precision. For instance, when solving integrals of many variables,
the approximation quality depends exponentially on the number of function
evaluations -- the so-called *curse of dimensionality*. Or, the function to be
optimized might be too costly to be evaluated accurately which is the case in
*deep learning* and *big data* (just to throw in some more buzz words). In these
situations, the (slightly modified) algorithms might still work, but guarantees
are harder to come by.

To draw an analogy to a classical computer science problem, I will use the A*
search algorithm. Imagine a huge weighted graph. The task is to compute the cost
from node X to node Y, but you are only given a small computational time budget,
a tiny fraction of the guaranteed worst case running time. Since the A*
algorithm uses an heuristic to estimate the remaining cost, the algorithm can be
terminated any time to produce an approximate output.

Now, the second key ingredient comes into play: probability theory. In
probabilistic numerics, probabilities can represent the uncertainties stemming
from approximations in the algorithm or finite run time. The calculus of
probability theory, most importantly Bayes' rule, allows to incorporate and
extend algorithms in many ways in a consistent and well-studied framework. E.g.,
the early stopping A* algorithm might not only return an *expected value* for
the cost, but also give a *standard deviation*. Or the algorithm could spend
some time comparing the estimated remaining cost with the observed values from
the graph weights, adjusting the overall estimation if, for instance, all
previous estimates have been too high. Another possible extension: the weights
of the graph might be represented by probability distributions themselves. If
the graph represents a road network, there might be traffic jams with some
probability.

Note, however, that this does not necessarily mean that there is randomness or
stochastic elements in a probabilistic numerical algorithm. While some
researchers also use sampling based methods in their algorithms, other methods
are completely deterministic working on deterministic problems to produce
deterministic results.

While many problems in probabilistic numerics are of mathematical nature, there
are also good reasons to get interested in this area when your focus is more on
computer science. One common problem is to represent the necessary probability
distributions with low memory cost. What are good programming interfaces when
dealing with probability distributions? There are also challenges when dealing
with specialized hardware, e.g., GPUs for large-scale optimization.

In conclusion, probabilistic numerics is a young and active research area using
probability theory to describe iterative approximative algorithms. There are a
plethora of open problems and potential applications and lots of interesting
challenges covering the whole spectrum of applied mathematics and (theoretical)
computer science.

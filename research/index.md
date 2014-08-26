---
title: Research Areas
layout: default
---

This page collects important ongoing areas of research. Most of these issues
have previously been discussed at a community meeting or workshop. If you feel
that a problem is missing on this list and is addressed by your published
research, please contact us.

## Fundamental Aspects

There are some principal questions that apply more or less directly to all
numerical problems. Chief among them is a philosophical question of what,
precisely, it means to assign a probability distribution over the result of a
computation.

# Special Challenges in Individual Areas

Each type of numerical problem poses special challenges that have to be
addressed by tailored solutions. Often, intended application areas are sources
of specific computational challenges.

## Quadrature

Quadrature is the problem of inferring the integral $$F=\int f(x)\,dx$$ over a
function $$f$$. Typically, $$f$$ is only accessible in form of a function
handle. Probabilistic quadrature rules usually model $$f$$ using a Gaussian
process measure.

#### Computational cost in competition with MCMC

In statistics and machine learning, quadrature methods compete with
Markov-Chain Monte-Carlo methods. Can they be similarly fast, even if the
function $$f$$ itself has negligible evaluation cost?

#### Model adaptation

If the prior probability distribution of the quadrature method is not well
calibrated, the posterior probability distribution can be a misleading measure
of uncertainty. Can this be addressed with automatic model adaptation methods,
and what is the computational cost of doing so?

## Linear Algebra

Linear algebra methods solve matrix computations. Of particular interest in
this area is the solution of linear problems of the type $$Ax=b$$, where $$A$$
is a matrix that can not be directly represented in memory, $$b$$ is a known
vector, and the solution $$x$$ needs to be found.

## Optimization

Optimization aims to find extremal values of a function $$f$$. At the moment,
research on probabilistic numerical optimization methods focusses on the
optimization of twice-continuously differentiable functions
$$f:\mathbb{R}^N\to\mathbb{R}$$, where $$N$$ is typically a large number.

## Ordinary Differential Equations

Ordinary differential equations are equations of the form
$$\partial x(t) / \partial t=f(x,t)$$. Classic ODE setups require the
specification of explicit initial or boundary value conditions, i.e. knowledge
of the form $$\partial x(t_0) / \partial t = x_0$$ or similar. One interesting
long-term question for probabilistic solvers for ODEs is whether they can deal
with problems in which boundary values are only known up to uncertainty.

---
title: Research Areas
layout: default
---

# Areas of Research

This page collects important ongoing areas of research. Most of these issues
have previously been discussed at a community meeting or workshop. Of course,
this list is necessarily simplified and incomplete. If you feel that a central
problem is missing on this list and is addressed by your published research,
please contact us. 

*More references can be found on [the literature page](../literature/index.html).*

## Fundamental Aspects

There are some principal questions that apply more or less directly to all
numerical problems. Chief among them is a philosophical question of what,
precisely, it means to assign a probability distribution over the result of a
computation. See [Mike Osborne's recent post on this issue]({% post_url 2014-08-27-Roundtable-Uncertainty %}), which summarizes the discussion at the
recent roundtable.  

Another ongoing issue is to identify and champion good areas of
application. Probabilistic numerical methods, in principle, allow the
quantification, propagation, and control of computational precision in large
computational pipelines. Development of a good code-base for this kind of
functionality will proceed as the following fundamental methodological
questions are slowly solved in the individual problem areas.

## Special Challenges in Individual Areas

Each type of numerical problem poses special challenges that have to be
addressed by tailored solutions. Often, intended application areas are sources
of specific computational challenges.

### Quadrature

Quadrature is the problem of inferring the integral $$F=\int f(x)\,\mathrm{d}x$$ over a
function $$f$$. Typically, $$f$$ is only accessible in form of a function
handle. Probabilistic quadrature rules usually model $$f$$ using a Gaussian
process measure. An important early work on Bayesian Quadrature is
{% cite o1991bayes --file Quadrature %}

Important research questions in Bayesian Quadrature currently include

* how to achieve sufficiently low computational cost to be wall-clock time
  competitive with MCMC methods.

* how to efficiently adapt model parameters to achieve well-calibrated
  uncertainty. Ideally, this should involve optimization _across_ covariance
  function families.

* how to build efficient quadrature methods for specific applications, most
  importantly marginalization in probabilistic models. See
  {% cite osborne2012active --file Quadrature %} for recent work.

### Linear Algebra

Linear algebra methods solve matrix computations. Of particular interest in
this area is the solution of linear problems of the type $$Ax=b$$, where $$A$$
is a matrix that can not be directly represented in memory, $$b$$ is a known
vector, and the solution $$x$$ needs to be found.
{% cite 2014arXiv14022058H --file LinearAlgebra %} recently showed that
the linear method of conjugate gradients can be interpreted as Gaussian
regression under specific priors and likelihoods (the same holds for the BFGS
method, which is equivalent to CG in the linear case). Important next steps
include

* good estimators for hyperparameters that give well-calibrated posteriors
  (meaningful error bars on matrix inverses).

* expanding the probabilistic interpretation to a larger class of linear algorithms.

### Optimization

Optimization aims to find extremal values of a function $$f$$. At the moment,
research on probabilistic numerical optimization methods focusses on the
optimization of twice-continuously differentiable functions
$$f:\mathbb{R}^N\to\mathbb{R}$$, where $$N$$ is typically a large number.
{% cite HennigKiefel --file Optimization %} showed that the Dennis family of
Quasi-Newton methods (which includes BFGS and DFP) can be interpreted as a specific
kind of Gaussian regression. Ongoing work includes

* finding good probabilistic optimization methods for optimization of noisy
  objectives (this requires solving a number of challenging sub-problems), as
  they arise, for example, in the training of big-data machine learning
  algorithms.

* expanding the probabilistic interpretation to a larger class of optimization algorithms.

### Ordinary Differential Equations

Ordinary differential equations are equations of the form
$$\partial x(t) / \partial t=f(x,t)$$. Classic ODE setups require the
specification of explicit initial or boundary value conditions, i.e. knowledge
of the form $$\partial x(t_0) / \partial t = x_0$$ or similar. One interesting
long-term question for probabilistic solvers for ODEs is whether they can deal
with problems in which boundary values are only known up to uncertainty. An
early work on probabilistic methods for the solution of ODEs was offered by
Skilling in 1991 {% cite skilling1991bayesian --file ODEs %}, using a Gaussian
process extrapolation formulation. Recently,
{% cite 13_bayes_uncer_quant_differ_equat --file ODEs %} provided a more
rigorous theoretical analysis, while {% cite HennigAISTATS2014 --file ODEs %}
showed the utility of such methods for the propagation and control of
uncertainty. Even more recently, {% cite 2014arXiv14062582S --file ODEs %}
showed a connection between Gaussian extrapolators and classic Runge-Kutta
methods. Many open questions remain. Among them are

* theoretical analysis, and better models, for the calibration of
  uncertainty in ODE solvers. Calibration is particularly hard in the ODE
  domain, because ODE solvers recursively construct new observations from their
  current belief. This "boot-strapping" leads to a systematic error in error
  estimation. A corresponding problem exists in classic methods (known their as
  the mis-match between local and global error estimation).

* better understanding for the algebraic structure and constraints of GP ODE
  solvers. A very deep literature exists for classic solvers such as the
  Runge-Kutta family. Currently, the probabilistic view is a lot less solid.

### Partial Differential Equations

Partial differential equations are perhaps a particularly interesting area for the
foundations of probabilistic numerics, because they are home to some of the
oldest mathematical results on connections between probability distributions
and the result of deterministic mathematical problems. In a famous paper,
{% cite kac1949distributions --file general %} showed that the solution to
certain types of PDEs is exactly equal to the expected path of certain
stochastic (Wiener) processes. This *Feynman-Kac* theorem is perhaps the first
explicit note of a precise connection between a stochastic object and a
deterministic computation. Recently, {% cite 2014arXiv14071517B --file PDEs %}
used the Feynman-Kac formulation to construct a fast solver for PDEs based on a
Markov-Chain Monte Carlo scheme.


## References

{% bibliography --cited --file Quadrature --file LinearAlgebra --file Optimization --file ODEs --file general --file PDEs %}

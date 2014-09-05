---
layout:     post
title:      "Tübingen Manifesto: Priors and Prior Work"
date:       2014-09-03
published:  true
author:     mosb
comments:   true
categories: [workshops, roundtable_manifesto]
---

*We in Probabilistic Numerics (ProbNum) face many unanswered questions in growing the field.
Our [roundtable in Tübingen]({% post_url 2014-08-22-Roundtable-2014-in-Tuebingen %}) aimed to bring together our new community to begin to address some of these questions. 
This is another of a sequence of posts that attempt to collate some of what we spoke about, and to, hopefully, provoke further discussion.*

## Generalisation is Great

There is a tension within in ProbNum: 
to what extent should we be in the business of reintepreting existing numerics as learning algorithms, and to what extent should we be developing ab initio solutions to numerical problems?
On this topic, the roundtable emerged at a reasonable, if dull, conclusion. 

Existing algorithms have become successful for good reason, and the experience of the ProbNum community is that these approaches are often tough to beat.
As such, we should always, where possible, aim to *generalise existing approaches.*

Doing so combines the best of both worlds: benefitting from the insights embedded in successful techniques, while still allowing the benefits of the ProbNum framework.
Further, adding a probabilistic intepretation to existing algorithms has proven to often require little overhead. 
Even providing theory to match the convergence analysis supplied for existing ODE solvers is not too great a hurdle: we can develop probabilistic convergence proofs in the place of traditional theory.
Finally, communicating the benefits of new ProbNum approaches is substantially aided by describing them in the language of older techniques.

## How Much Structure Should We Cram Into ProbNum?

Another key question for ProbNum is: when are richer, more structured, models, worth their associated computational cost? As Bayesians, we're often keen to incorporate as much prior information (structure) as possible. 
However, for numerics, this must be balanced against the computational overheads induced. 
In fact, one lesson hard-learned from early ProbNum research is that it is all-too-easy to use excessive structure.

## Traditional Approaches Use Either All the Structure or None

Here it is worth revisiting traditional approaches to understand their own choices for structure. 
For example, it's remarkable how much structure traditional optimisation algorithms ignore -- see
{% cite hennig13_quasi_newton_method --file Optimization %} -- while remaining exceptionally difficult to outperform with better-informed approaches.

The amount of structure used is also polarised, varying wildly from community to community. 
Broadly speaking, Runge-Kutta methods aren't much used in real world applications: most problems are solved with highly structured, bespoke, solvers. 
In contrast, in control engineering, structure is often ignored: most control engineers, in practice, will simply call the Matlab function `ode45.m`.

Similarly, in quadrature, users will either: 

* call `integrate.m`, a completely black-box solution uninformed by problem structure, or: 
* use heavily structure, bespoke, [Genz-style](http://www.math.wsu.edu/faculty/genz/homepage) algorithms for particular problems. 

The problem of bespoke solutions, of course, is that their applicability is limited.
Most at the roundtable did not feel they had the stamina to spend their careers solving a single, narrowly-defined, problem, as the developers of such solutions have done.

## ProbNum should embrace its flexibility

A key advantage of ProbNum algorithms is their *configurability.*As ProbNum algorithms are explicitly model-based, the model can be selected to match the structure of the problem at hand; 
Where Gaussian processes are used, we are free[^1] to choose their covariance and mean functions to suit;
hence an algorithm like Bayesian Quadrature can be adapted to a wide variety of problems.
The roundtable reached the conclusion that ProbNum should fully exploit this flexibility, one of its unique selling points.

Exposing design choices allows users to more easily adapt ProbNum to solve previously untackled problems.
For example, incorporating knowledge of specific low-dimensional structure seems like the only way to solve high-dimensional problems.
Further, this flexibility accommodates our long-term goal of assembling modular algorithms into an integrated ProbNum system.
That is, structure can be either incorporated or ignored into an individual algorithm, using a [meta-reasoning]( {% post_url 2014-09-01-Roundtable-ProbNum-ProbProg %} ) approach to meet the computational desiderata imposed by other algorithms in the ProbNum hierarchy.

[^1]: At least, we have some flexibility in incorporating such structure, although often the problem imposes constraints. For example, in Bayesian quadrature, we are limited by the requirement that the covariance function be integrable in closed-form.

## References

{% bibliography --cited --file Optimization %}

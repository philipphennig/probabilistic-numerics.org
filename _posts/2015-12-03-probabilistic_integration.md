---
layout:     post
title:      "Probabilistic Integration"
date:       2015-12-03 09:00:00
published:  true
comments: true
author:     FX
categories: []
---

Recent months have been very exciting for the probabilistic numerics community, with a series of new interesting papers appearing and a scoping workshop at the Alan Turing Institute discussing avenues for future research. In particular, there has been a lot of interest in solving differential equations, which was the topic of two workshops at the University of Warwick and at SciCADE, but the focus is now slightly shifting towards quadrature with two workshops on Probabilistic Integration (not to be missed!) at [NIPS 2015 in December]({{ site.baseurl }}/meetings/NIPS2015.html) and [MCMSki V in January]({{ site.baseurl }}/meetings/MCMSki2016.html).

Probabilistic Integration, and, in particular, Bayesian Quadrature (BQ), was one of the first areas to be investigated in probabilistic numerics. The overall idea is to fully handle our epistemic uncertainty over the numerical solution of the integral; this can, of course, be obtained by adopting a Bayesian approach. More precisely, we can model the integrand using a Gaussian Process and, using the linearity of Gaussian variables, obtain a Gaussian posterior distribution over the solution of the integral. We then usually consider the posterior mean of this Gaussian distribution to be our approximation of the integral, while the posterior variance can help us understand how uncertain we are about our solution.
This method has been extended numerous times in order to improve its applicability to statistical tasks, such as computing ratios of integrals, or considering cases where the integrand is a probability distribution and hence intrinsically non-negative.

Recent work has focussed on studying the links between BQ and other methods. For example, {% cite 2015arXiv150405994S --file Quadrature %}, discussed how many popular quadrature methods can be obtained as the posterior mean of a BQ method with a specific kernel. Similarly, {% cite bach2015equivalence --file Quadrature %} showed that performing BQ is equivalent to using a specific type of random features.

On the other hand, existing methods can, and sometimes should, also help to design more efficient BQ methods. In a recent paper by {% cite briol_frank-wolfe_2015 --file Quadrature %}, the authors showed how a convex optimisation method, called the Frank-Wolfe algorithm, could provide a probabilistic solution to integration problems. This method also provided the first ever provable posterior convergence and contraction rates for BQ. Follow-up work {% cite briol_probabilistic_2015 --file Quadrature %} also demonstrated that similar theory could be obtained when using Monte Carlo methods (such as Markov Chain or Quasi Monte Carlo) to pick the points at which the integrand is evaluated. This paper also provides rates for the newly proposed methods, as well as a framework for obtaining rates of any new future BQ methods.

Clearly, much remains to be done to be able to provide similar theoretical guarantees to alternative methods, but these early successes are very promising and the increasing popularity of workshops in probabilistic numerics clearly demonstrates the interest from potential users!

## References

{% bibliography --cited --file Quadrature %}

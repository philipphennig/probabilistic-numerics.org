---
layout:     post
title:      "Connections, Part II: Stochastic numerical methods"
date:       2015-01-15 06:00:00
published:  true
comments:   true
author:     phennig
categories: general
---

*As I go around presenting the idea of probabilistic numerics to various
 audiences, certain questions about related areas come up repeatedly. This post
 explains how probabilistic numerics compares to existing ideas of using
 stochasticity in numerical problems.
 [A previous post]({% post_url 2015-01-14-UQ %}) discussed connections to
 uncertainty quantification. A subsequent one will look at
 [Bayesian Optimization]({% post_url 2015-01-16-BO %}).*

*A disclaimer: Obviously, everyone has different opinions about the scope and
 purpose of certain concepts and academic fields. And I am not an expert in the
 areas discussed here. This post relates a part of my own personal
 justification, why I think certain ideas are novel and interesting. It is not
 intended as a holistic overview of a field. If anyone disagrees with
 characterizations I make here, I would be glad if you could relate your
 opinion in the comments section below.*

Using **stochasticity** to solve deterministic problems is anything but a new idea
in numerical mathematics. Random numbers have been employed in at least two quite different
ways for numerical purposes, one lowering cost and precision, the other
increasing cost and robustness.

### Randomized methods 

*Projecting* a large problem onto a randomly chosen smaller space can reduce
computational cost while introducing a new kind of imprecision. Such methods
are called *randomized* or, unfortunately, also *probabilistic* algorithms
{% cite liberty2007randomized --file related %}
{% cite halko2011finding --file related %}.
The key idea is that given a particular numerical problem spanning variables
from a certain high-dimensional space, one chooses a random projection into a
space of much lower dimensionality, and solves the problem in that space. The
surprising aspect, the strength of this approach, is that it tends to cause a
lot less deficiencies than one would intuitively assume; and this has been
studied quite rigorously.

### Perturbations ###

Repeatedly solving randomly *perturbed* variants of a problem can help quantify
the robustness of a task. This is in some sense the counterpart to the above
projection approach: Instead of removing degrees of freedom to get drastically
lower cost at surprisingly low loss of precision, perturbation methods enrich
the description of a problem to probe new interesting aspects -- at drastically
higher cost. (For clarity: I'm not talking about
["perturbation methods"](http://en.wikipedia.org/wiki/Perturbation_theory)
which are a theoretical tool, not a computational one, and random numbers only
play a conceptual role there).

### Monte Carlo methods ###

A third, much-studied area that is of particular relevance for probabilistic
numerics are [Monte Carlo](http://en.wikipedia.org/wiki/Monte_Carlo_method)
methods. In statistics and machine learning, MC methods are used primarily to
compute expectations and marginals -- i.e., for quadrature. In contrast to the
two other uses of random numbers above, MC methods really solve an unmodified
given numerical integration task. Although they can be quite elaborate
algorithms, the basic idea is quickly explained: To compute the intractable
expectation $$\langle f\rangle_p= \int f(x) p(x) dx$$, draw $$N$$ samples
$$x_i\sim p$$, and approximate $$\langle f\rangle_p\approx \frac{1}{N}\sum_i
f(x_i)$$. This is an unbiased statistical estimator which converges at the
*statistically* optimal rate of $$\mathcal{O}(N^{-1/2})$$. If you can't draw
exact samples from $$p$$, you have to compute them approximately, and this is
where a lot of the research (particularly in Markov Chain MC methods) has
focussed over the past decades.

### Uncertainty does not need random numbers ###

The area currently of biggest interest for probabilistic numerics are
complementary to the two former settings described above. With a probabilistic
numerical method, we do not necessarily want to reduce a given problem to a
less costly variant, but are interested in as good a solution to the actual
problem at hand (however, it is interesting that recent results suggest that
choosing projections in a non-random, "most informative" way can be done at
reasonable cost and may improve performance
{% cite GarnettOH2013 --file related %}). And
while we may well wonder about the sensitivity of the found solution to
perturbations of the task, our chief interest is in the error created by the
approximate computation itself, and the sensitivity of our computation's result
to further steps.

The story is much more intricate---and exciting---with regards to MC
methods. Recently, I have found myself repeatedly in discussions with
colleagues about the helpfulness of random numbers for computations, in
connection with our recent NIPS paper on fast Bayesian quadrature
{% cite gunter14-fast-bayesian-quadrature --file quadrature %}. There is a famous
polemic by Tony O'Hagan {% cite o1987monte --file Sampling%} pointing out that
randomness leads to serious inefficiencies when performing a deterministic
computation. It is well-known that, on low-dimensional problems, classic
quadrature rules can converge *much* faster than MC estimators: Depending on
the rule used, and the smoothness of the integrand, $$\mathcal{O}(N^{-p})$$ for
$$p\in\mathbb{N}$$ is not unusual. Classic quadrature rules are identified with maximum a
posteriori estimators under various Gaussian process priors over the integrand
{% cite minka2000deriving --file quadrature %}. Extending on this insight, our
recent NIPS paper presents a general purpose quadrature method for strictly
positive integrands (such as the probability distribution $$p$$) which
empirically outperforms (in wall-clock time) established MCMC methods. Given
the ubiquity of MC methods, this kind of result is very exciting, and once again
suggests an area of research that is only just beginning to take shape.

### References ###

{% bibliography --cited --file related --file quadrature --file Sampling %}

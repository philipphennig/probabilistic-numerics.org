---
layout:     post
title:      "Tübingen Manifesto: Probabilistic Numerics and Probailistic Programming"
date:       2014-08-27 20:00
published:  false
author:     Michael A Osborne
categories: workshops
---
We in Probabilistic Numerics face many unanswered questions in growing the field.
Our roundtable in Tübingen aimed to bring together our new community to begin to address some of these questions. 
This is another of a sequence of posts that attempt to collate some of what we spoke about, and to, hopefully, provoke further discussion.

# Discussion incl Noah Baumbach 
probprog is about the design of generative models, is about producing a posterior for the model. This is orthogonal to the uncertainty introduced through the use of numerical procedures. Use BQ downstream of a probabilistic programming. 

lazy evaluation as an analogue of a modular probablistics numeric system
lazy evaluation of significance

overload to return estimate + uncertainty

as in auto-diff, auto-integrate could exploit the structure of the integrand in order to construct an appropriate covariance function for BQ, code-parsing

in probabilistic programming, uncertainty is represented largely by bags of samples

"smooth interpretation" paper

numerical analysts care about: consistency, rates of convergence as function of smoothness of covariance operators

## meta-reasoning

deciding when to stop achieving accuracy you don't need.

meta-reasoning: selection of which part of the numerical pipeline to refine
"you should only do as much meta as regular reasoning"
-Stuart Russell

probnum for Bayesian meta-reasoning over which existing algorithm to use
is greedy selection of algorithm to improve enough?

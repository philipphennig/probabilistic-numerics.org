---
layout: default
title:  "Tübingen Manifesto"
date:   2014-08-27 20:00
categories: workshops
---

We in Probabilistic Numerics are a new community, and we face questions about many aspects of 
The roundtable in Tübingen was an excellent opportunity to air and discuss some of the questions facing our growing community. 

# Uncertainty

Uncertainty? Helpful to separate calculation from philosophical problems.

We are doing exactly what we do in stats: collect data and estimate. Exactly the same notion of uncertainty. 
Except in ODEs, for computational issues: we have a sequence of caulctions, dropping uncertainty, our future evaulations are conditional on past evaluations. 

Our uncertainty needs to be computed on the basis of a reasonable set of prior assumptions, of course.

Neil Lawrence says we should use coding theory to deal with computation. This is equivalent to probabilistic reasoning. Phrase all of probnum in terms of compression. 


## Probnum as analogue to ProbProg

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

## should we interpret or invent?

* exploit past successes of good algorithms
* generalisation of existing algorithms is oobviously the best
* good for explaining new approaches
* often adding in uncertainty to traditional approaches isn't too much overhead

## how much prior info to include


order convergence of ode solvers is the standard theoretical analysis; we can provide our own theory to replace all that. We can supply probabilistic convergence.

runge-kutta methods aren't much used because many problems actually are solved with specialised approaches in practice. Solvers are pretty much a bespoke industry. 

Not so in control. A control engineer is just going to call ode45. 

quadrature: you either use integrate.m, completely black-box, or bespoke genz style algorithms. BQ could be an intermediary, allowing for tunable amounts of prior information. QB could take optimal arguments: mean and covariance function.

Exposing design choices, situating ourselves in the middle between bespoke and black-box, accommodates our long-term goal of assembling modular algorithms all hooked together. 

Incorporating prior information to deal with high dimensions, this would give us a big user market beyond the state of the art.

## Who are our users?

scientists care about: uncertainty emerges from the mathemcatical model alone
is our internal understanding of uncertainty necessary to communicate externally?

climate scientists understand that uncertainty is importnatn; the misfit between their models and data is large

active learning (digging wells) requires uncertainties from your algorithm

active learning is very important within numerics: refining grids
bounds are a guide, too loose in practice; properly calibrated measure is important

coherence is critical for numerical algorithms, and for scientists exploring a research hypothesis

the added output of uncertainty adds value for users to interrogate performance: enhanced profiler that provides details on the importance of every algorithm in your pipeline.  

Jes: rather than expecting users to come to us, we need to find an application, and embed ourselves in that application.

## Community

in probprg, it's taken almost a decade to achieve internal coherence, and still hasn't identified a single user group.

lessons from probprog: public presence and open tent; *don't want to over-sell, over*

computation is not such a problem any more, prob theory is more developed: the time is right for prob num

gecko: evolutionary community that has gone under the radar.

NIPS is too novelty driven
SIAM as a possible community to reach out to. 

0. website: github.io
1. code repositories
2. literature incl. old papers
2. test problems, data
3. workshops in conference: NIPS 2015, SIAM 2015 meeting workshop (Ben & Mark), special session with invited speakers
4. mailing list

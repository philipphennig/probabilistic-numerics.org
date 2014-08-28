---
layout:     post
title:      "Tübingen Manifesto: Uncertainty"
date:       2014-08-27
published:  false
author:     Michael A Osborne
categories: workshops
---
We in Probabilistic Numerics face many unanswered questions in growing the field.
Our roundtable in Tübingen aimed to bring together our new community to begin to address some of these questions. 
This is another of a sequence of posts that attempt to collate some of what we spoke about, and to, hopefully, provoke further discussion.


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

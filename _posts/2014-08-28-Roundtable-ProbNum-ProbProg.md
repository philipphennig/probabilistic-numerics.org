---
layout:     post
title:      "Tübingen Manifesto: Probabilistic Numerics and Probabilistic Programming"
date:       2014-09-01
published:  true
author:     mosb
comments:   true
categories: [workshops, roundtable_manifesto]
---
*We in Probabilistic Numerics face many unanswered questions in growing the field.
Our [roundtable in Tübingen]({% post_url 2014-08-22-Roundtable-2014-in-Tuebingen %}) aimed to bring together our new community to begin to address some of these questions. 
This is another of a sequence of posts that attempt to collate some of what we spoke about, and to, hopefully, provoke further discussion.*

We were very fortunate to benefit from the coincidental presence of [Noah Goodman](http://stanford.edu/~ngoodman/) in Tübingen, who generously spent an afternoon at the roundtable talking with us. 
Noah, of course, is a founding and deeply committed member of the [Probabilistic Programming](http://probabilistic-programming.org/wiki/Home) community.
Noah had many fascinating reflections on developments within Probabilistic Programming (ProbProg), and how they might connect with Probabilistic Numerics (ProbNum). 

ProbProg seems to be largely about allowing the design of complex generative models, and then ensuring that uncertainty is properly propagated in producing posteriors using the model.
This is certainly not the same as the propagation required to manage uncertainty introduced through the use of finite-precision or approximate numerical procedures, but there are some commonalities. 
Below are a number of items drawing out some of the links between the fields.

## Meta-Reasoning

ProbNum offers the attractive potential of performing decision-theoretic management of systems of probabilistic numerical algorithms. 
That is, ProbNum could be used to select which part of a numerical pipeline to refine, that is, to decide when to stop a numerical algorithm achieving accuracy you don't need.
Noah was interested in this process, which he likened to [*meta-reasoning,*](http://mlg.eng.cam.ac.uk/duvenaud/talks/tea_talk_metareasoning/index.html) and recommended making the connection explicit. 

Noah also posed the excellent question of how much computation it was worth spending to perform this meta-reasoning. 
Of course, this is a question we couldn't readily answer.
Would a greedy selection of the numerical algorithm to spend the next unit of computation on be sufficient, or would more sophisticated strategies be required?
At this point, Noah quoted [Stuart Russell](http://www.cs.berkeley.edu/~russell/) in recommending that, as a rule, "you should only do as much meta-reasoning as regular reasoning". This seems sensible enough to me!

## Lazy Evaluation

Noah also mentioned links between ProbNum's approach of returning numerical results of flexible degrees of accuracy to the notion of [*lazy evaluation*](http://en.wikipedia.org/wiki/Lazy_evaluation) common in functional languages like Haskell.
In either case, only as much computation is performed as is absolutely required.
For lazy evaluation, what is required can be determined exactly, whereas the ProbNum approach would treat this as a question to be answered with decision theory. 
 
## Overloading

Another fundamental concept in languages that we discussed was that of [*overloading*](http://en.wikipedia.org/wiki/Function_overloading). 
Treating, for example, a probability distribution over integers as a type that generalises the type `int`, ProbNum might well benefit from being implemented using overloading.
That is, functions could be overloaded to permit the optional input and output of variances in addition to the usual input and output estimates.

## The Benefits of Knowing a Function's Source Code

In probabilistic programming, uncertainty is represented largely by bags of samples. 
It would certainly be interesting to use Bayesian Quadrature downstream of a probabilistic program to try to make better use of those samples.
In such a setting, Bayesian quadrature might even benefit from access to the structure of the probabilistic model, available in the probabilistic program source code.
This structure might inform the mean and covariance functions chosen for the Gaussian process model used within Bayesian quadrature, for example.
A similar approach is at the heart of [autodiff](http://www.autodiff.org/), which analyses the code for a function so as to allow for the computation of its derivatives.
Why shouldn't we do the same thing in computing integrals?


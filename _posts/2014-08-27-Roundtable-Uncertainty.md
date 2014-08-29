---
layout:     post
title:      "Tübingen Manifesto: Uncertainty"
date:       2014-08-27
published:  true
comments:   true
author:     mosb
categories: [workshops, roundtable_manifesto]
---
*We in Probabilistic Numerics face many unanswered questions in growing the field.
Our [roundtable in Tübingen]({% post_url 2014-08-22-Roundtable-2014-in-Tuebingen %}) aimed to bring together our new community to begin to address some of these questions. 
This is the first of a sequence of posts that attempt to collate some of what we spoke about, and to, hopefully, provoke further discussion.*

Our first major question was: *what is a well-defined notion of "uncertainty" for a probabilistic numerical method?* 
Consider $$\psi = \int_{0}^{1} \exp\bigl((\sin 3 x)^2 + x^2\bigr)\mathrm{d}x$$. 
In a sense, we know $$\psi$$: I was able to write it down using a small number of mathematical symbols.
However, of course, to find $$\psi$$ to three significant figures, I, for one, would have to use a numerical algorithm (please let [me](mailto:mosb@robots.ox.ac.uk) know if you do actually have a closed form expression for $$\psi$$!). 
Given the finite precision of any numerical algorithm, can we really still be said to know $$\psi$$?
If not, how should we think about the uncertainty in $$\psi$$?

On this, I think the roundtable arrived at a helpful consensus.
We came to the conclusion that uncertainty for probabilistic numerical algorithms was *exactly the same quantity* that we are used to in statistics.
That is, a probabilistic numerical algorithm is doing exactly what we do in statistics: collecting data and estimating.
Specifically, a numerical integration algorithm, tasked with finding $$\psi$$, would collect evaluations of the integrand, and use them to estimate the integral.
For a probabilistic numerical integration algorithm, these evaluations will be used to inform a probabilistic model for the integrand, typically a Gaussian process, which can then be used to determine a posterior probability density for the integral.
As such, we can use exactly the notion of uncertainty we're used to from any other form of statistical or probabilistic reasoning.
As with other probabilistic calculations, we could, if we desired, reframe the whole of probabilistic numerics as compression, using the language of coding theory. 
Whichever language we use, uncertainty in probabilistic numerics is clearly building on solid, existing, foundations.

Of course, there is a caveat: the uncertainty returned by a probabilistic numerics algorithm is conditional on the prior information upon which it is constructed. 
Whether the returned uncertainty makes any sense will depend critically on the quality of the prior information included.
For example, in ODE solving, standard numerical algorithms typically ignore the uncertainty in past evaluations: final distributions will thus typically be unreasonably confident.
The output of numerical integration algorithms will likewise be 
reliant on the assumptions built into the inference for the probabilistic model for the integrand.
In constructing probabilistic numeric algorithms, we must be careful to ensure that our prior assumptions reflect, as best as possible, our true state of knowledge.

More notes from the workshop to follow!

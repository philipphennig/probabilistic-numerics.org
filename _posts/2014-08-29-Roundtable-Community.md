---
layout:     post
title:      "Tübingen Manifesto: Community"
date:       2014-09-05
published:  true
comments:   true
author:     mosb
categories: [workshops, roundtable_manifesto]
---
*We in Probabilistic Numerics face many unanswered questions in growing the field.
Our [roundtable in Tübingen]({% post_url 2014-08-22-Roundtable-2014-in-Tuebingen %}) aimed to bring together our new community to begin to address some of these questions. 
This is the final of a sequence of posts that attempt to collate some of what we spoke about, and to, hopefully, provoke further discussion.*

## Who Are Our Users?

Before we can address some of the questions considered in the [last post]( {% post_url 2014-09-03-Roundtable-Priors-and-Prior-Work %} ), there is a more fundamental question to be answered: *who are our users?* 
Which other disciplines are likely to care most about the probabilistic numerics tools that we can potentially deliver?
Rather than waiting for users to come to us, it seems clear that we need to find a strong motivating application within which to deeply embed our approaches. 
Even given we can find such an application: how are we to reach out to the relevant users?
These considerations would seem to have direct influence on the course of research undertaken within ProbNum.

One clear community we might wish to engage with is *numerical analysis,* for obvious reasons. 
It is this much older field that has developed most[^1] of the techniques against which ProbNum must compare itself.
To advertise our work to numerical analysts, we would need to engage on their terms. 
This means that we must establish the reliability of ProbNum techniques according to the traditional notions of consistency and rates of convergence.

Working against establishing such theory for ProbNum is the very complexity of our algorithms. 
Much of ProbNum is built upon Gaussian processes (GPs), for which existing theory is patchy at best: it's difficult to say much of any significance if you don't know the right covariance function.
Worse still, ProbNum often requires approximations to full (expensive) Gaussian process (GP) inference so that algorithms can serve as cheap, inner-loop, methods.
Producing firm results for these algorithms is likely to induce many headaches. However, it seems undesirable to sacrifice algorithmic complexity, and often performance, simply so as to establish theory.

Furthermore, using GPs ensures that the output of many ProbNum algorithms has unbounded support: any result is possible. 
While it is, of course, possible to produce probabilistic bounds by thresholding the probability, this would seem to miss a central advantage of ProbNum: its production of full posteriors for quantities of interest.
Some rebels at the roundtable even posited that the bounds provided for many traditional numerical algorithms are far too loose, in practice. 
The greater structure incorporable into ProbNum algorithms promises much tighter, better-calibrated, representations of uncertainty.

Uncertainty becomes a central concern if ProbNum thinks about turning to applications in the experimental sciences.
Most scientists are well aware of the importance of uncertainty management.
For example, climate scientists are well-versed in statistical reasoning, and climate science models are sensitive to numerical procedures: 
quantifying the uncertainty introduced through the use of numerical algorithms seems a relatively easy sell. 
<!-- Honest uncertainty estimates are required wherever experimental design, or active learning, is involved.
If an experiment requires digging time-consuming and expensive holes, it makes sense to spend a little more computation to incorporate uncertainty management into your numerical procedures.
Nobody wants to waste an experiment because 
 -->

As an aside, the added output of uncertainty to numerical procedures adds value for users in interrogating performance. You could imagine ProbNum providing an enhanced profiler: able to assess the importance of every algorithm in your pipeline. Any user assembling a hierarchy of numerical procedures stands to benefit from a ProbNum approach to assessing sensitivity.

## Whither the ProbNum Community?

This final question we wrestled with at the roundtable was our collective direction as a community. 
Here, again, [Noah Goodman's](http://stanford.edu/~ngoodman/) insights from the development of the [Probabilistic Programming (ProbProg)](http://probabilistic-programming.org/wiki/Home) community were enlightening.

Noah pointed out that it had taken several years for ProbProg to achieve consensus on the prioritisation of research questions, and the question of who were the right group of users had yet to be satisfactorily answered: so we in ProbNum shouldn't panic if it takes us a little longer.
Noah also highlighted the need not to *over-sell* what the field could deliver. I think all of us in ProbNum are aware that we have some way to go, and I think we agree that we must be careful to proceed with honesty about what our algorithms can achieve relative to the state-of-the-art.
Noah finally emphasised the need for a strong public presence, and the maintenance of an *open tent.*
This argument resonated with us, and has been in our minds in the establishment of this website and blog. 
On that note: thanks for making it to the end of these blogs, and, if they have inflamed any interest within you, please do get in touch!

[^1]: It's probably fair to say that numerical analysis has, however, not been at the forefront of more modern means of quadrature, such as [Monte Carlo](http://en.wikipedia.org/wiki/Monte_Carlo_integration).

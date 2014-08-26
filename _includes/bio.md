Numerical algorithms, such as methods for the numerical solution of integrals
and ordinary differential equations, as well as optimization algorithms can be
interpreted as estimation algorithms. They estimate the value of a
quantity that can not directly be derived (the value of an integral, the
solution of a differential equation, the location of an extremum), given the
values of quantities that can be directly observed (function values of the
integrand, evaluations of the differential equation, function values of the
gradient of an objective). So these methods inform inference, and are
accessible to the formal frameworks of probability theory. They are learning
machines.

Taking this observation seriously, a probabilistic numerical method is a
numerical algorithm that takes in a probability distribution over its inputs,
and returns a probability distribution over its output. Recent research shows
that it is in fact possible to directly identify existing numerical methods,
including some real classics, with specific probabilistic models.

Interpreting numerical methods as learning algorithms offers various
interesting benefits. It can offer insight into the algebraic assumptions
inherent in existing methods. As a joint framework for methods developed in
separate communities, it allows transfer of knowledge among these areas. But
the probabilistic formulation also explicitly provides a richer output than
simple convergence bounds. If the probability measure returned by a
probabilistic method is well-calibrated, it can be used to monitor, propagate
and control the quality of computations. 

This website collects information pertaining to the development, analysis and
use of numerical algorithms with probabilistic interpretations. We retain a
growing list of academic publications on the subject, collect open and central
research questions, and publish a blog discussing recent developments. 

Although the mathematical idea of uncertainty about a computation was discussed
by several authors in the past, the first formal meeting of our community was a
workshop at Neural Information Processing Systems 2012. (the original website
of this workshop can be found
[here](http://www.probabilistic-numerics.org/index_workshop.html)).

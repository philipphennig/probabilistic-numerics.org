Numerical algorithms, such as methods for the numerical solution of integrals
and ordinary differential equations, as well as optimization algorithms can be
interpreted as estimation rules. They estimate the value of a latent,
intractable quantity -- the value of an integral, the solution of a
differential equation, the location of an extremum -- given the result of
tractable computations ("observations", such as function values of the
integrand, evaluations of the differential equation, function values of the
gradient of an objective). So these methods perform inference, and are
accessible to the formal frameworks of probability theory. They are learning
machines.

Taking this observation seriously, a probabilistic numerical method is a
numerical algorithm that takes in a probability distribution over its inputs,
and returns a probability distribution over its
output. [Recent research](literature/index.html) shows that it is in fact
possible to directly identify existing numerical methods, including some real
classics, with specific probabilistic models.

Interpreting numerical methods as learning algorithms offers various
benefits. It can offer insight into the algebraic assumptions inherent in
existing methods. As a joint framework for methods developed in separate
communities, it allows transfer of knowledge among these areas. But the
probabilistic formulation also explicitly provides a richer output than simple
convergence bounds. If the probability measure returned by a probabilistic
method is well-calibrated, it can be used to monitor, propagate and control the
quality of computations.

This site collects information pertaining to the development, analysis and
use of numerical algorithms with probabilistic interpretations. We retain
[a growing list of academic publications](literature/index.html) on the
subject, [collect open and central research questions](research/index.html),
and publish a [blog](blog/index.html) discussing recent developments. 

Although the mathematical idea of uncertainty about a computation was discussed
by several authors in the past, the first formal meeting of our community was a
workshop at Neural Information Processing Systems 2012. (the original website
of this workshop can be found
[here](http://www.probabilistic-numerics.org/index_workshop.html)).


## How to contribute

Would you like to get involved with PN research community? If you feel that
your own published work fits the above description, and should be mentioned on
the [literature site](literature/index.html), then please don't hesitate to
write us an email (see contact details on our pages linked above). Most
importantly, if you would like to contribute and meet other people interested
in related questions, join us for one of our
[meetings and workshops]({{site.baseurl}}/meetings/index.html).
    

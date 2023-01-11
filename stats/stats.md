# Processes

### Bernoulli process
A Bernoulli process is a Bernoulli trial repeated n times.
A Bernoulli trial either succeeds or fails; either outcome has the same probability each time.
The Bernoulli process is memoryless.
The Bernoulli distribution, in a word, is a binomial distribution made of a single Bernoulli trial.
A binomial distribution is one made of more than multiple Bernoulli trials.

Fun facts:
The distribution corresponding to Bernoulli trials is a [geometric distribution](https://en.wikipedia.org/wiki/Geometric_distribution).
The distribution corresponding to a binomial distribution without replacement is a hypergeometrical distribution.
(The two names/numbers (nomial/nombre) are success, failure. {0, 1})

### Poisson process
A Poisson process is the converse of "snowballing".
That is, an event doesn't engender subsequent events.
This is also called [memorylessness.](https://en.wikipedia.org/wiki/Memorylessness)
The frequency of events has no proportion to the occurrence of the events.

Examples:
Collision of particles.
People entering a restaurant.
Arrivals of a bus.
Receiving a letter in the mail.

Justification:
This couple coming in at 2:01 PM has nothing to do with *that* couple coming in at 2:00 PM.
(That is, for the purposes of modeling. The particular motives of these two couples do not concern us.)
Likewise, the collision *now* of these two particles with each other *might* have been caused by some undiscerned reaction, but, we are uncertain, and only notice the number of events, i.e. *collisions*.

Application:
Nevertheless, in spite of our agnosticism about the cause of the events, we can predict the frequency of an event in an amount of time using a Poisson distribution.


## Distributions

### Normal


### Gamma distribution

Wow, lol.
[This is actually so many distributions.](https://en.wikipedia.org/wiki/Gamma_distribution)
Has a shape parameter, kappa, and a rate parameter, 1 over beta.
Beta is called the scale parameter.
The inverse scale parameter is called the rate parameter.
For these reasons, 1 over beta is equal to lambda. (Shown below [^1])

### Poisson
A Poisson distribution is the average (lambda) amount of events (described by a Poisson process) which have been recorded to happen in an amount of time.
Its lambda is a rate of discrete occurrences in an amount of time.
A Probability mass function gives us the likelihood of n number of events occurring in t time, where the average occurrence of events in t time is lambda.
scipy.stats.poisson.pmf(n, l)
A continuous distribution function gives us the probability that n or fewer events will occur in t time, where the average occurrence in t time is lambda.
scipy.stats.poisson.cdf(n, l)
To take the probability that more than n events will occur in t time given lambda, we establish that something must happen by asserting 1 before the cdf.
Then we take the difference between 1 (certainty that something, anything will happen) and the probability that the event will occur n or fewer times.
By taking the CDF, we effectively make a Schnitt/Dedekind cut of probabilities at each point on the number line.
The event occurring n or fewer times (left of n, the Schnitt) have a given probability, and all values to the right have a given probability.
The interesting thing is that the magnitude of the number line is not proportional to the probability of occurrence.
Visualizing this might be possible with an area.
The event will happen n times or fewer in t time to the left of the cut, and more than n+1 times to the right of the cut.

1 - poisson.cdf(n, l)

### Exponential

[Notation: X is an exponential distribution.](https://en.wikipedia.org/wiki/Exponential_distribution#Probability_density_function)
An exponential distribution looks at the time between Poisson events.
Lambda has the meaning of rate here, as well as in the Poisson distribution.
However, the exponential distribution measures the probability,
not of a certain discrete number of events occurring in an interval of time,
but of a continuous amount of time elapsing between Poisson events.
The exponential distribution makes predictions with respect to a continuous quantity.

[^2]

from scipy.stats import expon

--P(wait < 1 min)--
expon.cdf(1, scale=0.5)

The scale is inversely as the dispersion.
With a smaller scale, we get a tighter distribution, with less horizontal disperson.
This is because of the definition F(x,s,theta) = F(x/s;1, theta)

The scale parameter is specified


### Uniform

### Binomial

[Without replacement, a binomial distribution is a hypergeometric one.](https://en.wikipedia.org/wiki/Binomial_distribution)
An example of a binomial distribution?
30 people take an exam. The number of successes is a binomial distribution.


### Chi

###


#### Footnotes

[^1]
[Check this for the meaning of the scale parameter.](https://en.wikipedia.org/wiki/Scale_parameter#Rate_parameter)

[^2] More differences between the Poisson and Exponential distributions.
Lambda in the Poisson distribution has the meaning of n events in t time.
Let's say that the average amount of support tickets created in a minute is 0.5.
In the exponential distribution, we would model this by saying 1/lambda.
Something must happen, and with the frequency of lambda.
The proportion of the the event's (growing) likelihood with respect to time.

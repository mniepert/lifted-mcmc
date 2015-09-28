# Introduction #

This document reports on additional experimental results. These will be added in an ongoing fashion.


# Markov logic networks #

The **infamous** smoker-cancer  Markov logic network.

```

friends(person,person)
smokes(person)
cancer(person)
1.4 !smokes(x)
2.3 !cancer(x)
4.6 !friends(x,y)
1.5 smokes(x) => cancer(x)
1.1 friends(x,y) ^ smokes(x) => smokes(y)
```

The smoker-cancer-asthma MLN by Vibhav Gogate.

```

friends(person, person)
asthma(person)
smokes(person)
cancer(person)
!asthma(v1) v !smokes(v1).
!asthma(v1) v !friends(v1, v2) v !smokes(v2).
!smokes(v1) v cancer(v1).
```



# Experimental Results #

We ran (a) the standard Gibbs sampler, (b) MC-SAT, and (c) the orbital Gibbs sampler and plotted the symmetric Kullback-Leibler divergence

![http://upload.wikimedia.org/wikipedia/en/math/7/f/f/7ff1f435ab3bc3cb4654ab665e7e57a2.png](http://upload.wikimedia.org/wikipedia/en/math/7/f/f/7ff1f435ab3bc3cb4654ab665e7e57a2.png)

on the single variable marginals. The exact single variable marginal probabilities were computed exactly using Van den Broeck et al's lifted knowledge compilation algorithm (taking about 2.0 seconds per variable).

Here's the plot for the smoker-cancer MLN with 50 people in the domain.

![http://lifted-mcmc.googlecode.com/files/MLN50.png](http://lifted-mcmc.googlecode.com/files/MLN50.png)

Here's the plot for the smoker-cancer MLN with 100 people in the domain.

![http://lifted-mcmc.googlecode.com/files/MLN100.png](http://lifted-mcmc.googlecode.com/files/MLN100.png)

Here's another plot for the asthma-smoker-cancer MLN with 50 people in the domain. We also plotted the irreversible orbital Gibbs sampler. Note the log-scale of the y-axis.

![http://lifted-mcmc.googlecode.com/files/asthma50.png](http://lifted-mcmc.googlecode.com/files/asthma50.png)
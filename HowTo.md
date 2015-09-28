# Manual #

Instructions on how to run the orbital Markov chains and the Rao-Blackwell estimator for MLNs.


  1. Install the [Gap System](http://www.gap-system.org/).
  1. Take the MLN and add your evidence. Here's an [example file](https://lifted-mcmc.googlecode.com/files/smokers_e10.mln).
  1. Use [WFOMC](http://dtai.cs.kuleuven.be/ml/systems/wfomc/) to ground the model to DIMACS: `java -jar wfomc.jar --ground --dimacs-out dimacs.cnf smokers_e10.mln > dummy.txt`
  1. Make sure that the altered Saucy version is in the current folder and executable (since this is based on the original [Saucy code](http://vlsicad.eecs.umich.edu/BK/SAUCY/), please contact me if you do not have this file!)
  1. Run (a) the orbital Gibbs sampler (orbital\_dimacs.g) or (b) the Rao-Blackwell estimator on Gibbs samples (rao-dimacs.g).
  * time gap -q -A < [orbital\_dimacs.g](https://lifted-mcmc.googlecode.com/files/orbital_dimacs.g)
  * time gap -q -A < [rao\_dimacs.g](https://lifted-mcmc.googlecode.com/files/rao_dimacs.g)

Note that for evaluation purposes, these files load the true marginals
at the beginning of the file:

```
# the correct marginals for evaluation purposes
# this is very problem dependent
Read("marginals.g");
```

You have to substitute this with the appropriate .g file. An example
file is available [here](https://lifted-mcmc.googlecode.com/files/marginals_smokers_e10.g). Moreover, there is a Gap file ([wfomc\_marginals.g](https://lifted-mcmc.googlecode.com/files/wfomc_marginals.g)) that generates a .g file storing the true marginals using WFOMC, if possible (i.e., domain-liftable with WFOMC). wfomc\_marginals.g calls WFOMC (marg.jar) for every variable.
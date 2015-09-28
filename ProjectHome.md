This is the project page for **Orbital Markov Chains** and the **symmetry-aware Rao-Blackwell estimator** both of which make probabilistic inference more efficient under model symmetries. The theory and some applications are described in the papers [Markov Chains on Orbits of Permutation Groups](http://arxiv.org/abs/1206.5396)  and [Symmetry-Aware Marginal Density Estimation](http://arxiv.org/abs/1304.2694).

**Orbital Markov Chains** are the first generally applicable class of symmetry-aware (lifted in SRL terms) MCMC algorithms for probabilistic inference. Orbital Markov chains implicitly  operate on a partition of the original state space. Orbital Markov chains mix more rapidly whenever there is symmetry in the model under consideration. Despite their exotic name, orbital Markov chains [work with very large graphical models](addresults.md)!

The **symmetry-aware Rao-Blackwell estimator** is applied as a post-processing step to standard sampling approaches such as MCMC. Under non-trivial model symmetries, its mean squared error is strictly smaller than that of the standard estimators. In fact, experiments have shown that it outperforms the standard estimators by several orders of magnitude in very large but highly symmetric graphical models.

The algorithms are implemented in the GAP programming language. GAP is a system for [computational discrete algebra](http://en.wikipedia.org/wiki/Computational_group_theory).

http://www.gap-system.org/

There are implementations of the [Orbital Markov chain](LiftedGibbs.md) and the [symmetry-aware Rao-Blackwell estimator](RaoBlackwellEstimator.md) in the GAP programming language. **There's also a [manual](HowTo.md).**

If you have a question and/or a model on which you want to run the symmetry-aware sampling approaches please let [me](http://www.matlog.net/research.php) know!
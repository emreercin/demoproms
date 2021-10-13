---
title: "Bayesian Network"
date: 2018-11-28T15:14:39+10:00
featured: true
weight: 2
---
Bayesian Networks (BNs) are graphical models that represent the combined probability distribution among a group of variables (Pearl, 1988).

A BN consists of two parts, the graphical structure and the parameters. The graphical structure is a directional acyclic graph. Nodes in the graph represent variables, edges represent relationships between variables. If two nodes A and B in a BA are directly connected from A to B by an edge, then A is the parent of B and B is the child of A. Each node has parameters that define its conditional probability distribution with its parents. In discrete BNs, these parameters are defined in conditional probability tables.

When a value is entered for any group of variables in the BN, the posterior probability distribution of other unknown variables can be calculated with inference algorithms such as a combination tree (Lauritzen and Spiegelhalter, 1988). The process of entering a value for a variable is also called entering evidence or entering an observation. With probabilistic inferences in the Bayes Network, predictive inference from parents to children, diagnostic inference from children to parents, or all-round inference between parents when the child is known can be calculated. Probabilities inference algorithms are useful for PROMs. When a value is entered into any set of questions in a PROM modeled as a BN, the posterior distributions of other questions and hidden factors can be calculated.

BNs can be made based on information, data, or a combination of the two. When the BN structure is made based on knowledge, the arrows in the model are determined according to the cause-effect relationships about the subject. BNs have structure learning algorithms to learn completely from data. These algorithms are divided into three groups as score-based, constraint-based and hybrid algorithms. Score-based algorithms aim to find the structure that rewards the fit of the model to the data, penalizes the model complexity, and optimizes the regulated scores (Gámez et al., 2011). Scores such as the Bayesian information criterion are suitable for this purpose. Constraint-based algorithms apply statistical tests to determine the conditional independence of the data and learn the BN structure compatible with the conditional independences detected (Le et al., 2019). Hybrid algorithms combine score-based and constraint-based principles. For example, the max-min climbing algorithm finds the graphical structure of the model without direction by applying constraint-based tests, then it aims to determine the directions using a score-based climbing algorithm (Tsamardinos et al., 2006).

__*Bu yazının Türkçe versiyonunu okumak için [tıklayınız](/services/bayes_aglari/).*__

# References

- Pearl, J. 1988. "Probabilistic Reasoning in Intelligent Systems". Morgan Kaufmann.
- Lauritzen, S. L., Spiegelhalter, D. J. 1988. "Local Computations with Probabilities on Graphical Structures and Their Application to Expert Systems". Journal of the Royal Statistical Society: Series B (Methodological), 50(2), 157–194.
- Gámez, J. A., Mateo, J. L., Puerta, J. M. 2011. "Learning Bayesian networks by hill climbing: efficient methods based on progressive restriction of the neighborhood". Data Mining and Knowledge Discovery, 22(1–2), 106–148.
- Le, T. D., Hoang, T., Li, J., Liu, L., Liu, H., Hu, S. 2019. "A Fast PC Algorithm for High Dimensional Causal Discovery with Multi-Core PCs". IEEE/ACM Transactions on Computational Biology and Bioinformatics, 16(5), 1483–1495.
- Tsamardinos, I., Brown, L. E., Aliferis, C. F. 2006. "The max-min hill-climbing Bayesian network structure learning algorithm". Machine Learning, 65(1), 31–78.

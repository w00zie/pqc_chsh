# Winning at CHSH with Parameterized Quantum Circuits and Bayesian Optimization

In this experiment I've tried to "win" a formulation of the CHSH game [1] in the formulation proposed by Mark Wilde [2] (*Sec. 3.6.2 : Entanglement in the CHSH Game*) and Ronald de Wolf [3] (*Sec. 15.2: CHSH: Clauser-Horne-Shimony-Holt*). 

This was done through the combined usage of [cirq](https://quantumai.google/cirq) and [bayesian optimization](https://github.com/fmfn/BayesianOptimization), as the goal is to find the optimal set of parameters that show the ability of winning at the CHSH game.

Starting from a small parameterized quantum circuit (7 parameterized gates and 3 Hadamard gates) randomly initialized, a global black-box optimization strategy was employed searching for the optimal parameters. 

The goal is to maximize the probability of winning the CHSH game and this is done alternating two phases: the first one is the simulation of the circuit, which leads us to a performance metric (the #wins/#runs ratio). This metric guides the optimizer in the second phase, searching for the set of parameters that maximize this ratio.

You can read my [blog post](https://w00zie.github.io/post/bell) for a few more details.

**Remark**: running the notebook multiple times will lead to (slightly) different results, due to the fact that I've not set a random seed. 

If you want to exactly reproduce the numbers you'll have to fix one yourself.

---

[1]: https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.23.880
[2]: http://www.markwilde.com/qit-notes.pdf
[3]: https://homepages.cwi.nl/~rdewolf/qcnotes.pdf
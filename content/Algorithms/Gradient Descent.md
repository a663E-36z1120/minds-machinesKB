**Gradient Descent** is an iterative gradient-based algorithm for performing (proximal) optimization on a set of differentiable variables with respect to a [[loss function]] when directly computing the optimum is costly or outright impossible.

Intuitively, we can imagine the parameters of the loss function form a "loss landscape", where at each update the gradient points toward approximately where the optimum is. With each iteration, we walk a path down the loss landscape guided by these gradients toward a proximal optimum.

Formally, we minimise a differentiable loss function $\mathcal L(\theta)$ with respect to parameters $\theta\in\mathbb R^{d}$ as follows:
$$
\theta_{t+1} \;=\; \theta_{t} \;-\; \eta_t \,\nabla_\theta \mathcal L(\theta_t)
$$
where:
- $\nabla_\theta \mathcal L(\theta_t)$ is the gradient (direction of steepest increase)
- $\eta_t>0$ is the learning‑rate. (i.e. step size along the optimisation path)

#algorithm
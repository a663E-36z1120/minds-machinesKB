
Minimise a differentiable loss function $\mathcal L(\theta)$ with respect to parameters $\theta\in\mathbb R^{d}$.

**Core update**

θt+1  =  θt  −  ηt ∇θL(θt),\theta_{t+1} \;=\; \theta_{t} \;-\; \eta_t \,\nabla_\theta \mathcal L(\theta_t),

where ∇θL(θt)\nabla_\theta \mathcal L(\theta_t) is the gradient (direction of steepest increase) and ηt>0\eta_t>0 is the learning‑rate. Stepping opposite the gradient yields the largest first‑order decrease in loss. For small ηt\eta_t:

L(θt+1)  ≈  L(θt)−ηt ∥∇θL(θt)∥2,\mathcal L(\theta_{t+1}) \;\approx\; \mathcal L(\theta_t) - \eta_t \,\|\nabla_\theta \mathcal L(\theta_t)\|^{2},


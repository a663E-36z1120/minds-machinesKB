The ***backpropagation*** algorithm optimizes the parameters of an [[artificial neural network]] undergoing [[deep learning]] through [[gradient descent]]. This happens in two passes similar to in a control loop in a [[control system]].

**1 .  Forward pass**  
For each layer $\ell=1,\dots,L$ of feed-forward neural network:
$$
\begin{aligned}
z_\ell &= W_\ell h_{\ell-1}+b_\ell \\[2pt]
h_\ell &= \phi_\ell(z_\ell)
\end{aligned}
$$
with $h_0 = x$. At the output layer obtain the loss $\mathcal L(h_L,y)$.

**2 .  Initialise the output error**  
$$
\delta_L = \nabla_{h_L}\mathcal L \;\; \odot \;\; \phi_L'(z_L)
$$
(“Hadamard”  $\odot$ = element‑wise product).

---

#### 3 .  Back‑propagate the error  
For layers \( \ell=L-1,\dots,1 \):

\[
\delta_\ell \;=\; (W_{\ell+1}^{\!\top}\,\delta_{\ell+1}) \;\odot\; \phi_\ell'(z_\ell)
\]

---

#### 4 .  Compute gradients  
\[
\frac{\partial \mathcal L}{\partial W_\ell}= \delta_\ell\,h_{\ell-1}^{\!\top},\qquad
\frac{\partial \mathcal L}{\partial b_\ell}= \delta_\ell
\]

These matrices/vectors are the exact derivatives needed for an update such as  
\( W_\ell \leftarrow W_\ell - \eta\,\partial\mathcal L/\partial W_\ell \).

---

#### 5 .  Complexity  
Back‑prop uses **reverse‑mode automatic differentiation**; its cost is at most a small constant factor of the forward pass (same FLOPs, plus storing activations).

---

#### 6 .  Intuition  
*The chain rule inside‑out.*  
Errors are first measured at the output, then **propagate backward** through transposed weight matrices, being scaled by each layer’s activation derivative.  Each weight learns in proportion to (error signal) × (input activation).

---

Back‑prop is the engine that makes modern deep learning trainable: it provides an efficient, exact gradient for *any* acyclic computation graph composed of differentiable operations.
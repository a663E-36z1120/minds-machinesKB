The ***backpropagation*** algorithm optimizes the parameters of an [[artificial neural network]] undergoing [[deep learning]] through [[gradient descent]]. 

This happens in two passes similar to in a control loop in a [[control system]]. The idea is to essentially apply the chain rule "inside-out" and backwards, which goes as follows:

---
**1 .  Forward Pass**  
For each layer $\ell=1,\dots,L$ of feed-forward neural network (e.g. multi-layer [[perceptron]]s (MLP)), with weights $W$, bias $b$, activation function $\phi$, hidden state (activity of previous layer) $h$, output $z$:
$$
\begin{aligned}
z_\ell &= W_\ell h_{\ell-1}+b_\ell \\
h_\ell &= \phi_\ell(z_\ell)
\end{aligned}
$$
For the first layer, $h_0 = x$, which is the training data. 
At the output layer, we obtain the loss according to a [[loss function]] $\mathcal{L}$:
$$\mathcal L(h_L,y)$$
where $y$ is the data label and $h_L$ is the activity from the final layer.

---
**2.  Backward Pass**
In the backward pass we propagate the **error signal** $\delta$ backward; error signal is the quantity that tells each weight how much it contributed to the final loss, namely:
$$\;\delta_\ell \;=\; \frac{\partial\mathcal L}{\partial z_\ell}$$
We start by getting the first error signal for the last layer, where we apply chain rule to $\mathcal L(h_L=\phi_L(z_L),y)$:
$$
\delta_L = \frac{\partial\mathcal L}{\partial z_L} = \nabla_{h_L}\mathcal L \; \odot \;\phi_L'(z_L)
$$
($\odot$ is the element‑wise product operator).

Then, for any layers $\ell=L-1,\dots,1$, we can derive the error signal from the error signal propagated back from later layers by applying chain rule to $z_{\ell+1} = W_{\ell+1} \phi_\ell(z_\ell)+b_{\ell+1}$:
$$
\;\delta_\ell = \frac{\partial\mathcal L}{\partial z_\ell}=\frac{\partial\mathcal L}{\partial z_{\ell+1}}\frac{\partial z_{\ell+1}}{\partial z_\ell} =\delta_{\ell+1}\odot \bigl(W_{\ell+1}^{\!\top}\phi_\ell'(z_\ell)\bigr)
$$
Finally, we can apply the chain rule to $z_\ell = W_\ell h_{\ell-1}+b_\ell$ to derive the weight and bias gradients from the error signal:
$$
\frac{\partial \mathcal L}{\partial W_\ell}= \frac{\partial\mathcal L}{\partial z_\ell} \frac{\partial z_\ell}{\partial W_\ell}= \delta_\ell\,h_{\ell-1}^{\!\top},\qquad
\frac{\partial \mathcal L}{\partial b_\ell}=\frac{\partial \mathcal{L}}{\partial z_\ell}\frac{\partial z_\ell}{\partial b_\ell}= \delta_\ell
$$
This allows to perform a [[gradient descent]] update step for the parameters of layer $l$:
$$ W_\ell \leftarrow W_\ell - \eta\,\frac{\partial\mathcal L}{\partial W_\ell} \qquad b_\ell \leftarrow b_\ell - \eta\,\frac{\partial\mathcal L}{\partial b_\ell}$$
where $\eta$ is the learning rate.

---

With the updated weights, we perform the forward pass again, rinse and repeat until (hopefully) convergence.
The **Universal‑Approximation Theorem (UAT)** essentially states that a feed‑forward [[artificial neural network]] with **just one hidden layer** of finitely many neurons — and a broad class of non‑linear [[activation function]]s (sigmoid, tanh, ReLU, etc.) — can approximate **any continuous function** $f:K\!\to\!\mathbb R^m$ on a compact domain $K\subset\mathbb R^n$ **arbitrarily well** in the uniform (sup‑norm) sense.

Formally, for every $\varepsilon>0$ there exists a width $N$, parameters $\{w_i,b_i,v_i\}_{i=1}^N$, and non-linear activation function $\sigma$ such that the network $\hat f(x)=\sum_{i=1}^N v_i\,\sigma(w_i^\top x+b_i)$ satisfies $\|f-\hat f\|_\infty<\varepsilon$ on $K$.

 #idea
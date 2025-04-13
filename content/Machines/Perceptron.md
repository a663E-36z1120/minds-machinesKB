A **perceptron** is a single-layer [[Artificial Neural Network]], first proposed by [[Frank Rosenblatt]] in 1958. 

**Structure**
It takes a vector of inputs $x_1,\dots,x_n,$ multiplies each by a weight $w_i$, adds a bias $b$, forms a weighted sum $z=\sum_i w_i x_i + b$, and passes $z$ through an ***hardlim*** [[Activation Function]], where:
$$\text{hardlim}(z)= \begin{cases} 1 & \text{if } z \ge 0,\\[4pt] 0 & \text{if } z < 0. \end{cases}$$

**Learning rule**
For each misclassified training example, update the weights:
    
$$w_i \leftarrow w_i + \eta\, (y - \hat y)\, x_i,\qquad b \leftarrow b + \eta\, (y - \hat y)$$
where $y$ is the true label, $\hat{y}$ the prediction, and $\eta$ the learning rate. This rule provably converges if a separating hyperplane exists.

Geometrically, the perceptron learns a **linear*** hyperplane that separates the input space into two classes; everything on one side is labeled 1, the other side 0. Hence a perceptron can represent any **linearly separable** Boolean function (e.g., AND, OR) but not non‑linear ones like XOR.

#machine
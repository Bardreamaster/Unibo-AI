## HW1

### Ex1

**Observations:**

- η=0.05: Convergence is slow because the step size is too small.
- η=0.2: Fast convergence to the unique minimizer
- η=1.0: Oscillation/Divergence occurs because the step size is too large, causing the iterates to overshoot the minimum.

### Ex2

**Why different initializations converge to different minima?**

Different initial points may converge to different local minima because the function is non-convex

**How backtracking automatically chooses a suitable step size at each iteration?**

- **Initialization (初始化):** The algorithm typically starts with an initial step size $\alpha = 1$.
- **The Armijo Condition (Armijo 准则):** At each step, it checks if the new function value satisfies the Armijo condition: $f(x + \alpha p) \le f(x) + c \alpha \nabla f(x)^T p$. This condition ensures that the reduction in the function value is proportional to the step size and the steepness of the gradient.
- **Contraction (缩减):** If the condition is not met (meaning the step is too large and potentially overshooting the minimum), the step size is reduced by multiplying it by a contraction factor $\tau$
- **Iteration (迭代):** This process repeats until the Armijo condition is satisfied, at which point the current $\alpha$ is accepted as the step size for that iteration.

**Situations where constant step size would fail.**

1. The Step Size is "Too Large" (Divergence and Oscillation)Sign Flipping
2. The Step Size is "Too Small" (Slow Convergence)
3. Ill-Conditioned Problems (Narrow Valleys)


### Ex3



## HW2

### Ex1

**Why GD is smooth but slow for large?**

GD uses the full dataset to compute the gradient at each iteration, resulting in a smooth and stable convergence path. However, this also means that each iteration is computationally expensive, especially for large datasets, leading to slower overall progress.

**Why SGD is noisy but progresses faster?**

SGD computes the gradient using only a small subset (mini-batch) of the data at each iteration. This introduces noise into the gradient estimates, causing the optimization path to be more erratic. However, because each iteration is much faster to compute, SGD can make quicker progress towards the minimum, especially in large datasets.

**How batch size affects the noise level and convergence stability.**

For fixed noise level, larger batch sizes reduce the variance of the gradient estimates, leading to a more stable convergence path. However, this comes at the cost of increased computational time per iteration. Conversely, smaller batch sizes introduce more noise into the gradient estimates, which can lead to faster but less stable convergence.

### Ex2

**Why the variance decreases with larger batches?**

Because larger batches provide a more accurate estimate of the true gradient by averaging over more data points.

**Why SGD becomes more stable as batch size increases?**

Because larger batches reduce the variance in the gradient estimates, leading to more consistent and reliable updates.

**The trade-off between stability and computational cost.**

Larger batch sizes improve stability by reducing gradient variance, but they also increase computational cost per iteration. Smaller batches are computationally cheaper but introduce more noise, leading to less stable convergence.

### Ex3

**How noise helps escape shallow minima or bad regions?**

For shallow minima or bad regions, the noise in SGD can provide the necessary perturbations to help the optimization process escape these areas. The stochastic nature of SGD allows it to explore the parameter space more broadly, increasing the chances of finding a better minimum.

**How too much noise prevents convergence?**

At the end of training, excessive noise can prevent the optimization process from settling into a minimum. Because the area is flat, the noisy updates can keep pushing the parameters around, preventing convergence to a stable solution.

### Ex4

**Why GD gives a smooth curve and SGD oscillates.**

For full gradient, GD computes the exact gradient using the entire dataset, resulting in smooth and consistent updates. In contrast, SGD uses mini-batches, introducing noise into the gradient estimates, which causes oscillations (in the optimization path).

**Why larger batches reduce noise but cost more per iteration.**

Larger batches provide more accurate gradient estimates by averaging over more data points, which reduces the variance (noise) in the updates. However, processing larger batches requires more computational resources and time per iteration.

**Why all methods roughly converge to the same region.**

All methods aim to minimize the same objective function, so despite differences in their update rules and noise levels, they tend to converge to similar regions in the parameter space where the objective function has low values.

**Why SGD is more suitable for large datasets, even when noisy.**

SGD is more suitable for large datasets because it requires less memory and computational power per iteration compared to GD. Even though SGD introduces noise, its ability to make frequent updates allows it to explore the parameter space more effectively, leading to faster convergence in practice.

And there are more parameters to tune on a large dataset, SGD could help escape shallow minima which could be more common in high-dimensional space.

## HW3

### Ex1

**why the decision boundary of Logistic Regression is linear?**

### Ex2

**Compare the stability and speed of convergence over the choice of different batch sizes.**

**Why the gradients become noisier for small batches? Why larger batches give smoother curves?**

Larger batches give smoother curves because averaging the gradients over more samples reduces the variance of the gradient estimate. As the batch size approaches N, the estimated gradient converges to the true (full) gradient, eliminating stochastic noise and resulting in a smooth, deterministic descent path

### Ex3

**How lower thresholds increase recall and lower precision,**

**How higher thresholds increase precision and reduce recall,**

**Why classification metrics depend on the application (as discussed in class).**


### Ex4

**Explain why normalization is required, connecting to:**
    - conditioning,
    - stable optimization,
    - meaningful gradient magnitudes.

**Discuss on which method converge faster, which oscillate more, and how this relates to adaptive learning rates discussed in class.**


## HW4

### Ex1

**why singular values appear in descending order, why small singular values correspond to “less important” directions, and why floating-point arithmetic makes exact zeros rare.**


### Ex2

**why SVD gives the *optimal* rank-$k$ approximation**

### Ex3

**How visual quality improves with $k$,**


**Why most of the “energy” is contained in the first singular values,**


**The trade-off between compression and fidelity,**


**The connection between SVD and optimal low-rank approximation.**



### Ex5

### Ex6

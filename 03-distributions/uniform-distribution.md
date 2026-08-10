# Uniform Distribution

[← Back to Course README](../README.md)

- [Uniform Distribution on an Interval [a, b]](#uniform-distribution-on-an-interval-a-b)
- [Derivation of Mean and Variance](#derivation-of-mean-and-variance)
- [Derivation of the Mean $E[X]$](#derivation-of-the-mean-ex)
- [Derivation of the Variance $Var(X)$](#derivation-of-the-variance-varx)
- [2-Dimensional Uniform Distribution](#2-dimensional-uniform-distribution)
- [Solved Problems](#solved-problems)
  - [Question 45: Point on Line Segment](#question-45-point-on-line-segment)
  - [Question 46: Uniform Interval Parameter Alpha](#question-46-uniform-interval-parameter-alpha)
  - [Question 47: 2D Uniform Distribution over Bounded Region](#question-47-2d-uniform-distribution-over-bounded-region)

> **Topic**: Uniform Distribution: Uniform Distribution on an Interval [a, b], Derivation of Mean and Variance, Derivation of the Mean $E[X]$, Derivation of the Variance $Var(X)$

---

## Uniform Distribution on an Interval [a, b]

A continuous random variable $X$ is said to have a uniform distribution on the interval $[a, b]$ if its probability density function (PDF) is given by:
$f(x) = \begin{cases} \frac{1}{b-a} & \text{for } a \le x \le b \\ 0 & \text{otherwise} \end{cases}$


---

## Derivation of Mean and Variance

For a Uniform Distribution on the interval $[a, b]$, the probability density function (PDF) is given by:
$f(x) = \begin{cases} \frac{1}{b-a} & \text{for } a \le x \le b \\ 0 & \text{otherwise} \end{cases}$


---

## Derivation of the Mean $E[X]$

The mean (expected value) of a continuous random variable is defined as $E[X] = \int_{-\infty}^{\infty} x \cdot f(x) dx$.

*   **Step 1: Set up the integral for $E[X]$**
    Since $f(x)$ is non-zero only for $a \le x \le b$, the integral becomes:
    $E[X] = \int_{a}^{b} x \cdot \frac{1}{b-a} dx$

*   **Step 2: Factor out the constant and integrate**
    $E[X] = \frac{1}{b-a} \int_{a}^{b} x dx$
    $E[X] = \frac{1}{b-a} \left[ \frac{x^2}{2} \right]_{a}^{b}$

*   **Step 3: Evaluate the definite integral**
    $E[X] = \frac{1}{b-a} \left( \frac{b^2}{2} - \frac{a^2}{2} \right)$
    $E[X] = \frac{1}{2(b-a)} (b^2 - a^2)$

*   **Step 4: Simplify using the difference of squares formula ($b^2 - a^2 = (b-a)(b+a)$)**
    $E[X] = \frac{1}{2(b-a)} (b-a)(b+a)$
    $E[X] = \frac{a+b}{2}$
    Thus, the mean of a Uniform Distribution is $\frac{a+b}{2}$.


---

## Derivation of the Variance $Var(X)$

The variance is defined as $Var(X) = E[X^2] - (E[X])^2$. We already know $E[X] = \frac{a+b}{2}$.
First, we need to find $E[X^2]$.

*   **Step 1: Set up the integral for $E[X^2]$**
    $E[X^2] = \int_{-\infty}^{\infty} x^2 \cdot f(x) dx$
    $E[X^2] = \int_{a}^{b} x^2 \cdot \frac{1}{b-a} dx$

*   **Step 2: Factor out the constant and integrate**
    $E[X^2] = \frac{1}{b-a} \int_{a}^{b} x^2 dx$
    $E[X^2] = \frac{1}{b-a} \left[ \frac{x^3}{3} \right]_{a}^{b}$

*   **Step 3: Evaluate the definite integral**
    $E[X^2] = \frac{1}{b-a} \left( \frac{b^3}{3} - \frac{a^3}{3} \right)$
    $E[X^2] = \frac{1}{3(b-a)} (b^3 - a^3)$

*   **Step 4: Simplify using the difference of cubes formula ($b^3 - a^3 = (b-a)(b^2 + ab + a^2)$)**
    $E[X^2] = \frac{1}{3(b-a)} (b-a)(b^2 + ab + a^2)$
    $E[X^2] = \frac{b^2 + ab + a^2}{3}$

*   **Step 5: Substitute $E[X^2]$ and $E[X]$ into the variance formula**
    $Var(X) = E[X^2] - (E[X])^2$
    $Var(X) = \frac{b^2 + ab + a^2}{3} - \left( \frac{a+b}{2} \right)^2$
    $Var(X) = \frac{b^2 + ab + a^2}{3} - \frac{a^2 + 2ab + b^2}{4}$

*   **Step 6: Find a common denominator and combine terms**
    The common denominator is 12.
    $Var(X) = \frac{4(b^2 + ab + a^2) - 3(a^2 + 2ab + b^2)}{12}$
    $Var(X) = \frac{4b^2 + 4ab + 4a^2 - 3a^2 - 6ab - 3b^2}{12}$
    $Var(X) = \frac{b^2 - 2ab + a^2}{12}$

*   **Step 7: Recognize the perfect square trinomial ($b^2 - 2ab + a^2 = (b-a)^2$)**
    $Var(X) = \frac{(b-a)^2}{12}$
    Thus, the variance of a Uniform Distribution is $\frac{(b-a)^2}{12}$.


---

## 2-Dimensional Uniform Distribution


For a 2-dimensional random variable $(X,Y)$ uniformly distributed over a region $R$ in the plane, the joint PDF is given by:
$f(x,y) = \begin{cases} \frac{1}{\text{Area of } R} & \text{for } (x,y) \in R \\ 0 & \text{otherwise} \end{cases}$
This is a valid PDF because the integral of $f(x,y)$ over the entire region $R$ equals 1.


---

## Solved Problems


---

### Question 45: Point on Line Segment

> **Question:** A point is chosen at random on a line segment $[0, 2]$. What is the probability that the chosen point lies between 1 and 3/2?
>
> **Answer:**
> *   **Step 1:** Identify the interval and the PDF.
> The line segment is $[0, 2]$, so $a=0$ and $b=2$.
> The PDF for a uniform distribution on $[a, b]$ is $f(x) = \frac{1}{b-a}$.
> Here, $f(x) = \frac{1}{2-0} = \frac{1}{2}$ for $0 \le x \le 2$.
> *   **Step 2:** Define the event of interest.
> We want to find the probability that the chosen point lies between 1 and 3/2, i.e., $P(1 < X < 3/2)$.
> *   **Step 3:** Calculate the probability by integrating the PDF over the specified interval.
> $P(1 < X < 3/2) = \int_{1}^{3/2} f(x) dx = \int_{1}^{3/2} \frac{1}{2} dx$
> *   **Step 4:** Evaluate the integral.
> $P(1 < X < 3/2) = \frac{1}{2} [x]_{1}^{3/2} = \frac{1}{2} \left(\frac{3}{2} - 1\right) = \frac{1}{2} \left(\frac{1}{2}\right) = \frac{1}{4}$
>
>
> ---


### Question 46: Uniform Interval Parameter Alpha

> **Question:** Suppose $X$ is uniformly distributed on $[-\alpha, \alpha]$, where $\alpha > 0$. Determine $\alpha$ so that the following conditions are satisfied:
>
> (i) $P[X > 1] = 1/3$
> (ii) $P[|X| > 1] = 1/2$
> (iii) $P[|X| < 4/3] = 0.7$
> (iv) $P[|X| < 1/2] = 0.3$
> (v) $P[|X| < 1] = P[|X| > 1]$
>
> **Answer:**
> The PDF for $X$ uniformly distributed on $[-\alpha, \alpha]$ is $f(x) = \frac{1}{2\alpha}$ for $-\alpha \le x \le \alpha$.
>
> **(i) $P[X > 1] = 1/3$**
> *   **Step 1:** Set up the integral for $P(X > 1)$. This requires $1 < \alpha$ for the interval to be valid.
> $P(X > 1) = \int_{1}^{\alpha} \frac{1}{2\alpha} dx$
> *   **Step 2:** Evaluate the integral.
> $P(X > 1) = \frac{1}{2\alpha} [x]_{1}^{\alpha} = \frac{\alpha - 1}{2\alpha}$
> *   **Step 3:** Set the result equal to $1/3$ and solve for $\alpha$.
> $\frac{\alpha - 1}{2\alpha} = \frac{1}{3}$
> $3(\alpha - 1) = 2\alpha$
> $3\alpha - 3 = 2\alpha$
> $\alpha = 3$
>
> **(ii) $P[|X| > 1] = 1/2$**
> *   **Step 1:** Understand $|X| > 1$. This means $X > 1$ or $X < -1$. Due to symmetry, $P(X > 1) = P(X < -1)$.
> $P(|X| > 1) = P(X > 1) + P(X < -1) = 2 \times P(X > 1)$.
> *   **Step 2:** Calculate $P(X > 1)$ (assuming $1 < \alpha$).
> $P(X > 1) = \int_{1}^{\alpha} \frac{1}{2\alpha} dx = \frac{\alpha - 1}{2\alpha}$
> *   **Step 3:** Substitute into the equation for $P(|X| > 1)$.
> $P(|X| > 1) = 2 \times \frac{\alpha - 1}{2\alpha} = \frac{\alpha - 1}{\alpha}$
> *   **Step 4:** Set the result equal to $1/2$ and solve for $\alpha$.
> $\frac{\alpha - 1}{\alpha} = \frac{1}{2}$
> $2(\alpha - 1) = \alpha$
> $2\alpha - 2 = \alpha$
> $\alpha = 2$
>
> **(iii) $P[|X| < 4/3] = 0.7$**
> *   **Step 1:** Understand $|X| < 4/3$. This means $-4/3 < X < 4/3$. This requires $4/3 < \alpha$.
> *   **Step 2:** Set up and evaluate the integral.
> $P(|X| < 4/3) = \int_{-4/3}^{4/3} \frac{1}{2\alpha} dx = \frac{1}{2\alpha} [x]_{-4/3}^{4/3}$
> $P(|X| < 4/3) = \frac{1}{2\alpha} \left(\frac{4}{3} - (-\frac{4}{3})\right) = \frac{1}{2\alpha} \left(\frac{8}{3}\right) = \frac{4}{3\alpha}$
> *   **Step 3:** Set the result equal to $0.7$ and solve for $\alpha$.
> $\frac{4}{3\alpha} = 0.7 = \frac{7}{10}$
> $40 = 21\alpha$
> $\alpha = \frac{40}{21} \approx 1.905$
>
> **(iv) $P[|X| < 1/2] = 0.3$**
> *   **Step 1:** Understand $|X| < 1/2$. This means $-1/2 < X < 1/2$.
> *   **Step 2:** Set up and evaluate the integral.
> $P(|X| < 1/2) = \int_{-1/2}^{1/2} \frac{1}{2\alpha} dx = \frac{1}{2\alpha} [x]_{-1/2}^{1/2}$
> $P(|X| < 1/2) = \frac{1}{2\alpha} \left(\frac{1}{2} - (-\frac{1}{2})\right) = \frac{1}{2\alpha} (1) = \frac{1}{2\alpha}$
> *   **Step 3:** Set the result equal to $0.3$ and solve for $\alpha$.
> $\frac{1}{2\alpha} = 0.3 = \frac{3}{10}$
> $10 = 6\alpha$
> $\alpha = \frac{10}{6} = \frac{5}{3} \approx 1.667$
>
> **(v) $P[|X| < 1] = P[|X| > 1]$**
> *   **Step 1:** Calculate $P(|X| < 1)$. This means $-1 < X < 1$. Requires $1 < \alpha$.
> $P(|X| < 1) = \int_{-1}^{1} \frac{1}{2\alpha} dx = \frac{1}{2\alpha} [x]_{-1}^{1} = \frac{1}{2\alpha} (1 - (-1)) = \frac{2}{2\alpha} = \frac{1}{\alpha}$
> *   **Step 2:** Calculate $P(|X| > 1)$. This is the complement of $P(|X| \le 1)$. Since $X$ is continuous, $P(|X| \le 1) = P(|X| < 1)$.
> $P(|X| > 1) = 1 - P(|X| \le 1) = 1 - P(|X| < 1) = 1 - \frac{1}{\alpha}$
> *   **Step 3:** Set the two probabilities equal and solve for $\alpha$.
> $\frac{1}{\alpha} = 1 - \frac{1}{\alpha}$
> $\frac{2}{\alpha} = 1$
> $\alpha = 2$
>
>
>
> ---


### Question 47: 2D Uniform Distribution over Bounded Region

> **Question:** Suppose that the 2-D RV $(x,y)$ is uniformly distributed over the region $R$ bounded b/w $y=x$ and $y=x^2$. Find the marginal PDF of $x$ & $y$.
>
> **Answer:**
> *   **Step 1: Find the Area of Region R.**
> The region is bounded by $y=x^2$ and $y=x$, which intersect at $(0,0)$ and $(1,1)$.
> $$\text{Area of } R = \int_{0}^{1} (x - x^2) dx = \left[ \frac{x^2}{2} - \frac{x^3}{3} \right]_{0}^{1} = \frac{1}{2} - \frac{1}{3} = \frac{1}{6}$$
> *   **Step 2: Set up the Joint PDF.**
> The joint PDF is $f(x,y) = \frac{1}{1/6} = 6$ for $0<x<1, x^2<y<x$.
> *   **Step 3: Calculate the Marginal PDF of x.**
> $g(x) = \int_{y=x^2}^{x} 6 dy = 6[y]_{y=x^2}^{x} = 6(x-x^2)$ for $0<x<1$.
> *   **Step 4: Calculate the Marginal PDF of y.**
> The bounds for $x$ are from $y$ to $\sqrt{y}$.
> $h(y) = \int_{x=y}^{\sqrt{y}} 6 dx = 6[x]_{x=y}^{\sqrt{y}} = 6(\sqrt{y} - y)$ for $0<y<1$.
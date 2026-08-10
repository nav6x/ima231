# Moment Generating Functions (MGF)

[← Back to Course README](../README.md)

- [Definition of MGF](#definition-of-mgf)
- [Finding Moments from the MGF](#finding-moments-from-the-mgf)
- [Deriving the Mean (1st Moment)](#deriving-the-mean-1st-moment)
- [Deriving the Variance (from 1st and 2nd Moments)](#deriving-the-variance-from-1st-and-2nd-moments)
- [Property: MGF of a Sum of Independent RVs](#property-mgf-of-a-sum-of-independent-rvs)
  - [Question 26: MGF of Continuous Exponential RV](#question-26-mgf-of-continuous-exponential-rv)
- [Homework Question: MGF of Exponential Distribution](#homework-question-mgf-of-exponential-distribution)
- [MGF for Standard Distributions](#mgf-for-standard-distributions)
- [Poisson Distribution](#poisson-distribution)
- [Binomial Distribution](#binomial-distribution)
  - [Question 27: MGF of Discrete Geometric-type RV](#question-27-mgf-of-discrete-geometric-type-rv)

> **Topic**: Moment Generating Functions (MGF): Definition of MGF, Finding Moments from the MGF, Deriving the Mean (1st Moment), Deriving the Variance (from 1st and 2nd Moments)

---

## Definition of MGF

The MGF of a random variable X, denoted $M_X(t)$, is defined as the expected value of $e^{tX}$:

$M_X(t) = E[e^{tX}]$

-   For a **discrete random variable (d.r.v)** with PMF $p(x_i)$:
    $M_X(t) = \sum_{i} e^{tx_i} p(x_i)$

-   For a **continuous random variable (c.r.v)** with PDF $f(x)$:
    $M_X(t) = \int_{-\infty}^{\infty} e^{tx} f(x) dx$


---

## Finding Moments from the MGF

The $n^{th}$ moment about the origin, $E[X^n]$, can be found by taking the $n^{th}$ derivative of the MGF with respect to $t$ and then evaluating the result at $t=0$.

$E[X^n] = M_X^{(n)}(0) = \left. \frac{d^n}{dt^n} M_X(t) \right|_{t=0}$


---

## Deriving the Mean (1st Moment)

*   **Concept:** The mean, $E[X]$, is the first moment. We find it by taking the first derivative of the MGF and evaluating it at $t=0$.

*   **Step 1: Expand $e^{tX}$ as a Taylor Series.**
    $e^{tX} = 1 + tX + \frac{(tX)^2}{2!} + \frac{(tX)^3}{3!} + \dots$

*   **Step 2: Find the expectation of the series.**
    $M_X(t) = E[e^{tX}] = E[1 + tX + \frac{t^2X^2}{2!} + \dots]$
    Using the linearity of expectation, this becomes:
    $M_X(t) = 1 + tE[X] + \frac{t^2}{2!}E[X^2] + \dots$

*   **Step 3: Differentiate with respect to t.**
    $M_X'(t) = \frac{d}{dt}M_X(t) = E[X] + tE[X^2] + \frac{t^2}{2}E[X^3] + \dots$

*   **Step 4: Evaluate at t=0.**
    $M_X'(0) = E[X] + 0 + 0 + \dots = E[X]$.


---

## Deriving the Variance (from 1st and 2nd Moments)

*   **Concept:** The variance is given by $V(X) = E[X^2] - (E[X])^2$. We can find $E[X^2]$ from the second derivative of the MGF.

*   **Step 1: Differentiate $M_X'(t)$ to get the second derivative.**
    $M_X''(t) = \frac{d}{dt}M_X'(t) = E[X^2] + tE[X^3] + \dots$

*   **Step 2: Evaluate at t=0.**
    $M_X''(0) = E[X^2] + 0 + \dots = E[X^2]$.

*   **Step 3: Calculate the variance.**
    $V(X) = E[X^2] - (E[X])^2 = M_X''(0) - [M_X'(0)]^2$.


---

## Property: MGF of a Sum of Independent RVs

If X and Y are independent random variables with MGFs $M_X(t)$ and $M_Y(t)$ respectively, then the MGF of their sum, $Z = X+Y$, is:

$M_{X+Y}(t) = M_X(t) M_Y(t)$

*   **Proof:**
    $M_{X+Y}(t) = E[e^{t(X+Y)}] = E[e^{tX}e^{tY}]$.
    Because X and Y are independent, the expectation of their product is the product of their expectations:
    $E[e^{tX}e^{tY}] = E[e^{tX}]E[e^{tY}] = M_X(t)M_Y(t)$. **(Proved)**


---

### Question 26: MGF of Continuous Exponential RV

> A RV X has PDF $f(x) = \begin{cases} 2e^{-2x} & x \ge 0 \\ 0 & x < 0 \end{cases}$.
> (i) Find the MGF.
> (ii) Using the MGF, find the first two moments about the origin and the variance.
>
> **Answer**
>
> *   **Concept:** This is an exponential distribution with rate parameter $\lambda = 2$. We will calculate the MGF by integration and then differentiate it to find the moments.
>
> **(i) Find the MGF**
>
> *   **Step 1: Set up the integral for the MGF.**
> $M_X(t) = E[e^{tX}] = \int_{0}^{\infty} e^{tx} (2e^{-2x}) \,dx = 2 \int_{0}^{\infty} e^{tx-2x} \,dx = 2 \int_{0}^{\infty} e^{-x(2-t)} \,dx$.
>
> *   **Step 2: Solve the integral.** (This requires $2-t > 0$, so $t<2$)
> $M_X(t) = 2 \left[ \frac{e^{-x(2-t)}}{-(2-t)} \right]_{0}^{\infty} = \frac{-2}{2-t} [e^{-\infty} - e^0] = \frac{-2}{2-t} [0 - 1] = \frac{2}{2-t}$.
>
> **(ii) Find the moments and variance**
>
> *   **Step 1: Find the first moment (Mean).**
> $M_X'(t) = \frac{d}{dt} \left( 2(2-t)^{-1} \right) = 2(-1)(2-t)^{-2}(-1) = \frac{2}{(2-t)^2}$.
> $E[X] = M_X'(0) = \frac{2}{(2-0)^2} = \frac{2}{4} = \frac{1}{2}$.
>
> *   **Step 2: Find the second moment.**
> $M_X''(t) = \frac{d}{dt} \left( 2(2-t)^{-2} \right) = 2(-2)(2-t)^{-3}(-1) = \frac{4}{(2-t)^3}$.
> $E[X^2] = M_X''(0) = \frac{4}{(2-0)^3} = \frac{4}{8} = \frac{1}{2}$.
>
> *   **Step 3: Calculate the variance.**
> $V(X) = E[X^2] - (E[X])^2 = \frac{1}{2} - (\frac{1}{2})^2 = \frac{1}{2} - \frac{1}{4} = \frac{1}{4}$.
>
>
>
> ---


## Homework Question: MGF of Exponential Distribution

Find the MGF of the exponential distribution $f(x) = \lambda e^{-\lambda x}$ for $x > 0$. Using the MGF, find its mean and variance.

**Answer**

*   **Step 1: Find the MGF.**
    $M_X(t) = \int_{0}^{\infty} e^{tx} (\lambda e^{-\lambda x}) \,dx = \lambda \int_{0}^{\infty} e^{-x(\lambda-t)} \,dx$.
    For the integral to converge, $\lambda-t > 0$, so $t < \lambda$.
    $M_X(t) = \lambda \left[ \frac{e^{-x(\lambda-t)}}{-(\lambda-t)} \right]_{0}^{\infty} = \frac{-\lambda}{\lambda-t}[0 - 1] = \frac{\lambda}{\lambda-t}$.

*   **Step 2: Find the Mean.**
    $M_X'(t) = \frac{d}{dt}(\lambda(\lambda-t)^{-1}) = \lambda(-1)(\lambda-t)^{-2}(-1) = \frac{\lambda}{(\lambda-t)^2}$.
    $E[X] = M_X'(0) = \frac{\lambda}{(\lambda-0)^2} = \frac{1}{\lambda}$.

*   **Step 3: Find the Variance.**
    $M_X''(t) = \frac{d}{dt}(\lambda(\lambda-t)^{-2}) = \lambda(-2)(\lambda-t)^{-3}(-1) = \frac{2\lambda}{(\lambda-t)^3}$.
    $E[X^2] = M_X''(0) = \frac{2\lambda}{(\lambda-0)^3} = \frac{2}{\lambda^2}$.
    $V(X) = E[X^2] - (E[X])^2 = \frac{2}{\lambda^2} - (\frac{1}{\lambda})^2 = \frac{1}{\lambda^2}$.


---

## MGF for Standard Distributions


---

## Poisson Distribution

*   **Concept:** For a discrete distribution, the MGF is a sum. We use the known Taylor series expansion for $e^x$ to simplify the resulting sum.
*   **Derivation:**
    $M_X(t) = E[e^{tX}] = \sum_{k=0}^{\infty} e^{tk} \frac{e^{-\lambda}\lambda^k}{k!} = e^{-\lambda} \sum_{k=0}^{\infty} \frac{(e^t\lambda)^k}{k!}$.
    The sum is the Taylor series for $e^z$ with $z = \lambda e^t$. So, $\sum_{k=0}^{\infty} \frac{(\lambda e^t)^k}{k!} = e^{\lambda e^t}$.
    $M_X(t) = e^{-\lambda} e^{\lambda e^t} = e^{\lambda(e^t - 1)}$.


---

## Binomial Distribution

*   **Concept:** The MGF is a sum which can be simplified using the Binomial Theorem: $(a+b)^n = \sum_{k=0}^{n} \binom{n}{k} a^k b^{n-k}$.
*   **Derivation:**
    $M_X(t) = E[e^{tX}] = \sum_{k=0}^{n} e^{tk} \binom{n}{k} p^k q^{n-k} = \sum_{k=0}^{n} \binom{n}{k} (pe^t)^k q^{n-k}$.
    This matches the form of the binomial expansion with $a = pe^t$ and $b = q$.
    $M_X(t) = (pe^t + q)^n$.


---

### Question 27: MGF of Discrete Geometric-type RV

> If X is a RV taking values $0, 1, 2, \dots$ with PMF $f(x) = ab^x$, where a and b are positive numbers such that $a+b=1$. Find the MGF of X.
>
> **Answer**
>
> *   **Concept:** This describes a geometric distribution starting from 0. The MGF is a sum which can be simplified using the formula for the sum of an infinite geometric series, $S = \frac{a_1}{1-r}$, where $a_1$ is the first term and $r$ is the common ratio.
>
> *   **Step 1: Set up the summation for the MGF.**
> $M_X(t) = E[e^{tX}] = \sum_{x=0}^{\infty} e^{tx} (ab^x) = a \sum_{x=0}^{\infty} (be^t)^x$.
>
> *   **Step 2: Apply the geometric series formula.**
> This is a geometric series with first term 1 and common ratio $r = be^t$. For the sum to converge, we need $|be^t| < 1$.
> $M_X(t) = a \left( \frac{1}{1 - be^t} \right) = \frac{a}{1 - be^t}$.
>
> *   **Step 3: (As in notes) Find the mean.**
> $M_X'(t) = a(-1)(1-be^t)^{-2}(-be^t) = \frac{abe^t}{(1-be^t)^2}$.
> $E[X] = M_X'(0) = \frac{ab}{(1-b)^2}$.
> Since $a+b=1$, we have $a=1-b$. Substituting this in:
> $E[X] = \frac{(1-b)b}{(1-b)^2} = \frac{b}{1-b} = \frac{b}{a}$.

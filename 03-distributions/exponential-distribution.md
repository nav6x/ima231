# Exponential Distribution

[← Back to Course README](../README.md)

- [Definition and Properties](#definition-and-properties)
- [Probability Density Function (PDF)](#probability-density-function-pdf)
- [Cumulative Distribution Function (CDF)](#cumulative-distribution-function-cdf)
- [Derivation of the Mean $E[X]$](#derivation-of-the-mean-ex)
- [Derivation of the Variance $Var(X)$](#derivation-of-the-variance-varx)
- [Memoryless Property](#memoryless-property)
  - [Question 56: Customer Arrival Rate](#question-56-customer-arrival-rate)
  - [Question 57: Electronic Component Lifetime](#question-57-electronic-component-lifetime)
  - [Question 58: Memoryless Property of Exponential](#question-58-memoryless-property-of-exponential)
  - [Question 59: Earthquake Time Expectation](#question-59-earthquake-time-expectation)

> **Topic**: Exponential Distribution: Definition and Properties, Probability Density Function (PDF), Cumulative Distribution Function (CDF), Derivation of the Mean $E[X]$

---

## Definition and Properties

The Exponential distribution is a continuous probability distribution that models the time between events in a Poisson process. It is the continuous counterpart of the geometric distribution and has the memoryless property.


---

## Probability Density Function (PDF)

For an Exponential distribution with rate parameter $\lambda > 0$, the PDF is given by:
$$f(x; \lambda) = \lambda e^{-\lambda x}$$
where $x \geq 0$ and $\lambda > 0$. Sometimes the distribution is parameterized using the mean $\mu = 1/\lambda$, in which case:
$$f(x; \mu) = \frac{1}{\mu} e^{-x/\mu}$$


---

## Cumulative Distribution Function (CDF)

The CDF of an Exponential distribution is:
$$F(x; \lambda) = 1 - e^{-\lambda x}$$
for $x \geq 0$.


---

## Derivation of the Mean $E[X]$

*   **Step 1: Set up the integral for $E[X]$**
    $E[X] = \int_{0}^{\infty} x \cdot \lambda e^{-\lambda x} dx$
    $E[X] = \lambda \int_{0}^{\infty} x e^{-\lambda x} dx$

*   **Step 2: Use integration by parts: $\int u \, dv = uv - \int v \, du$**
    Let $u = x$, so $du = dx$
    Let $dv = e^{-\lambda x} dx$, so $v = -\frac{1}{\lambda} e^{-\lambda x}$
    $\int x e^{-\lambda x} dx = -\frac{x}{\lambda} e^{-\lambda x} - \int \left(-\frac{1}{\lambda} e^{-\lambda x}\right) dx$
    $\int x e^{-\lambda x} dx = -\frac{x}{\lambda} e^{-\lambda x} + \frac{1}{\lambda} \int e^{-\lambda x} dx$
    $\int x e^{-\lambda x} dx = -\frac{x}{\lambda} e^{-\lambda x} + \frac{1}{\lambda} \cdot \left(-\frac{1}{\lambda} e^{-\lambda x}\right)$
    $\int x e^{-\lambda x} dx = -\frac{x}{\lambda} e^{-\lambda x} - \frac{1}{\lambda^2} e^{-\lambda x}$
    $\int x e^{-\lambda x} dx = -\frac{e^{-\lambda x}}{\lambda^2} (\lambda x + 1)$

*   **Step 3: Evaluate the definite integral**
    $\int_{0}^{\infty} x e^{-\lambda x} dx = \left[ -\frac{e^{-\lambda x}}{\lambda^2} (\lambda x + 1) \right]_{0}^{\infty}$
    As $x \to \infty$, $e^{-\lambda x} \to 0$ faster than any polynomial, so the upper limit is 0.
    At $x = 0$: $-\frac{e^{0}}{\lambda^2} (0 + 1) = -\frac{1}{\lambda^2}$
    $\int_{0}^{\infty} x e^{-\lambda x} dx = 0 - \left(-\frac{1}{\lambda^2}\right) = \frac{1}{\lambda^2}$

*   **Step 4: Calculate $E[X]$**
    $E[X] = \lambda \cdot \frac{1}{\lambda^2} = \frac{1}{\lambda}$


---

## Derivation of the Variance $Var(X)$

The variance is defined as $Var(X) = E[X^2] - (E[X])^2$. We know $E[X] = 1/\lambda$, so we need to find $E[X^2]$.

*   **Step 1: Set up the integral for $E[X^2]$**
    $E[X^2] = \int_{0}^{\infty} x^2 \cdot \lambda e^{-\lambda x} dx$
    $E[X^2] = \lambda \int_{0}^{\infty} x^2 e^{-\lambda x} dx$

*   **Step 2: Use integration by parts twice**
    Let $u = x^2$, so $du = 2x \, dx$
    Let $dv = e^{-\lambda x} dx$, so $v = -\frac{1}{\lambda} e^{-\lambda x}$
    $\int x^2 e^{-\lambda x} dx = -\frac{x^2}{\lambda} e^{-\lambda x} - \int \left(-\frac{1}{\lambda} e^{-\lambda x}\right) \cdot 2x \, dx$
    $\int x^2 e^{-\lambda x} dx = -\frac{x^2}{\lambda} e^{-\lambda x} + \frac{2}{\lambda} \int x e^{-\lambda x} dx$
    We already know $\int x e^{-\lambda x} dx = -\frac{e^{-\lambda x}}{\lambda^2} (\lambda x + 1)$
    $\int x^2 e^{-\lambda x} dx = -\frac{x^2}{\lambda} e^{-\lambda x} + \frac{2}{\lambda} \cdot \left(-\frac{e^{-\lambda x}}{\lambda^2} (\lambda x + 1)\right)$
    $\int x^2 e^{-\lambda x} dx = -\frac{x^2}{\lambda} e^{-\lambda x} - \frac{2}{\lambda^3} e^{-\lambda x} (\lambda x + 1)$
    $\int x^2 e^{-\lambda x} dx = -\frac{e^{-\lambda x}}{\lambda^3} (\lambda^2 x^2 + 2\lambda x + 2)$

*   **Step 3: Evaluate the definite integral**
    $\int_{0}^{\infty} x^2 e^{-\lambda x} dx = \left[ -\frac{e^{-\lambda x}}{\lambda^3} (\lambda^2 x^2 + 2\lambda x + 2) \right]_{0}^{\infty}$
    As $x \to \infty$, the exponential term dominates, so the upper limit is 0.
    At $x = 0$: $-\frac{e^{0}}{\lambda^3} (0 + 0 + 2) = -\frac{2}{\lambda^3}$
    $\int_{0}^{\infty} x^2 e^{-\lambda x} dx = 0 - \left(-\frac{2}{\lambda^3}\right) = \frac{2}{\lambda^3}$

*   **Step 4: Calculate $E[X^2]$**
    $E[X^2] = \lambda \cdot \frac{2}{\lambda^3} = \frac{2}{\lambda^2}$

*   **Step 5: Calculate $Var(X)$**
    $Var(X) = E[X^2] - (E[X])^2 = \frac{2}{\lambda^2} - \left(\frac{1}{\lambda}\right)^2$
    $Var(X) = \frac{2}{\lambda^2} - \frac{1}{\lambda^2} = \frac{1}{\lambda^2}$


---

## Memoryless Property

The Exponential distribution has the memoryless property:
$P(X > s + t | X > s) = P(X > t)$


---

### Question 56: Customer Arrival Rate

> **Question:** The time between arrivals of customers at a store follows an exponential distribution with a rate parameter of $\lambda = 0.2$ customers per minute. What is the expected time between customer arrivals and the variance of this time?
>
> **Answer:**
> For an Exponential distribution with rate parameter $\lambda = 0.2$:
> * Mean: $E[X] = \frac{1}{\lambda} = \frac{1}{0.2} = 5$ minutes
> * Variance: $Var(X) = \frac{1}{\lambda^2} = \frac{1}{(0.2)^2} = \frac{1}{0.04} = 25$ minutes^2
>
>
> ---


### Question 57: Electronic Component Lifetime

> **Question:** The lifetime of a certain electronic component follows an exponential distribution with mean 1000 hours. What is the probability that the component will last more than 1500 hours?
>
> **Answer:**
> *   **Step 1:** Find the rate parameter $\lambda$ from the mean.
> Since $E[X] = \frac{1}{\lambda} = 1000$, we have $\lambda = \frac{1}{1000} = 0.001$ per hour
> *   **Step 2:** Use the complement of the CDF to find $P(X > 1500)$.
> $P(X > 1500) = 1 - F(1500) = 1 - (1 - e^{-\lambda \cdot 1500}) = e^{-\lambda \cdot 1500}$
> *   **Step 3:** Calculate the probability.
> $P(X > 1500) = e^{-0.001 \cdot 1500} = e^{-1.5} \approx 0.2231$
>
>
> ---


### Question 58: Memoryless Property of Exponential

> **Question:** Using the memoryless property, if the same component in Question 2 has already been working for 500 hours, what is the probability that it will last an additional 1000 hours?
>
> **Answer:**
> *   **Step 1:** Apply the memoryless property of the exponential distribution.
> $P(X > 500 + 1000 | X > 500) = P(X > 1000)$
> *   **Step 2:** Calculate $P(X > 1000)$ using the same rate parameter $\lambda = 0.001$.
> $P(X > 1000) = e^{-\lambda \cdot 1000} = e^{-0.001 \cdot 1000} = e^{-1} \approx 0.3679$
>
>
> ---


### Question 59: Earthquake Time Expectation

> **Question:** The time until an earthquake occurs in a region follows an exponential distribution with mean 10 years. What is the probability that an earthquake will occur within the next 3 years?
>
> **Answer:**
> *   **Step 1:** Find the rate parameter from the mean.
> Since $E[X] = \frac{1}{\lambda} = 10$, we have $\lambda = \frac{1}{10} = 0.1$ per year
> *   **Step 2:** Calculate $P(X \leq 3)$ using the CDF.
> $P(X \leq 3) = F(3) = 1 - e^{-\lambda \cdot 3} = 1 - e^{-0.1 \cdot 3} = 1 - e^{-0.3}$
> *   **Step 3:** Compute the final value.
> $P(X \leq 3) = 1 - e^{-0.3} \approx 1 - 0.7408 = 0.2592$

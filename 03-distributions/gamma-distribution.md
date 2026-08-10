# Gamma Distribution

[← Back to Course README](../README.md)

- [Definition and Properties](#definition-and-properties)
- [Probability Density Function (PDF)](#probability-density-function-pdf)
- [Derivation of the Mean $E[X]$](#derivation-of-the-mean-ex)
- [Derivation of the Variance $Var(X)$](#derivation-of-the-variance-varx)
  - [Question 60: Gamma Distribution Parameters](#question-60-gamma-distribution-parameters)
  - [Question 61: Component Failure Time](#question-61-component-failure-time)
  - [Question 62: Exponential as Special Case of Gamma](#question-62-exponential-as-special-case-of-gamma)
  - [Question 63: Incomplete Gamma Function Probability](#question-63-incomplete-gamma-function-probability)

> **Topic**: Gamma Distribution: Definition and Properties, Probability Density Function (PDF), Derivation of the Mean $E[X]$, Derivation of the Variance $Var(X)$

---

## Definition and Properties

The Gamma distribution is a two-parameter family of continuous probability distributions. It is widely used in statistics, engineering, and science to model waiting times and other right-skewed data.


---

## Probability Density Function (PDF)

For a Gamma distribution with shape parameter $k > 0$ (sometimes denoted as $\alpha$) and rate parameter $\theta > 0$ (or scale parameter $\beta > 0$), the PDF is given by:
$$f(x; k, \theta) = \frac{\theta^k}{\Gamma(k)} x^{k-1} e^{-\theta x}$$
where $x > 0$, $k > 0$, $\theta > 0$, and $\Gamma(\cdot)$ is the Gamma function.

Alternatively, with shape parameter $k$ and scale parameter $\beta$:
$$f(x; k, \beta) = \frac{1}{\Gamma(k)\beta^k} x^{k-1} e^{-x/\beta}$$


---

## Derivation of the Mean $E[X]$

Using the rate parameterization $f(x; k, \theta) = \frac{\theta^k}{\Gamma(k)} x^{k-1} e^{-\theta x}$:

*   **Step 1: Set up the integral for $E[X]$**
    $E[X] = \int_{0}^{\infty} x \cdot \frac{\theta^k}{\Gamma(k)} x^{k-1} e^{-\theta x} dx$
    $E[X] = \frac{\theta^k}{\Gamma(k)} \int_{0}^{\infty} x^k e^{-\theta x} dx$

*   **Step 2: Use substitution $u = \theta x$, so $x = u/\theta$ and $dx = du/\theta$**
    When $x = 0$, $u = 0$. When $x = \infty$, $u = \infty$.
    $E[X] = \frac{\theta^k}{\Gamma(k)} \int_{0}^{\infty} \left(\frac{u}{\theta}\right)^k e^{-u} \cdot \frac{du}{\theta}$
    $E[X] = \frac{\theta^k}{\Gamma(k)} \int_{0}^{\infty} \frac{u^k}{\theta^k} e^{-u} \cdot \frac{du}{\theta}$
    $E[X] = \frac{\theta^k}{\Gamma(k)} \cdot \frac{1}{\theta^{k+1}} \int_{0}^{\infty} u^k e^{-u} du$
    $E[X] = \frac{1}{\theta\Gamma(k)} \int_{0}^{\infty} u^k e^{-u} du$

*   **Step 3: Recognize the Gamma function**
    $\int_{0}^{\infty} u^{a-1} e^{-u} du = \Gamma(a)$
    So, $\int_{0}^{\infty} u^k e^{-u} du = \Gamma(k+1) = k\Gamma(k)$

*   **Step 4: Final result for $E[X]$**
    $E[X] = \frac{1}{\theta\Gamma(k)} \cdot k\Gamma(k) = \frac{k}{\theta}$


---

## Derivation of the Variance $Var(X)$

The variance is defined as $Var(X) = E[X^2] - (E[X])^2$. We know $E[X] = k/\theta$, so we need to find $E[X^2]$.

*   **Step 1: Set up the integral for $E[X^2]$**
    $E[X^2] = \int_{0}^{\infty} x^2 \cdot \frac{\theta^k}{\Gamma(k)} x^{k-1} e^{-\theta x} dx$
    $E[X^2] = \frac{\theta^k}{\Gamma(k)} \int_{0}^{\infty} x^{k+1} e^{-\theta x} dx$

*   **Step 2: Use substitution $u = \theta x$, so $x = u/\theta$ and $dx = du/\theta$**
    $E[X^2] = \frac{\theta^k}{\Gamma(k)} \int_{0}^{\infty} \left(\frac{u}{\theta}\right)^{k+1} e^{-u} \cdot \frac{du}{\theta}$
    $E[X^2] = \frac{\theta^k}{\Gamma(k)} \cdot \frac{1}{\theta^{k+2}} \int_{0}^{\infty} u^{k+1} e^{-u} du$
    $E[X^2] = \frac{1}{\theta^2\Gamma(k)} \int_{0}^{\infty} u^{k+1} e^{-u} du$

*   **Step 3: Recognize the Gamma function**
    $\int_{0}^{\infty} u^{k+1} e^{-u} du = \Gamma(k+2) = (k+1)\Gamma(k+1) = (k+1)k\Gamma(k)$

*   **Step 4: Calculate $E[X^2]$**
    $E[X^2] = \frac{1}{\theta^2\Gamma(k)} \cdot k(k+1)\Gamma(k) = \frac{k(k+1)}{\theta^2}$

*   **Step 5: Calculate $Var(X)$**
    $Var(X) = E[X^2] - (E[X])^2 = \frac{k(k+1)}{\theta^2} - \left(\frac{k}{\theta}\right)^2$
    $Var(X) = \frac{k(k+1)}{\theta^2} - \frac{k^2}{\theta^2} = \frac{k(k+1) - k^2}{\theta^2} = \frac{k}{\theta^2}$


---

### Question 60: Gamma Distribution Parameters

> **Question:** If $X$ follows a Gamma distribution with shape parameter $k = 4$ and rate parameter $\theta = 2$, find the mean and variance of $X$.
>
> **Answer:**
> *   **Step 1:** For a Gamma distribution with shape parameter $k$ and rate parameter $\theta$:
> * Mean: $E[X] = \frac{k}{\theta}$
> * Variance: $Var(X) = \frac{k}{\theta^2}$
> *   **Step 2:** Substitute $k = 4$ and $\theta = 2$:
> * Mean: $E[X] = \frac{4}{2} = 2$
> * Variance: $Var(X) = \frac{4}{2^2} = \frac{4}{4} = 1$
>
>
> ---


### Question 61: Component Failure Time

> **Question:** A system has components that fail according to a Gamma distribution with shape parameter $k = 3$ and scale parameter $\beta = 2$. What is the expected time until failure and the variance of the failure time?
>
> **Answer:**
> Using the scale parameterization $f(x; k, \beta) = \frac{1}{\Gamma(k)\beta^k} x^{k-1} e^{-x/\beta}$:
> * Mean: $E[X] = k\beta = 3 \times 2 = 6$
> * Variance: $Var(X) = k\beta^2 = 3 \times 2^2 = 3 \times 4 = 12$
>
>
> ---


### Question 62: Exponential as Special Case of Gamma

> **Question:** Show that the exponential distribution is a special case of the Gamma distribution.
>
> **Answer:**
> *   **Step 1:** The PDF of an exponential distribution with rate parameter $\lambda$ is:
> $f(x; \lambda) = \lambda e^{-\lambda x}$ for $x \geq 0$
> *   **Step 2:** The PDF of a Gamma distribution with shape parameter $k$ and rate parameter $\theta$ is:
> $f(x; k, \theta) = \frac{\theta^k}{\Gamma(k)} x^{k-1} e^{-\theta x}$
> *   **Step 3:** For $k = 1$ and $\theta = \lambda$:
> $f(x; 1, \lambda) = \frac{\lambda^1}{\Gamma(1)} x^{1-1} e^{-\lambda x} = \frac{\lambda}{1} x^{0} e^{-\lambda x} = \lambda e^{-\lambda x}$
> *   **Step 4:** This is exactly the PDF of the exponential distribution.
> *   **Step 5:** Therefore, the exponential distribution is a special case of the Gamma distribution with shape parameter $k = 1$.
>
>
> ---


### Question 63: Incomplete Gamma Function Probability

> **Question:** If $X$ follows a Gamma distribution with parameters $k = 5$ and $\theta = 3$, find $P(X < 6)$ in terms of the incomplete Gamma function.
>
> **Answer:**
> *   **Step 1:** The CDF of a Gamma distribution is expressed using the regularized incomplete Gamma function.
> *   **Step 2:** For $X \sim \text{Gamma}(k, \theta)$, the CDF is:
> $P(X < x) = \frac{\gamma(k, \theta x)}{\Gamma(k)}$
> where $\gamma(k, \theta x)$ is the lower incomplete Gamma function.
> *   **Step 3:** With $k = 5$, $\theta = 3$, and $x = 6$:
> $P(X < 6) = \frac{\gamma(5, 3 \times 6)}{\Gamma(5)} = \frac{\gamma(5, 18)}{\Gamma(5)} = \frac{\gamma(5, 18)}{4!} = \frac{\gamma(5, 18)}{24}$

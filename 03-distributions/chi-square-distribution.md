# Chi-Square Distribution

[← Back to Course README](../README.md)

- [Definition and Properties](#definition-and-properties)
- [Probability Density Function (PDF)](#probability-density-function-pdf)
- [Derivation of the Mean $E[X]$](#derivation-of-the-mean-ex)
- [Derivation of the Variance $Var(X)$](#derivation-of-the-variance-varx)
  - [Question 53: Chi-Square Mean and Variance](#question-53-chi-square-mean-and-variance)
  - [Question 54: Sum of Independent Standard Normal Variables](#question-54-sum-of-independent-standard-normal-variables)
  - [Question 55: Sample Variance Distribution](#question-55-sample-variance-distribution)

> **Topic**: Chi-Square Distribution: Definition and Properties, Probability Density Function (PDF), Derivation of the Mean $E[X]$, Derivation of the Variance $Var(X)$

---

## Definition and Properties

The Chi-Square distribution is a special case of the Gamma distribution. It arises from the sum of squares of independent standard normal random variables.


---

## Probability Density Function (PDF)

For a Chi-Square distribution with $k$ degrees of freedom, the PDF is given by:
$$f(x; k) = \frac{1}{2^{k/2}\Gamma(k/2)} x^{k/2-1} e^{-x/2}$$
where $x > 0$, $k > 0$, and $\Gamma(\cdot)$ is the Gamma function.


---

## Derivation of the Mean $E[X]$

For a Chi-Square distribution with $k$ degrees of freedom:

*   **Step 1: Set up the integral for $E[X]$**
    $E[X] = \int_{0}^{\infty} x \cdot \frac{1}{2^{k/2}\Gamma(k/2)} x^{k/2-1} e^{-x/2} dx$

*   **Step 2: Simplify the integrand**
    $E[X] = \frac{1}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} x^{k/2} e^{-x/2} dx$

*   **Step 3: Use substitution $u = x/2$, so $x = 2u$ and $dx = 2du$**
    When $x = 0$, $u = 0$. When $x = \infty$, $u = \infty$.
    $E[X] = \frac{1}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} (2u)^{k/2} e^{-u} \cdot 2du$
    $E[X] = \frac{1}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} 2^{k/2+1} u^{k/2} e^{-u} du$
    $E[X] = \frac{2^{k/2+1}}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} u^{k/2} e^{-u} du$
    $E[X] = \frac{2}{\Gamma(k/2)} \int_{0}^{\infty} u^{k/2} e^{-u} du$

*   **Step 4: Recognize the Gamma function**
    $\int_{0}^{\infty} u^{a-1} e^{-u} du = \Gamma(a)$
    So, $\int_{0}^{\infty} u^{k/2} e^{-u} du = \Gamma(k/2 + 1) = \frac{k}{2}\Gamma(k/2)$

*   **Step 5: Final result for $E[X]$**
    $E[X] = \frac{2}{\Gamma(k/2)} \cdot \frac{k}{2}\Gamma(k/2) = k$


---

## Derivation of the Variance $Var(X)$

The variance is defined as $Var(X) = E[X^2] - (E[X])^2$. We know $E[X] = k$, so we need to find $E[X^2]$.

*   **Step 1: Set up the integral for $E[X^2]$**
    $E[X^2] = \int_{0}^{\infty} x^2 \cdot \frac{1}{2^{k/2}\Gamma(k/2)} x^{k/2-1} e^{-x/2} dx$
    $E[X^2] = \frac{1}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} x^{k/2+1} e^{-x/2} dx$

*   **Step 2: Use substitution $u = x/2$, so $x = 2u$ and $dx = 2du$**
    $E[X^2] = \frac{1}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} (2u)^{k/2+1} e^{-u} \cdot 2du$
    $E[X^2] = \frac{2^{k/2+2}}{2^{k/2}\Gamma(k/2)} \int_{0}^{\infty} u^{k/2+1} e^{-u} du$
    $E[X^2] = \frac{4}{\Gamma(k/2)} \int_{0}^{\infty} u^{k/2+1} e^{-u} du$

*   **Step 3: Recognize the Gamma function**
    $\int_{0}^{\infty} u^{k/2+1} e^{-u} du = \Gamma(k/2 + 2) = (k/2 + 1)\Gamma(k/2 + 1) = (k/2 + 1)(k/2)\Gamma(k/2)$

*   **Step 4: Calculate $E[X^2]$**
    $E[X^2] = \frac{4}{\Gamma(k/2)} \cdot \frac{k}{2} \cdot \frac{k+2}{2} \Gamma(k/2) = k(k+2)$

*   **Step 5: Calculate $Var(X)$**
    $Var(X) = E[X^2] - (E[X])^2 = k(k+2) - k^2 = k^2 + 2k - k^2 = 2k$


---

### Question 53: Chi-Square Mean and Variance

> **Question:** If $X$ follows a Chi-Square distribution with 10 degrees of freedom, find the mean and variance of $X$.
>
> **Answer:**
> For a Chi-Square distribution with $k$ degrees of freedom:
> * Mean: $E[X] = k = 10$
> * Variance: $Var(X) = 2k = 2 \times 10 = 20$
>
>
> ---


### Question 54: Sum of Independent Standard Normal Variables

> **Question:** If $X_1, X_2, \ldots, X_n$ are independent standard normal random variables, what is the distribution of $Y = X_1^2 + X_2^2 + \cdots + X_n^2$? Find $E[Y]$ and $Var(Y)$.
>
> **Answer:**
> *   **Step 1:** Since each $X_i$ follows a standard normal distribution $N(0,1)$, the sum of their squares follows a Chi-Square distribution.
> *   **Step 2:** $Y = X_1^2 + X_2^2 + \cdots + X_n^2$ follows a Chi-Square distribution with $n$ degrees of freedom.
> *   **Step 3:** For $Y \sim \chi^2(n)$:
> * Mean: $E[Y] = n$
> * Variance: $Var(Y) = 2n$
>
>
> ---


### Question 55: Sample Variance Distribution

> **Question:** A random sample of size 25 is drawn from a normal population. The sample variance is found to be $s^2 = 16$. Find the mean and variance of $(n-1)s^2/\sigma^2$ where $\sigma^2$ is the population variance.
>
> **Answer:**
> *   **Step 1:** For a normal population with sample size $n$ and sample variance $s^2$, the quantity $(n-1)s^2/\sigma^2$ follows a Chi-Square distribution with $(n-1)$ degrees of freedom.
> *   **Step 2:** Here, $n = 25$, so $(n-1)s^2/\sigma^2 \sim \chi^2(24)$.
> *   **Step 3:** Mean: $E[(n-1)s^2/\sigma^2] = 24$
> *   **Step 4:** Variance: $Var((n-1)s^2/\sigma^2) = 2 \times 24 = 48$

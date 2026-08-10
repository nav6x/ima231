# Normal Distribution

[← Back to Course README](../README.md)

- [Overview](#overview)
- [Probability Density Function (PDF)](#probability-density-function-pdf)
- [Proof of Validity](#proof-of-validity)
- [Properties and Applications](#properties-and-applications)
- [Derivation of Mean and Variance](#derivation-of-mean-and-variance)
- [Derivation of the Mean $E[X]$](#derivation-of-the-mean-ex)
- [Derivation of the Variance $Var(X)$](#derivation-of-the-variance-varx)
- [Solved Problems](#solved-problems)
  - [Question 48: Standard Normal Probability Calculation](#question-48-standard-normal-probability-calculation)
  - [Question 49: Electric Devices Reliability](#question-49-electric-devices-reliability)
  - [Question 50: Electric Cable Diameter](#question-50-electric-cable-diameter)
  - [Question 51: Soldier Heights Standard Deviation](#question-51-soldier-heights-standard-deviation)
  - [Question 52: Normal Distribution Mean and Standard Deviation](#question-52-normal-distribution-mean-and-standard-deviation)

> **Topic**: Normal Distribution: Overview, Probability Density Function (PDF), Proof of Validity, Properties and Applications

---

## Overview

*   The Normal Distribution is a continuous probability distribution characterized by its bell-shaped curve, also known as the Gaussian distribution.
*   It is considered the most important distribution in statistics because it models many natural phenomena and is fundamental to many statistical methods.
*   The curve is symmetric around its mean, and the mean, median, and mode are all equal.
*   Key points on the curve include the **Point of Inflection**, where the curvature changes.


---

## Probability Density Function (PDF)

The PDF for a normal distribution is given by:
$f(x; \mu, \sigma) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2} \left(\frac{x - \mu}{\sigma}\right)^2}$
where:
*   $\mu$ (mu) is the mean of the distribution, representing the center of the bell curve.
*   $\sigma$ (sigma) is the standard deviation, representing the spread or width of the distribution. A smaller $\sigma$ results in a narrower, taller peak, while a larger $\sigma$ results in a wider, flatter curve.
*   $e$ is the base of the natural logarithm (approximately 2.71828).
*   $\pi$ (pi) is the mathematical constant (approximately 3.14159).


---

## Proof of Validity

To be a valid PDF, the integral of the function over its entire domain must equal 1.
We need to prove: $\int_{-\infty}^{\infty} \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2} \left(\frac{x - \mu}{\sigma}\right)^2} dx = 1$

1.  **Substitution:**
    Let $z = \frac{x-\mu}{\sigma}$. Then $dz = \frac{dx}{\sigma}$, so $dx = \sigma dz$.
    The integral becomes:
    $\int_{-\infty}^{\infty} \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2} z^2} (\sigma dz)$
    $= \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} e^{-\frac{1}{2} z^2} dz$

2.  **Using the Gaussian Integral:**
    The integral $\int_{-\infty}^{\infty} e^{-ax^2} dx = \sqrt{\frac{\pi}{a}}$ is a known result called the Gaussian integral.
    In our case, $a = \frac{1}{2}$.
    So, $\int_{-\infty}^{\infty} e^{-\frac{1}{2} z^2} dz = \sqrt{\frac{\pi}{1/2}} = \sqrt{2\pi}$.

3.  **Final Calculation:**
    $\frac{1}{\sqrt{2\pi}} \cdot \sqrt{2\pi} = 1$
    Hence, the Normal Distribution is a valid PDF.


---

## Properties and Applications

*   **Symmetry:** The curve is symmetric about the mean $\mu$. The area under the curve to the left of $\mu$ is 0.5, and the area to the right is 0.5.
*   **Empirical Rule (68-95-99.7 Rule):**
    *   Approximately 68% of the data falls within one standard deviation of the mean ($(\mu - \sigma, \mu + \sigma)$).
    *   Approximately 95% of the data falls within two standard deviations of the mean ($(\mu - 2\sigma, \mu + 2\sigma)$).
    *   Approximately 99.7% of the data falls within three standard deviations of the mean ($(\mu - 3\sigma, \mu + 3\sigma)$).
*   **Standard Normal Distribution:** A special case where $\mu = 0$ and $\sigma = 1$. The PDF is $f(z) = \frac{1}{\sqrt{2\pi}} e^{-z^2/2}$. Any normal distribution can be converted to a standard normal distribution using the z-score formula: $z = \frac{x - \mu}{\sigma}$.


---

## Derivation of Mean and Variance

For a Normal Distribution, the probability density function (PDF) is given by:
$f(x; \mu, \sigma) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2} \left(\frac{x - \mu}{\sigma}\right)^2}$
where $\mu$ is the mean and $\sigma$ is the standard deviation.


---

## Derivation of the Mean $E[X]$

The mean (expected value) of a continuous random variable is defined as $E[Z] = \int_{-\infty}^{\infty} z \cdot f(z) dz$.
$E[Z] = \int_{-\infty}^{\infty} z \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} dz$

*   **Step 2: Evaluate the integral**
    Let $u = -\frac{1}{2} z^2$. Then $du = -z dz$.
    When $z \to -\infty$, $u \to -\infty$. When $z \to \infty$, $u \to -\infty$.
    The integral becomes:
    $E[Z] = \frac{1}{\sqrt{2\pi}} \int_{\infty}^{-\infty} e^u (-du) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} e^u du$
    However, a simpler way to evaluate this integral is to recognize that the integrand $g(z) = z e^{-\frac{1}{2} z^2}$ is an **odd function**.
    An odd function satisfies $g(-z) = -g(z)$.
    $g(-z) = (-z) e^{-\frac{1}{2} (-z)^2} = -z e^{-\frac{1}{2} z^2} = -g(z)$
    The integral of an odd function over a symmetric interval $[-\infty, \infty]$ is always zero.
    Therefore, $E[Z] = 0$.

*   **Step 3: Generalize to $E[X]$ for a Normal Distribution**
    Any normal random variable $X$ can be expressed as a linear transformation of a standard normal random variable $Z$:
    $X = \sigma Z + \mu$
    Using the property of expectation $E[aZ + b] = aE[Z] + b$:
    $E[X] = E[\sigma Z + \mu] = \sigma E[Z] + \mu$
    Since $E[Z] = 0$:
    $E[X] = \sigma (0) + \mu = \mu$
    Thus, the mean of a Normal Distribution is $\mu$.


---

## Derivation of the Variance $Var(X)$

We will first derive the variance for the **Standard Normal Distribution** ($Z$), where $E[Z]=0$.
The variance is defined as $Var(Z) = E[Z^2] - (E[Z])^2$. Since $E[Z]=0$, $Var(Z) = E[Z^2]$.

*   **Step 1: Set up the integral for $E[Z^2]$**
    $E[Z^2] = \int_{-\infty}^{\infty} z^2 \cdot f(z) dz = \int_{-\infty}^{\infty} z^2 \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} dz$
    $E[Z^2] = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} z^2 e^{-\frac{1}{2} z^2} dz$

*   **Step 2: Use Integration by Parts**
    Let $u = z$ and $dv = z e^{-\frac{1}{2} z^2} dz$.
    Then $du = dz$.
    To find $v$, integrate $dv$:
    $\int z e^{-\frac{1}{2} z^2} dz$. Let $w = -\frac{1}{2} z^2$, so $dw = -z dz$.
    $\int e^w (-dw) = -e^w = -e^{-\frac{1}{2} z^2}$. So, $v = -e^{-\frac{1}{2} z^2}$.

    Applying integration by parts formula $\int u dv = uv - \int v du$:
    $\int_{-\infty}^{\infty} z^2 e^{-\frac{1}{2} z^2} dz = \left[ z (-e^{-\frac{1}{2} z^2}) \right]_{-\infty}^{\infty} - \int_{-\infty}^{\infty} (-e^{-\frac{1}{2} z^2}) dz$

*   **Step 3: Evaluate the boundary term**
    The term $\left[ z (-e^{-\frac{1}{2} z^2}) \right]_{-\infty}^{\infty}$ evaluates to 0 at both limits because $e^{-\frac{1}{2} z^2}$ approaches 0 much faster than $z$ approaches $\infty$ (or $-\infty$).
    So, the expression simplifies to:
    $\int_{-\infty}^{\infty} z^2 e^{-\frac{1}{2} z^2} dz = \int_{-\infty}^{\infty} e^{-\frac{1}{2} z^2} dz$

*   **Step 4: Recognize the integral of the Gaussian function**
    We know that the integral of the standard normal PDF over its entire domain is 1:
    $\int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2} z^2} dz = 1$
    This implies $\int_{-\infty}^{\infty} e^{-\frac{1}{2} z^2} dz = \sqrt{2\pi}$.

*   **Step 5: Substitute back to find $E[Z^2]$**
    $E[Z^2] = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} e^{-\frac{1}{2} z^2} dz = \frac{1}{\sqrt{2\pi}} (\sqrt{2\pi}) = 1$
    Therefore, $Var(Z) = E[Z^2] = 1$.

*   **Step 6: Generalize to $Var(X)$ for a Normal Distribution**
    Using the property of variance $Var(aZ + b) = a^2 Var(Z)$:
    $X = \sigma Z + \mu$
    $Var(X) = Var(\sigma Z + \mu) = \sigma^2 Var(Z)$
    Since $Var(Z) = 1$:
    $Var(X) = \sigma^2 (1) = \sigma^2$
    Thus, the variance of a Normal Distribution is $\sigma^2$.


---

## Solved Problems


---

### Question 48: Standard Normal Probability Calculation

> **Question:** Suppose that $X \sim N(2, 0.16)$. Find:
> 1) $P[X \ge 2.3]$
> 2) $P[1.8 \le X \le 2.1]$
> 3) $P[X < 1.5]$
>
> **Answer:**
> Given $\mu = 2$ and $\sigma^2 = 0.16$, so $\sigma = \sqrt{0.16} = 0.4$.
> We use the standard normal transformation $Z = \frac{X - \mu}{\sigma}$.
>
> **1) $P[X \ge 2.3]$**
> *   $Z = \frac{2.3 - 2}{0.4} = \frac{0.3}{0.4} = 0.75$
> *   $P[X \ge 2.3] = P[Z \ge 0.75] = 1 - P[Z < 0.75]$
> *   Using a Z-table, $P[Z < 0.75] \approx 0.7734$.
> *   $P[X \ge 2.3] = 1 - 0.7734 = 0.2266$.
>
> **2) $P[1.8 \le X \le 2.1]$**
> *   For $X=1.8: Z = \frac{1.8 - 2}{0.4} = -0.5$
> *   For $X=2.1: Z = \frac{2.1 - 2}{0.4} = 0.25$
> *   $P[1.8 \le X \le 2.1] = P[-0.5 \le Z \le 0.25] = P[Z < 0.25] - P[Z < -0.5]$
> *   $P[Z < 0.25] \approx 0.5987$
> *   $P[Z < -0.5] = 1 - P[Z < 0.5] \approx 1 - 0.6915 = 0.3085$
> *   $P[1.8 \le X \le 2.1] = 0.5987 - 0.3085 = 0.2902$.
>
> **3) $P[X < 1.5]$**
> *   $Z = \frac{1.5 - 2}{0.4} = -1.25$
> *   $P[X < 1.5] = P[Z < -1.25] = 1 - P[Z < 1.25]$
> *   $P[Z < 1.25] \approx 0.8944$
> *   $P[X < 1.5] = 1 - 0.8944 = 0.1056$.
>
>
> ---


### Question 49: Electric Devices Reliability

> **Question:** Suppose that the life length of two electric devices D1 and D2 have distributions $N(40, 36)$ and $N(45, 9)$ respectively. If the device is to be used for a 45-hour period, which device is to be preferred? If it is to be used for a 48-hour period, which device is to be preferred?
>
> **Answer:**
> We want to find the device with the higher probability of lasting *at least* the specified period.
>
> **Device D1:** $\mu_1 = 40, \sigma_1^2 = 36 \implies \sigma_1 = 6$
> **Device D2:** $\mu_2 = 45, \sigma_2^2 = 9 \implies \sigma_2 = 3$
>
> **Case 1: 45-hour period**
> *   **P(D1 > 45):**
> *   $Z_1 = \frac{45 - 40}{6} = \frac{5}{6} \approx 0.833$
> *   $P(Z_1 > 0.833) = 1 - P(Z_1 \le 0.833) \approx 1 - 0.7967 = 0.2033$
> *   **P(D2 > 45):**
> *   $Z_2 = \frac{45 - 45}{3} = 0$
> *   $P(Z_2 > 0) = 0.5$
> *   **Conclusion:** For a 45-hour period, **Device D2 is preferred** as it has a higher probability of lasting.
>
> **Case 2: 48-hour period**
> *   **P(D1 > 48):**
> *   $Z_1 = \frac{48 - 40}{6} = \frac{8}{6} \approx 1.33$
> *   $P(Z_1 > 1.33) = 1 - P(Z_1 \le 1.33) \approx 1 - 0.9082 = 0.0918$
> *   **P(D2 > 48):**
> *   $Z_2 = \frac{48 - 45}{3} = 1$
> *   $P(Z_2 > 1) = 1 - P(Z_2 \le 1) \approx 1 - 0.8413 = 0.1587$
> *   **Conclusion:** For a 48-hour period, **Device D2 is preferred** as it has a higher probability of lasting.
>
>
> ---


### Question 50: Electric Cable Diameter

> **Question:** The diameter of an electric cable is normally distributed with mean $\mu=0.8$ and variance $\sigma^2=0.0004$.
> (a) What is the probability that the diameter will exceed 0.81 inches?
> (b) Suppose the cable is considered defective if the diameter differs from its mean by more than 0.025. What is the probability of obtaining a defective cable?
>
> **Answer:**
> Given $\mu = 0.8$ and $\sigma^2 = 0.0004$, so $\sigma = \sqrt{0.0004} = 0.02$.
>
> **(a) P(Diameter > 0.81)**
> *   $Z = \frac{0.81 - 0.8}{0.02} = \frac{0.01}{0.02} = 0.5$
> *   $P(X > 0.81) = P(Z > 0.5) = 1 - P(Z \le 0.5)$
> *   $P(Z \le 0.5) \approx 0.6915$
> *   $P(X > 0.81) = 1 - 0.6915 = 0.3085$.
>
> **(b) P(defective cable)**
> A cable is defective if $|X - \mu| > 0.025$.
> *   $|X - 0.8| > 0.025$
> *   Divide by $\sigma$: $\frac{|X - 0.8|}{0.02} > \frac{0.025}{0.02}$
> *   $|Z| > 1.25$
> *   This means $Z > 1.25$ or $Z < -1.25$. By symmetry, $P(Z > 1.25) = P(Z < -1.25)$.
> *   $P(\text{defective}) = 2 \times P(Z > 1.25) = 2 \times (1 - P(Z \le 1.25))$
> *   $P(Z \le 1.25) \approx 0.8944$
> *   $P(\text{defective}) = 2 \times (1 - 0.8944) = 2 \times 0.1056 = 0.2112$.
>
>
> ---


### Question 51: Soldier Heights Standard Deviation

> **Question:** The heights of 500 soldiers are found to have a normal distribution. 258 of them are found to be within 2cm of the mean height of 170cm. Find the standard deviation of X.
>
> **Answer:**
> Given $\mu = 170cm$.
> The condition "within 2cm of the mean" means $|X - 170| \le 2$, or $168 \le X \le 172$.
> The probability of this is $258/500 = 0.516$.
> $P(168 \le X \le 172) = 0.516$
> $P(-\frac{2}{\sigma} \le Z \le \frac{2}{\sigma}) = 0.516$
> $P(Z \le \frac{2}{\sigma}) - P(Z \le -\frac{2}{\sigma}) = 0.516$
> $P(Z \le \frac{2}{\sigma}) - (1 - P(Z \le \frac{2}{\sigma})) = 0.516$
> $2 \cdot P(Z \le \frac{2}{\sigma}) - 1 = 0.516$
> $2 \cdot P(Z \le \frac{2}{\sigma}) = 1.516$
> $P(Z \le \frac{2}{\sigma}) = 0.758$
> From the Z-table, a probability of 0.758 corresponds to a Z-score of approximately 0.7.
> $\frac{2}{\sigma} = 0.7 \implies \sigma = \frac{2}{0.7} \approx 2.857$
>
>
> ---


### Question 52: Normal Distribution Mean and Standard Deviation

> **Question:** In a normal distribution, 31% of items are under 45 and 8% are over 64. Find the mean & standard deviation of the distribution.
>
> **Answer:**
> Let X be the random variable. We are given:
> 1. $P(X < 45) = 0.31$
> 2. $P(X > 64) = 0.08$
>
> From these, we can find the corresponding Z-scores.
> 1. $P(Z < \frac{45-\mu}{\sigma}) = 0.31$. Since this is less than 0.5, the Z-score is negative. From the Z-table, $P(Z < -0.5) \approx 0.3085$. So, $\frac{45-\mu}{\sigma} = -0.5$.
> $45 - \mu = -0.5\sigma$ (Eq 1)
>
> 2. $P(Z > \frac{64-\mu}{\sigma}) = 0.08$. This means $P(Z \le \frac{64-\mu}{\sigma}) = 1 - 0.08 = 0.92$. From the Z-table, this corresponds to a Z-score of approx 1.4.
> $\frac{64-\mu}{\sigma} = 1.4$
> $64 - \mu = 1.4\sigma$ (Eq 2)
>
> Now we solve the system of two linear equations:
> Subtract Eq 1 from Eq 2:
> $(64 - \mu) - (45 - \mu) = 1.4\sigma - (-0.5\sigma)$
> $19 = 1.9\sigma$
> $\sigma = 19 / 1.9 = 10$
>
> Substitute $\sigma = 10$ into Eq 1:
> $45 - \mu = -0.5 \times 10$
> $45 - \mu = -5$
> $\mu = 50$
>
> So, the mean is **50** and the standard deviation is **10**.

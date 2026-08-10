# Poisson Distribution

[← Back to Course README](../README.md)

- [Overview](#overview)
- [Probability Mass Function (PMF)](#probability-mass-function-pmf)
- [Properties](#properties)
- [Proofs and Derivations](#proofs-and-derivations)
- [1. Proof of PMF Validity (Sum = 1)](#1-proof-of-pmf-validity-sum-1)
- [2. Derivation of the Mean (Expected Value)](#2-derivation-of-the-mean-expected-value)
- [3. Derivation of the Variance $Var(X)$](#3-derivation-of-the-variance-varx)
    - [Derivation of $E[X(X-1)]$](#derivation-of-exx-1)
    - [Calculating $Var(X)$](#calculating-varx)
- [Solved Problems](#solved-problems)
  - [Question 40: Accidental Drowning Rate](#question-40-accidental-drowning-rate)
  - [Question 41: Taxi Driver Accidents](#question-41-taxi-driver-accidents)
  - [Question 42: Insurance Policy Claims](#question-42-insurance-policy-claims)
  - [Question 43: Poisson Probability Relation](#question-43-poisson-probability-relation)
  - [Question 44: Even and Odd Poisson Probabilities](#question-44-even-and-odd-poisson-probabilities)

> **Topic**: Poisson Distribution: Overview, Probability Mass Function (PMF), Properties, Proofs and Derivations

---

## Overview

The Poisson Distribution is a discrete probability distribution that expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant mean rate and independently of the time since the last event.

*   **Relationship to Binomial Distribution:** It can be used as an approximation to the Binomial Distribution when the number of trials ($n$) is very large and the probability of success ($p$) is very small. In such cases, the mean $\lambda = np$ remains finite. A common rule of thumb is that the Poisson distribution is a good approximation of the binomial distribution if n is at least 20 and p is smaller than or equal to 0.05. In a binomial distribution, if n -> infinity and p -> 0, it tends to Poisson Distribution.


---

## Probability Mass Function (PMF)

The PMF for a Poisson Distribution is given by:
$P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$
where:
*   $X$ is the random variable representing the number of events.
*   $k$ is the number of occurrences (a non-negative integer: $k = 0, 1, 2, \dots$).
*   $\lambda$ (lambda) is the average rate of occurrence (mean) of the event in the given interval ($\lambda > 0$).
*   $e$ is the base of the natural logarithm (approximately 2.71828).
*   $k!$ is the factorial of $k$.


---

## Properties

*   **Mean (Expected Value):** $E[X] = \lambda$
*   **Variance:** $Var(X) = \lambda$


---

## Proofs and Derivations


---

## 1. Proof of PMF Validity (Sum = 1)

To be a valid PMF, the sum of all probabilities must equal 1.
$\sum_{k=0}^{\infty} P(X=k) = \sum_{k=0}^{\infty} \frac{e^{-\lambda} \lambda^k}{k!}$
Since $e^{-\lambda}$ is a constant with respect to k, we can factor it out:
$= e^{-\lambda} \sum_{k=0}^{\infty} \frac{\lambda^k}{k!}$
The summation part is the Taylor series expansion for $e^\lambda$:
$\sum_{k=0}^{\infty} \frac{\lambda^k}{k!} = 1 + \lambda + \frac{\lambda^2}{2!} + \frac{\lambda^3}{3!} + \dots = e^\lambda$
Substituting this back, we get:
$= e^{-\lambda} e^\lambda = 1$
Thus, the Poisson PMF is a valid probability distribution.


---

## 2. Derivation of the Mean (Expected Value)

The expected value $E[X]$ is calculated as $\sum_{k=0}^{\infty} k \cdot P(X=k)$.
$E[X] = \sum_{k=0}^{\infty} k \frac{e^{-\lambda} \lambda^k}{k!}$
The term for $k=0$ is 0, so we can start the sum from $k=1$.
$E[X] = \sum_{k=1}^{\infty} k \frac{e^{-\lambda} \lambda^k}{k!}$
We can simplify $\frac{k}{k!} = \frac{1}{(k-1)!}$.
$E[X] = \sum_{k=1}^{\infty} \frac{e^{-\lambda} \lambda^k}{(k-1)!}$
Factor out $e^{-\lambda}$ and one $\lambda$:
$E[X] = e^{-\lambda} \lambda \sum_{k=1}^{\infty} \frac{\lambda^{k-1}}{(k-1)!}$
Let $m = k-1$. When $k=1$, $m=0$. The sum becomes:
$E[X] = e^{-\lambda} \lambda \sum_{m=0}^{\infty} \frac{\lambda^{m}}{m!}$
The summation is again the Taylor series for $e^\lambda$.
$E[X] = e^{-\lambda} \lambda (e^\lambda) = \lambda$
Thus, the mean of the Poisson distribution is $\lambda$.


---

## 3. Derivation of the Variance $Var(X)$

The variance is defined as $Var(X) = E[X^2] - (E[X])^2$. We already know $E[X] = \lambda$. So, we need to find $E[X^2]$.
It's often easier to calculate $E[X(X-1)]$ first.

#### Derivation of $E[X(X-1)]$

*   **Step 1: Set up the summation for $E[X(X-1)]$
    $E[X(X-1)] = \sum_{k=0}^{\infty} k(k-1) P(X=k)$
    $E[X(X-1)] = \sum_{k=0}^{\infty} k(k-1) \frac{e^{-\lambda} \lambda^k}{k!}$

*   **Step 2: Handle the $k=0$ and $k=1$ terms
    The terms for $k=0$ and $k=1$ are $0 \cdot (-1) \cdot P(X=0) = 0$ and $1 \cdot (0) \cdot P(X=1) = 0$.
    So, we can start the summation from $k=2$.
    $E[X(X-1)] = \sum_{k=2}^{\infty} k(k-1) \frac{e^{-\lambda} \lambda^k}{k!}$

*   **Step 3: Simplify the term $k(k-1) \cdot \frac{1}{k!}$
    $k(k-1) \cdot \frac{1}{k!} = k(k-1) \cdot \frac{1}{k(k-1)(k-2)!} = \frac{1}{(k-2)!}$

*   **Step 4: Substitute the simplified term back into the summation
    $E[X(X-1)] = \sum_{k=2}^{\infty} \frac{e^{-\lambda} \lambda^k}{(k-2)!}$

*   **Step 5: Factor out $e^{-\lambda}$ and $\lambda^2$
    $E[X(X-1)] = e^{-\lambda} \lambda^2 \sum_{k=2}^{\infty} \frac{\lambda^{k-2}}{(k-2)!}$

*   **Step 6: Change the index of summation
    Let $m = k-2$. When $k=2$, $m=0$. When $k \to \infty$, $m \to \infty$.
    The summation becomes:
    $E[X(X-1)] = e^{-\lambda} \lambda^2 \sum_{m=0}^{\infty} \frac{\lambda^{m}}{m!}$

*   **Step 7: Recognize the Taylor series for $e^\lambda$
    The summation is the Taylor series expansion for $e^\lambda$:
    $\sum_{m=0}^{\infty} \frac{\lambda^{m}}{m!} = e^\lambda$

*   **Step 8: Final result for $E[X(X-1)]$
    $E[X(X-1)] = e^{-\lambda} \lambda^2 (e^\lambda) = \lambda^2$

#### Calculating $Var(X)$

Now we use the identity $Var(X) = E[X^2] - (E[X])^2$.
We know that $E[X^2] = E[X(X-1)] + E[X]$.

*   **Step 1: Substitute $E[X(X-1)]$ and $E[X]$ into the equation for $E[X^2]$**
    $E[X^2] = \lambda^2 + \lambda$

*   **Step 2: Substitute $E[X^2]$ and $E[X]$ into the variance formula**
    $Var(X) = (\lambda^2 + \lambda) - (\lambda)^2$
    $Var(X) = \lambda^2 + \lambda - \lambda^2$
    $Var(X) = \lambda$
    Thus, the variance of the Poisson distribution is $\lambda$.


---

## Solved Problems


---

### Question 40: Accidental Drowning Rate

> **Question:** According to the NDVS of US department of health & human services, the average number of accidental drownings per year in the U.S is 3.0 per 1,00,000 population. Find the probability that in a city of population 2,00,000, there will be:
> (a) exactly six drownings
> (b) fewer than 3 drownings
> (c) between 4 and 8 drownings (exclusive)
>
> **Answer:**
> First, we need to determine the appropriate value of $\lambda$ for the city's population.
> *   **Step 1:** Calculate $\lambda$ for the city of 2,00,000 population.
> The rate is 3.0 drownings per 1,00,000 population. For 2,00,000 population, the average number of drownings is:
> $\lambda = 3.0 \times \frac{2,00,000}{1,00,000} = 6$
>
> *   **Step 2:** Use the Poisson PMF: $P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$ with $\lambda=6$.
>
> **(a) Probability of exactly six drownings:**
> *   **Step 1:** Set $k=6$.
> *   **Step 2:** Calculate $P(X=6)$.
> $P(X=6) = \frac{e^{-6} 6^6}{6!} \approx 0.1606$
>
> **(b) Probability of fewer than 3 drownings:**
> *   **Step 1:** This means $P(X < 3)$, which is $P(X=0) + P(X=1) + P(X=2)$.
> *   **Step 2:** Calculate each term:
> *   $P(X=0) = \frac{e^{-6} 6^0}{0!} = e^{-6} \approx 0.00248$
> *   $P(X=1) = \frac{e^{-6} 6^1}{1!} = 6e^{-6} \approx 0.01487$
> *   $P(X=2) = \frac{e^{-6} 6^2}{2!} = \frac{36}{2}e^{-6} \approx 0.04462$
> *   **Step 3:** Sum the probabilities:
> $P(X < 3) \approx 0.00248 + 0.01487 + 0.04462 \approx 0.0619$
>
> **(c) Probability of between 4 and 8 drownings (exclusive):**
> *   **Step 1:** This means $P(4 < X < 8)$, which is $P(X=5) + P(X=6) + P(X=7)$.
> *   **Step 2:** Calculate each term:
> *   $P(X=5) = \frac{e^{-6} 6^5}{5!} \approx 0.1606$
> *   $P(X=6) = \frac{e^{-6} 6^6}{6!} \approx 0.1606$
> *   $P(X=7) = \frac{e^{-6} 6^7}{7!} \approx 0.1377$
> *   **Step 3:** Sum the probabilities:
> $P(4 < X < 8) \approx 0.1606 + 0.1606 + 0.1377 \approx 0.4589$
>
>
> ---


### Question 41: Taxi Driver Accidents

> **Question:** The number of accidents in a year to taxi drivers in a city follows a Poisson Distribution with a mean of 3 accidents per 1000 taxi drivers. If there are 1000 taxi drivers, find approximately the number of drivers with:
> (i) no accident in a year
> (ii) more than 3 accidents in a year
>
> **Answer:**
> The mean number of accidents per taxi driver is given as $\lambda = 3$.
> The Poisson PMF is $P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$.
>
> **(i) Number of drivers with no accident in a year:**
> *   **Step 1:** Calculate the probability of a single driver having no accidents ($k=0$).\n    $P(X=0) = \frac{e^{-3} 3^0}{0!} = e^{-3} \approx 0.0498$
> *   **Step 2:** Multiply this probability by the total number of drivers.
> Number of drivers $\approx 1000 \times 0.0498 \approx 50$
>
> **(ii) Number of drivers with more than 3 accidents in a year:**
> *   **Step 1:** Calculate the probability of a driver having more than 3 accidents, $P(X > 3)$. It's easier to calculate the complement: $P(X > 3) = 1 - P(X \le 3)$.
> *   **Step 2:** Calculate $P(X \le 3) = P(X=0) + P(X=1) + P(X=2) + P(X=3).$
> *   $P(X=0) \approx 0.0498$ (from part i)\n    *   $P(X=1) = \frac{e^{-3} 3^1}{1!} = 3e^{-3} \approx 0.1494$
> *   $P(X=2) = \frac{e^{-3} 3^2}{2!} = 4.5e^{-3} \approx 0.2240$
> *   $P(X=3) = \frac{e^{-3} 3^3}{3!} = 4.5e^{-3} \approx 0.2240$
> $P(X \le 3) \approx 0.0498 + 0.1494 + 0.2240 + 0.2240 \approx 0.6472$
> *   **Step 3:** Calculate $P(X > 3).$
> $P(X > 3) = 1 - 0.6472 = 0.3528$
> *   **Step 4:** Multiply by the total number of drivers.
> Number of drivers $\approx 1000 \times 0.3528 \approx 353$
>
> ***Note:*** The source document also contains an incorrect calculation where $\lambda$ was mistakenly calculated as $3/1000 = 0.003$. The calculations here use the correct interpretation where $\lambda=3$ represents the mean for the given population size.
>
>
> ---


### Question 42: Insurance Policy Claims

> **Question:** Suppose that an insurance company has discovered that only about 0.1% of the population is involved in a certain type of accident each year. If it has 10000 policy holders, what is the probability that not more than 5 of its clients are involved in such an accident next year?
>
> **Answer:**
> *   **Step 1:** Identify the parameters for the Poisson distribution.
> The average rate of accidents per policy holder is $p = 0.1\% = 0.001$.
> The total number of policy holders is $n = 10000$.
> The mean number of accidents for the group is $\lambda = np = 10000 \times 0.001 = 10$.
> *   **Step 2:** We need to find the probability that not more than 5 clients are involved, which is $P(X \le 5)$.
> *   **Step 3:** Calculate $P(X \le 5) = P(X=0) + P(X=1) + P(X=2) + P(X=3) + P(X=4) + P(X=5)$ using the Poisson PMF with $\lambda=10$.
> Using a Poisson cumulative probability table or calculator for $\lambda=10$:
> $P(X \le 5) \approx 0.0671$
>
>
> ---


### Question 43: Poisson Probability Relation

> **Question:** In a Poisson Distribution, suppose that $X$ has a Poisson distribution such that $P(X=2) = \frac{2}{3} P(X=1)$. Evaluate:
> 1) $P(X=0)$
> 2) $P(X=3)$
>
> **Answer:**
> *   **Step 1:** Use the Poisson PMF $P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$ and the given condition to find $\lambda$.
> $P(X=2) = \frac{e^{-\lambda} \lambda^2}{2!}$
> $P(X=1) = \frac{e^{-\lambda} \lambda^1}{1!}$
> Given: $\frac{e^{-\lambda} \lambda^2}{2!} = \frac{2}{3} \times \frac{e^{-\lambda} \lambda^1}{1!}$
> *   **Step 2:** Simplify the equation to solve for $\lambda$.
> $\frac{\lambda^2}{2} = \frac{2\lambda}{3}$
> Assuming $\lambda \ne 0$, we can divide both sides by $\lambda$:
> $\frac{\lambda}{2} = \frac{2}{3}$
> $\lambda = \frac{4}{3}$
>
> *   **Step 3:** Now, evaluate the required probabilities using $\lambda = 4/3$.
>
> 1) **Evaluate $P(X=0)$:**
> $P(X=0) = \frac{e^{-(4/3)} (4/3)^0}{0!} = \frac{e^{-4/3} \times 1}{1} = e^{-4/3} \approx 0.2636$
>
> 2) **Evaluate $P(X=3)$:**
> $P(X=3) = \frac{e^{-(4/3)} (4/3)^3}{3!} = \frac{e^{-4/3} \times (64/27)}{6} = \frac{64}{162} e^{-4/3} \approx 0.1041$
>
>
> ---


### Question 44: Even and Odd Poisson Probabilities

> **Question:** In a Poisson Distribution, prove that $P[X \text{ is even}] = \frac{1}{2} (1 + e^{-2\lambda})$ and $P[X \text{ is odd}] = \frac{1}{2} (1 - e^{-2\lambda})$.
>
> **Answer:**
> *   **Step 1:** Recall the Taylor series expansions for $e^\lambda$ and $e^{-\lambda}$:
> $e^\lambda = \sum_{k=0}^{\infty} \frac{\lambda^k}{k!} = \frac{\lambda^0}{0!} + \frac{\lambda^1}{1!} + \frac{\lambda^2}{2!} + \frac{\lambda^3}{3!} + \dots$
> $e^{-\lambda} = \sum_{k=0}^{\infty} \frac{(-\lambda)^k}{k!} = \frac{\lambda^0}{0!} - \frac{\lambda^1}{1!} + \frac{\lambda^2}{2!} - \frac{\lambda^3}{3!} + \dots$
>
> The Poisson PMF is $P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$.
>
> **Proof for $P(X \text{ is even})$:**
> *   **Step 2:** Write out the sum for $P(X \text{ is even})$.
> $P(X \text{ is even}) = P(X=0) + P(X=2) + P(X=4) + \dots$
> $P(X \text{ is even}) = \sum_{k \text{ even}} \frac{e^{-\lambda} \lambda^k}{k!} = e^{-\lambda} \sum_{k \text{ even}} \frac{\lambda^k}{k!}$
> $P(X \text{ is even}) = e^{-\lambda} \left( \frac{\lambda^0}{0!} + \frac{\lambda^2}{2!} + \frac{\lambda^4}{4!} + \dots \right)$
> *   **Step 3:** Relate the sum of even terms to $e^\lambda$ and $e^{-\lambda}$.
> Consider the sum: $e^\lambda + e^{-\lambda} = 2 \left( \frac{\lambda^0}{0!} + \frac{\lambda^2}{2!} + \frac{\lambda^4}{4!} + \dots \right)$
> Therefore, $\left( \frac{\lambda^0}{0!} + \frac{\lambda^2}{2!} + \frac{\lambda^4}{4!} + \dots \right) = \frac{e^\lambda + e^{-\lambda}}{2}$
> *   **Step 4:** Substitute back into the expression for $P(X \text{ is even})$.
> $P(X \text{ is even}) = e^{-\lambda} \left( \frac{e^\lambda + e^{-\lambda}}{2} \right) = \frac{e^{-\lambda}e^\lambda + e^{-\lambda}e^{-\lambda}}{2} = \frac{1 + e^{-2\lambda}}{2}$
> **(Proved)**
>
> **Proof for $P(X \text{ is odd})$:**
> *   **Step 5:** Write out the sum for $P(X \text{ is odd})$.
> $P(X \text{ is odd}) = P(X=1) + P(X=3) + P(X=5) + \dots$
> $P(X \text{ is odd}) = \sum_{k \text{ odd}} \frac{e^{-\lambda} \lambda^k}{k!} = e^{-\lambda} \sum_{k \text{ odd}} \frac{\lambda^k}{k!}$
> $P(X \text{ is odd}) = e^{-\lambda} \left( \frac{\lambda^1}{1!} + \frac{\lambda^3}{3!} + \frac{\lambda^5}{5!} + \dots \right)$
> *   **Step 6:** Relate the sum of odd terms to $e^\lambda$ and $e^{-\lambda}$.
> Consider the difference: $e^\lambda - e^{-\lambda} = 2 \left( \frac{\lambda^1}{1!} + \frac{\lambda^3}{3!} + \frac{\lambda^5}{5!} + \dots \right)$
> Therefore, $\left( \frac{\lambda^1}{1!} + \frac{\lambda^3}{3!} + \frac{\lambda^5}{5!} + \dots \right) = \frac{e^\lambda - e^{-\lambda}}{2}$
> *   **Step 7:** Substitute back into the expression for $P(X \text{ is odd})$.
> $P(X \text{ is odd}) = e^{-\lambda} \left( \frac{e^\lambda - e^{-\lambda}}{2} \right) = \frac{e^{-\lambda}e^\lambda - e^{-\lambda}e^{-\lambda}}{2} = \frac{1 - e^{-2\lambda}}{2}$
> **(Proved)**

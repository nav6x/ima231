# Binomial Distribution

[← Back to Course README](../README.md)

- [Derivation of Mean and Variance](#derivation-of-mean-and-variance)
- [Derivation of the Mean $E[X]$](#derivation-of-the-mean-ex)
- [Derivation of the Variance $Var(X)$](#derivation-of-the-variance-varx)
    - [Derivation of $E[X(X-1)]$](#derivation-of-exx-1)
    - [Calculating $Var(X)$](#calculating-varx)
  - [Question 36: Tossing Six Coins](#question-36-tossing-six-coins)
  - [Question 37: Mean and Variance of Binomial Distribution](#question-37-mean-and-variance-of-binomial-distribution)
  - [Question 38: Children Gender Probability](#question-38-children-gender-probability)
  - [Question 39: Opponent Games Probability](#question-39-opponent-games-probability)

> **Topic**: Binomial Distribution: Derivation of Mean and Variance, Derivation of the Mean $E[X]$, Derivation of the Variance $Var(X)$

---

## Derivation of Mean and Variance

For a Binomial Distribution, the probability mass function (PMF) is given by:
$P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}$
where $n$ is the number of trials, $p$ is the probability of success, and $k$ is the number of successes.


---

## Derivation of the Mean $E[X]$

The mean (expected value) of a discrete random variable is defined as $E[X] = \sum_{k=0}^{n} k \cdot P(X=k)$.

*   **Step 1: Set up the summation for $E[X]$**
    $E[X] = \sum_{k=0}^{n} k \binom{n}{k} p^k (1-p)^{n-k}$

*   **Step 2: Handle the $k=0$ term and expand $\binom{n}{k}$**
    The term for $k=0$ is $0 \cdot P(X=0) = 0$, so we can start the summation from $k=1$.
    Recall that $\binom{n}{k} = \frac{n!}{k!(n-k)!}$.
    $E[X] = \sum_{k=1}^{n} k \frac{n!}{k!(n-k)!} p^k (1-p)^{n-k}$

*   **Step 3: Simplify the term $k \cdot \frac{n!}{k!}$**
    $k \cdot \frac{n!}{k!} = k \cdot \frac{n!}{k(k-1)!} = \frac{n!}{(k-1)!(n-k)!}$

*   **Step 4: Substitute the simplified term back into the summation**
    $E[X] = \sum_{k=1}^{n} \frac{n!}{(k-1)!(n-k)!} p^k (1-p)^{n-k}$

*   **Step 5: Factor out $n$ and $p$**
    We can write $n! = n \cdot (n-1)!$ and $p^k = p \cdot p^{k-1}$.
    $E[X] = np \sum_{k=1}^{n} \frac{(n-1)!}{(k-1)!(n-k)!} p^{k-1} (1-p)^{n-k}$

*   **Step 6: Change the index of summation**
    Let $j = k-1$. When $k=1$, $j=0$. When $k=n$, $j=n-1$.
    Also, $n-k = (n-1) - (k-1) = (n-1) - j$.
    The summation becomes:
    $E[X] = np \sum_{j=0}^{n-1} \frac{(n-1)!}{j!((n-1)-j)!} p^{j} (1-p)^{(n-1)-j}$

*   **Step 7: Recognize the Binomial PMF**
    The summation term is the sum of probabilities for a Binomial Distribution with parameters $(n-1)$ and $p$. Since it sums over all possible values of $j$ for this new distribution, the sum is equal to 1.
    $\sum_{j=0}^{n-1} \binom{n-1}{j} p^{j} (1-p)^{(n-1)-j} = 1$

*   **Step 8: Final result for $E[X]$**
    $E[X] = np \cdot 1 = np$


---

## Derivation of the Variance $Var(X)$

The variance is defined as $Var(X) = E[X^2] - (E[X])^2$. We already know $E[X] = np$. So, we need to find $E[X^2]$.
It's often easier to calculate $E[X(X-1)]$ first.

#### Derivation of $E[X(X-1)]$

*   **Step 1: Set up the summation for $E[X(X-1)]$**
    $E[X(X-1)] = \sum_{k=0}^{n} k(k-1) P(X=k)$
    $E[X(X-1)] = \sum_{k=0}^{n} k(k-1) \binom{n}{k} p^k (1-p)^{n-k}$

*   **Step 2: Handle the $k=0$ and $k=1$ terms**
    The terms for $k=0$ and $k=1$ are $0 \cdot (-1) \cdot P(X=0) = 0$ and $1 \cdot (0) \cdot P(X=1) = 0$.
    So, we can start the summation from $k=2$.
    $E[X(X-1)] = \sum_{k=2}^{n} k(k-1) \frac{n!}{k!(n-k)!} p^k (1-p)^{n-k}$

*   **Step 3: Simplify the term $k(k-1) \cdot \frac{n!}{k!}$**
    $k(k-1) \cdot \frac{n!}{k!} = k(k-1) \cdot \frac{n!}{k(k-1)(k-2)!} = \frac{n!}{(k-2)!(n-k)!}$

*   **Step 4: Substitute the simplified term back into the summation**
    $E[X(X-1)] = \sum_{k=2}^{n} \frac{n!}{(k-2)!(n-k)!} p^k (1-p)^{n-k}$

*   **Step 5: Factor out $n(n-1)$ and $p^2$**
    We can write $n! = n(n-1)(n-2)!$ and $p^k = p^2 p^{k-2}$.
    $E[X(X-1)] = n(n-1)p^2 \sum_{k=2}^{n} \frac{(n-2)!}{(k-2)!(n-k)!} p^{k-2} (1-p)^{n-k}$

*   **Step 6: Change the index of summation**
    Let $m = k-2$. When $k=2$, $m=0$. When $k=n$, $m=n-2$.
    Also, $n-k = (n-2) - (k-2) = (n-2) - m$.
    The summation becomes:
    $E[X(X-1)] = n(n-1)p^2 \sum_{m=0}^{n-2} \frac{(n-2)!}{m!((n-2)-m)!} p^{m} (1-p)^{(n-2)-m}$

*   **Step 7: Recognize the Binomial PMF**
    The summation term is the sum of probabilities for a Binomial Distribution with parameters $(n-2)$ and $p$. This sum is equal to 1.
    $\sum_{m=0}^{n-2} \binom{n-2}{m} p^{m} (1-p)^{(n-2)-m} = 1$

*   **Step 8: Final result for $E[X(X-1)]$**
    $E[X(X-1)] = n(n-1)p^2 \cdot 1 = n(n-1)p^2$

#### Calculating $Var(X)$

Now we use the identity $Var(X) = E[X^2] - (E[X])^2$.
We know that $E[X^2] = E[X(X-1)] + E[X]$.

*   **Step 1: Substitute $E[X(X-1)]$ and $E[X]$ into the equation for $E[X^2]$**
    $E[X^2] = n(n-1)p^2 + np$

*   **Step 2: Substitute $E[X^2]$ and $E[X]$ into the variance formula**
    $Var(X) = (n(n-1)p^2 + np) - (np)^2$
    $Var(X) = n^2p^2 - np^2 + np - n^2p^2$
    $Var(X) = np - np^2$

*   **Step 3: Factor out $np$**
    $Var(X) = np(1-p)$


---

### Question 36: Tossing Six Coins

> **Question:** Six coins are tossed. Find the probability of getting:
> (i) exactly 3 heads
> (ii) at most 3 heads
> (iii) at least 3 heads
> (iv) at least one head
>
> **Answer:**
> Let $X$ be the random variable representing the number of heads in 6 coin tosses.
> This follows a Binomial Distribution with parameters $n=6$ (number of trials) and $p=0.5$ (probability of success, i.e., getting a head).
> The probability mass function (PMF) for a Binomial Distribution is given by:
> $P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}$
> Here, $n=6$ and $p=0.5$, so $(1-p)=0.5$.
> $P(X=k) = \binom{6}{k} (0.5)^k (0.5)^{6-k} = \binom{6}{k} (0.5)^6$
>
> **(i) Exactly 3 heads:**
> *   **Step 1:** Identify $k=3$.
> *   **Step 2:** Calculate $P(X=3)$.
> $P(X = 3) = \binom{6}{3} (0.5)^6 = 20 \times 0.015625 = 0.3125$
>
> **(ii) At most 3 heads:**
> *   **Step 1:** This means $X \le 3$. We need to calculate $P(X=0) + P(X=1) + P(X=2) + P(X=3)$.
> *   **Step 2:** Calculate individual probabilities:
> *   $P(X=0) = \binom{6}{0} (0.5)^6 = 1 \times 0.015625 = 0.015625$
> *   $P(X=1) = \binom{6}{1} (0.5)^6 = 6 \times 0.015625 = 0.09375$
> *   $P(X=2) = \binom{6}{2} (0.5)^6 = 15 \times 0.015625 = 0.234375$
> *   $P(X=3) = \binom{6}{3} (0.5)^6 = 20 \times 0.015625 = 0.3125$
> *   **Step 3:** Sum these probabilities:
> $P(X \le 3) = 0.015625 + 0.09375 + 0.234375 + 0.3125 = 0.65625$
> *(Note: The original text calculated $P(X \le 2)$ for "at most 3 heads". The calculation above is for $P(X \le 3)$ as per the question.)*
>
> **(iii) At least 3 heads:**
> *   **Step 1:** This means $X \ge 3$. We need to calculate $P(X=3) + P(X=4) + P(X=5) + P(X=6)$.
> *   **Step 2:** Calculate individual probabilities:
> *   $P(X=3) = 0.3125$ (from part i)
> *   $P(X=4) = \binom{6}{4} (0.5)^6 = 15 \times 0.015625 = 0.234375$
> *   $P(X=5) = \binom{6}{5} (0.5)^6 = 6 \times 0.015625 = 0.09375$
> *   $P(X=6) = \binom{6}{6} (0.5)^6 = 1 \times 0.015625 = 0.015625$
> *   **Step 3:** Sum these probabilities:
> $P(X \ge 3) = 0.3125 + 0.234375 + 0.09375 + 0.015625 = 0.65625$
>
> **(iv) At least one head:**
> *   **Step 1:** This means $X \ge 1$. It's easier to calculate the complement: $P(X \geq 1) = 1 - P(X=0)$.
> *   **Step 2:** Calculate $P(X=0)$.
> $P(X=0) = \binom{6}{0} (0.5)^6 = 1 \times 0.015625 = 0.015625$
> *   **Step 3:** Calculate $P(X \geq 1)$.
> $P(X \geq 1) = 1 - 0.015625 = 0.984375$
>
>
> ---


### Question 37: Mean and Variance of Binomial Distribution

> **Question:** The mean and variance of a Binomial Distribution are 4 and 4/3 respectively. Find $P(X \ge 1)$.
>
> **Answer:**
> For a Binomial Distribution, Mean $(\mu) = np$ and Variance $(\sigma^2) = np(1-p)$.
>
> *   **Step 1:** Use the given mean and variance to find $n$ and $p$.
> $np = 4$  (Equation 1)
> $np(1-p) = 4/3$ (Equation 2)
> *   **Step 2:** Substitute Equation 1 into Equation 2:
> $4(1-p) = 4/3$
> $1-p = \frac{4/3}{4} = 1/3$
> $p = 1 - 1/3 = 2/3$
> *   **Step 3:** Find $n$ using Equation 1:
> $n(2/3) = 4 \Rightarrow n = 4 \times (3/2) = 6$
> *   **Step 4:** Now we have $n=6$ and $p=2/3$. We need to find $P(X \ge 1)$.
> $P(X \ge 1) = 1 - P(X=0)$
> *   **Step 5:** Calculate $P(X=0)$ using the Binomial PMF:
> $P(X=0) = \binom{n}{0} p^0 (1-p)^{n-0} = \binom{6}{0} (2/3)^0 (1/3)^6$
> $P(X=0) = 1 \times 1 \times (1/729) = 1/729$
> *   **Step 6:** Calculate $P(X \ge 1)$:
> $P(X \ge 1) = 1 - 1/729 = 728/729 \approx 0.9986$
>
>
> ---


### Question 38: Children Gender Probability

> **Question:** Find the probability that in a family of 4 children, there will be at least one boy. Assume the probability of male birth is 1/2 (0.5).
>
> **Answer:**
> Let $X$ be the number of boys in a family of 4 children.
> This is a Binomial Distribution with $n=4$ and $p=0.5$ (probability of having a boy).
> We need to find $P(X \ge 1)$.
>
> *   **Step 1:** Use the complement rule: $P(X \ge 1) = 1 - P(X=0)$.
> *   **Step 2:** Calculate $P(X=0)$ (probability of having 0 boys, i.e., all girls).
> $P(X=0) = \binom{4}{0} (0.5)^0 (0.5)^{4-0} = 1 \times 1 \times (0.5)^4 = 0.0625$
> *   **Step 3:** Calculate $P(X \ge 1)$.
> $P(X \ge 1) = 1 - 0.0625 = 0.9375$
>
>
> ---


### Question 39: Opponent Games Probability

> **Question:** In playing with an opponent of equal ability, which is more probable?
> - winning 3 games out of 4
> - winning 5 games out of 8
>
> **Answer:**
> Assume the probability of winning a single game is $p=0.5$ (equal ability).
>
> **Case 1: Winning 3 games out of 4**
> This follows a Binomial Distribution with $n=4$ and $p=0.5$. We need to find $P(X=3)$.
> *   **Step 1:** Use the Binomial PMF: $P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}$.
> *   **Step 2:** Calculate $P(X=3)$ for $n=4, k=3, p=0.5$.
> $P(X=3) = \binom{4}{3} (0.5)^3 (0.5)^{4-3} = 4 \times (0.5)^3 \times (0.5)^1 = 4 \times 0.125 \times 0.5 = 0.25$
>
> **Case 2: Winning 5 games out of 8**
> This follows a Binomial Distribution with $n=8$ and $p=0.5$. We need to find $P(X=5)$.
> *   **Step 1:** Use the Binomial PMF.
> *   **Step 2:** Calculate $P(X=5)$ for $n=8, k=5, p=0.5$.
> $P(X=5) = \binom{8}{5} (0.5)^5 (0.5)^{8-5} = 56 \times (0.5)^5 \times (0.5)^3 = 56 \times (0.5)^8$
> $P(X=5) = 56 \times 0.00390625 = 0.21875$
>
> **Conclusion:** Comparing the probabilities, $0.25 > 0.21875$. Therefore, it is more probable to win 3 games out of 4.

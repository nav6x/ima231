# Joint, Marginal, and Conditional Distributions

[← Back to Course README](../README.md)

- [Two-Dimensional Random Variables](#two-dimensional-random-variables)
- [Joint PMF for Discrete RVs](#joint-pmf-for-discrete-rvs)
- [Joint PDF for Continuous RVs](#joint-pdf-for-continuous-rvs)
- [Marginal Distributions](#marginal-distributions)
- [Marginal PMF (Discrete)](#marginal-pmf-discrete)
- [Marginal PDF (Continuous)](#marginal-pdf-continuous)
  - [Question 18: Discrete Joint PMF & Marginal PMF](#question-18-discrete-joint-pmf-marginal-pmf)
  - [Question 19: Joint PMF for Marble Selection](#question-19-joint-pmf-for-marble-selection)
  - [Question 20: Finding Constant k for Joint PMF](#question-20-finding-constant-k-for-joint-pmf)
  - [Question 21: Marginal PDF from Continuous Joint PDF](#question-21-marginal-pdf-from-continuous-joint-pdf)
  - [Question 22: Joint PDF and Region Probability](#question-22-joint-pdf-and-region-probability)
  - [Question 23: Exponential-type Joint PDF](#question-23-exponential-type-joint-pdf)
- [Mean, Variance, Covariance, and Correlation](#mean-variance-covariance-and-correlation)
- [Mean and Variance (2D RV)](#mean-and-variance-2d-rv)
- [Covariance](#covariance)
- [Correlation Coefficient ($\rho$)](#correlation-coefficient-rho)
  - [Question 24: Covariance of Linear Transformations](#question-24-covariance-of-linear-transformations)
- [Conditional Probabilities](#conditional-probabilities)
- [Discrete Case](#discrete-case)
- [Continuous Case](#continuous-case)
- [Properties of Expectation and Variance](#properties-of-expectation-and-variance)
- [Covariance and Independence Anomaly](#covariance-and-independence-anomaly)
  - [Question 25: Exponential Joint PDF & Independence Test](#question-25-exponential-joint-pdf-independence-test)
  - [Team Question 16](#team-question-16)

> **Topic**: Joint, Marginal, and Conditional Distributions: Two-Dimensional Random Variables, Joint PMF for Discrete RVs, Joint PDF for Continuous RVs, Marginal Distributions

---

## Two-Dimensional Random Variables

Let 'E' be an experiment & 'S' a sample space associated with E. Let X = X(s) and Y = Y(s) be two functions, each assigning a real number to each outcome $s \in S$. We call (X, Y) a two-dimensional random variable (or random vector).

-   When (X,Y) => discrete, X & Y are discrete.
-   When (X,Y) => continuous, X & Y are continuous.
-   However, in (X,Y), either X or Y being discrete and the other being continuous is a possibility.


---

## Joint PMF for Discrete RVs

For a discrete random variable (d.r.v), the joint PMF is given by:
$p(x_i, y_j) = P(X = x_i, Y = y_j)$

It must satisfy:
1.  $p(x_i, y_j) \geq 0$
2.  $\sum_{i} \sum_{j} p(x_i, y_j) = 1$


---

## Joint PDF for Continuous RVs

For a 2D continuous random variable (c.r.v), the joint PDF $f(x, y)$ must satisfy:
1.  $f(x, y) \geq 0$
2.  $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(x, y) dx dy = 1$

The **Cumulative Distribution Function (CDF)** is $F(x, y) = P(X \leq x, Y \leq y)$.


---

## Marginal Distributions

The marginal distribution of one variable can be obtained by summing or integrating over the other variable.


---

## Marginal PMF (Discrete)

-   **Marginal PMF of X**: $p(x_i) = \sum_{j} p(x_i, y_j)$
-   **Marginal PMF of Y**: $q(y_j) = \sum_{i} p(x_i, y_j)$


---

## Marginal PDF (Continuous)

-   **Marginal PDF of X**: $g(x) = \int_{-\infty}^{\infty} f(x, y) dy$
-   **Marginal PDF of Y**: $h(y) = \int_{-\infty}^{\infty} f(x, y) dx$


---

### Question 18: Discrete Joint PMF & Marginal PMF

> Compute marginal PMF of X and Y, $P[ x < 1, y < 1]$.
>
> | y/x | 0    | 1    | 2    | q(y) |
> | --- | ---- | ---- | ---- | ---- |
> | **0** | 0.1  | 0.04 | 0.02 | 0.16 |
> | **1** | 0.08 | 0.20 | 0.06 | 0.34 |
> | **2** | 0.06 | 0.14 | 0.30 | 0.50 |
> | **p(x)**| 0.24 | 0.38 | 0.38 |      |
>
> **Answer**
>
> **Marginal PMF of X**
> - $p(0) = 0.24$
> - $p(1) = 0.38$
> - $p(2) = 0.38$
>
> **Marginal PMF of Y**
> - $q(0) = 0.16$
> - $q(1) = 0.34$
> - $q(2) = 0.50$
>
> $P[X < 1, Y < 1] = P(X=0, Y=0) = 0.1$
> *(Note: The calculation in original notes corresponds to P[X<2, Y<2] = 0.42)*
>
>
>
> ---


### Question 19: Joint PMF for Marble Selection

> 2 marbles are selected randomly from a box that contains 3 blue marbles, 2 red marbles and 3 green marbles. If X is the no of blue marbles and Y is the no of red marbles selected, find the joint pmf and marginal pmfs of X and Y.
>
> **Answer**
>
> | y/x | 0      | 1      | 2      | p(y)   |
> | --- | ------ | ------ | ------ | ------ |
> | **0** | 0.1071 | 0.3214 | 0.1071 | 0.5356 |
> | **1** | 0.2143 | 0.2143 | 0      | 0.4286 |
> | **2** | 0.0357 | 0      | 0      | 0.0357 |
> | **q(x)**| 0.3571 | 0.5357 | 0.1071 |        |
>
>
>
> ---


### Question 20: Finding Constant k for Joint PMF

> The joint pmf of $x,y$ is given by $p(x, y) = K (2x + 3y)$; $x = 0, 1, 2$, $Y=1,2,3$. Find the value of $k$ and the marginal PMF of $X$ and $Y$.
>
> **Answer**
>
> To find the value of $k$, we use the property that the sum of all probabilities must be $1$.
> $\sum_{x} \sum_{y} p(x,y) = 1$
> $\sum_{x=0}^{2} \sum_{y=1}^{3} K(2x+3y) = 1$
> $K [ (0+3)+(0+6)+(0+9) + (2+3)+(2+6)+(2+9) + (4+3)+(4+6)+(4+9) ] = 1$
> $K [ 18 + 24 + 30 ] = 1$
> $K [72] = 1 \Rightarrow K = \frac{1}{72}$
>
> **Marginal PMF of X**
> $p(x) = \sum_{y} p(x,y)$
> - $p(0) = \sum_{y=1}^{3} \frac{1}{72}(0+3y) = \frac{1}{72}(3+6+9) = \frac{18}{72}$
> - $p(1) = \sum_{y=1}^{3} \frac{1}{72}(2+3y) = \frac{1}{72}(5+8+11) = \frac{24}{72}$
> - $p(2) = \sum_{y=1}^{3} \frac{1}{72}(4+3y) = \frac{1}{72}(7+10+13) = \frac{30}{72}$
>
> **Marginal PMF of Y**
> $q(y) = \sum_{x} p(x,y)$
> - $q(1) = \sum_{x=0}^{2} \frac{1}{72}(2x+3) = \frac{1}{72}(3+5+7) = \frac{15}{72}$
> - $q(2) = \sum_{x=0}^{2} \frac{1}{72}(2x+6) = \frac{1}{72}(6+8+10) = \frac{24}{72}$
> - $q(3) = \sum_{x=0}^{2} \frac{1}{72}(2x+9) = \frac{1}{72}(9+11+13) = \frac{33}{72}$
>
>
>
> ---


### Question 21: Marginal PDF from Continuous Joint PDF

> The joint PDF of a 2D RV is:
> $f(x,y) = 2(x+y-2xy)$ for $0 \leq x \leq 1, 0 \leq y \leq 1$
> Find the marginal PDF of X.
>
> **Answer**
> $g(x) = \int_{-\infty}^{\infty} f(x,y) dy = \int_{0}^{1} 2(x+y-2xy) dy$
> $= [2xy + y^2 - 2xy^2]_{y=0}^{1}$
> $= (2x(1) + 1^2 - 2x(1)^2) - 0 = 2x + 1 - 2x = 1$
> So, $g(x) = 1$ for $0 \leq x \leq 1$ and $0$ elsewhere.
>
>
>
> ---


### Question 22: Joint PDF and Region Probability

> The joint PDF of two-dimensional RV $(x,y)$ is:
> $f(x,y) = 4xy; 0<x<1, 0<y<1$
> $f(x,y) = 0; \text{otherwise}$
>
> (i) **Find marginal pdf of Y**
> (ii) **Find $P(x+y < 1)$**
>
> **Answer**
>
> (i) **Marginal PDF of Y**
> $h(y) = \int_{-\infty}^{\infty} f(x,y) dx = \int_{0}^{1} 4xy dx$
> $= [2x^2y]_{x=0}^{1} = 2y$
> So, $h(y) = 2y; 0<y<1$ and $0$ otherwise.
>
> (ii) **$P(X+Y < 1) = P(X < 1-Y)$**
> $\int_{y=0}^{1} \int_{x=0}^{1-y} 4xy dx dy$
> $= \int_{y=0}^{1} [2x^2y]_{x=0}^{1-y} dy$
> $= \int_{y=0}^{1} 2(1-y)^2 y dy$
> $= \int_{y=0}^{1} 2(1+y^2-2y)y dy$
> $= \int_{y=0}^{1} (2y + 2y^3 - 4y^2) dy$
> $= [y^2 + \frac{y^4}{2} - \frac{4y^3}{3}]_{0}^{1}$
> $= 1 + \frac{1}{2} - \frac{4}{3} = \frac{6+3-8}{6} = \frac{1}{6}$
>
>
>
> ---


### Question 23: Exponential-type Joint PDF

> The joint PDF of RV $(x,y)$ is given by:
> $f(x,y) = kxye^{-(x^2+y^2)}$ for $x>0, y>0$
> Find the marginal PDF of $X$ and $Y$.
>
> **Answer**
>
> 1.  **Find k:**
> $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f(x,y) dxdy = 1$
> $\int_{0}^{\infty} \int_{0}^{\infty} kxye^{-(x^2+y^2)} dxdy = 1$
> $k \cdot (\int_{0}^{\infty} xe^{-x^2} dx) \cdot (\int_{0}^{\infty} ye^{-y^2} dy) = 1$
> Let's solve $\int_{0}^{\infty} xe^{-x^2} dx$. Let $u = x^2$, $du = 2x dx$.
> $\int xe^{-x^2} dx = \frac{1}{2}\int e^{-u} du = -\frac{1}{2} e^{-u} = -\frac{1}{2} e^{-x^2}$.
> $[ -\frac{1}{2} e^{-x^2} ]_{0}^{\infty} = 0 - (-\frac{1}{2}) = \frac{1}{2}$.
> So, $k \cdot (\frac{1}{2}) \cdot (\frac{1}{2}) = 1 \Rightarrow k=4$.
>
> 2.  **Marginal PDF of X:**
> $g(x) = \int_{0}^{\infty} 4xye^{-(x^2+y^2)} dy = 4xe^{-x^2} \int_{0}^{\infty} ye^{-y^2} dy$
> $g(x) = 4xe^{-x^2} \cdot (\frac{1}{2}) = 2xe^{-x^2}$ for $x>0$.
>
> 3.  **Marginal PDF of Y:**
> By symmetry, $h(y) = 2ye^{-y^2}$ for $y>0$.
>
>
>
> ---


## Mean, Variance, Covariance, and Correlation


---

## Mean and Variance (2D RV)

The mean/expected value of a random variable $g(x,y)$ is:
-   **Discrete**: $E[g(x,y)] = \sum_{i} \sum_{j} g(x_i, y_j) p(x_i, y_j)$
-   **Continuous**: $E[g(x,y)] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x,y) f(x,y) dx dy$


---

## Covariance

Covariance is the relation b/w two random variables.
$\text{Cov}(X,Y) = E[(X - E[X])(Y - E[Y])]$
Alternate definition: $\text{Cov}(X,Y) = E[XY] - E[X]E[Y]$

-   If covariance $> 0$, the variables are said to be positively correlated.
-   If it has a value $= 0$, correlation is also nil/0; there is no correlation.
-   If value $< 0$, variables have a negative correlation.

**Note**: For independent RVs, covariance $= 0$. $E[XY] = E[X]E[Y]$. However, if covariance is $0$, it does not mean that $X$ and $Y$ are independent random variables.


---

## Correlation Coefficient ($\rho$)

Informs us regarding the extent of correlation.
$\rho = \frac{\text{Cov}(X,Y)}{\sqrt{V(X)V(Y)}}$

-   $-1 \leq \rho \leq 1$ (always lies within this range)
-   If $\rho = 1$, variables are strongly positively correlated.
-   If $\rho = -1$, variables are strongly negatively correlated.
-   If $\rho$ is closer to $0$, then the variables are either weakly positively or negatively correlated.


---

### Question 24: Covariance of Linear Transformations

> Two independent RVs $X_1$ and $X_2$ have means $5$ and $10$ respectively and $4$ and $9$ variances respectively. Find the covariance b/w $U = 3X_1 + 4X_2$ and $V = 3X_1 - X_2$.
>
> **Answer**
> $\text{Cov}(U,V) = E(UV) - E(U)E(V)$
> $E(U) = E(3X_1 + 4X_2) = 3E(X_1) + 4E(X_2) = 3 \cdot 5 + 4 \cdot 10 = 55$
> $E(V) = E(3X_1 - X_2) = 3E(X_1) - E(X_2) = 3 \cdot 5 - 10 = 5$
> $UV = (3X_1 + 4X_2)(3X_1 - X_2) = 9X_1^2 - 3X_1X_2 + 12X_1X_2 - 4X_2^2 = 9X_1^2 + 9X_1X_2 - 4X_2^2$
> $E(UV) = 9E(X_1^2) + 9E(X_1X_2) - 4E(X_2^2)$
> Since $X_1$ and $X_2$ are independent, $E(X_1X_2) = E(X_1)E(X_2) = 5 \cdot 10 = 50$.
> $V(X) = E(X^2) - [E(X)]^2 \Rightarrow E(X^2) = V(X) + [E(X)]^2$
> $E(X_1^2) = V(X_1) + [E(X_1)]^2 = 4 + 5^2 = 29$
> $E(X_2^2) = V(X_2) + [E(X_2)]^2 = 9 + 10^2 = 109$
> $E(UV) = 9(29) + 9(50) - 4(109) = 261 + 450 - 436 = 275$
> $\text{Cov}(U,V) = 275 - (55)(5) = 275 - 275 = 0$
>
>
>
> ---


## Conditional Probabilities


---

## Discrete Case
-   $p(x_i|y_j) = \frac{p(x_i, y_j)}{q(y_j)}$
-   $q(y_j|x_i) = \frac{p(x_i, y_j)}{p(x_i)}$


---

## Continuous Case
-   $g(x|y) = \frac{f(x,y)}{h(y)}$
-   $h(y|x) = \frac{f(x,y)}{g(x)}$


---

## Properties of Expectation and Variance

-   $E(aX + bY) = aE(X) + bE(Y)$
-   $V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\text{Cov}(X,Y)$
-   For linear transformations $U = aX + b$ and $V = cY + d$, the correlation coefficient is $\rho_{UV} = \frac{ac}{|ac|} \rho_{XY}$.


---

## Covariance and Independence Anomaly

An important concept is that while independent random variables always have a covariance of zero, the reverse is not always true. A covariance of zero does not guarantee independence.

**Proof by Example:**
Let a random variable $X$ have values $\{-1, 0, 1\}$ with equal probability $p(x) = \frac{1}{3}$ for each value.
Let another random variable be $Y = X^2$.

1.  **Check for dependence:**
    The value of $Y$ is completely determined by the value of $X$. For instance, if we know $X = 1$, then $Y$ must be $1$. This means the variables are **not independent**.

2.  **Calculate Covariance:**
    $\text{Cov}(X,Y) = E[XY] - E[X]E[Y]$

    *   **$E[X]$:**
        $E[X] = (-1)(\frac{1}{3}) + (0)(\frac{1}{3}) + (1)(\frac{1}{3}) = 0$

    *   **$E[Y]$:**
        The values of $Y$ are $(-1)^2=1$, $(0)^2=0$, $(1)^2=1$.
        $p(Y=1) = p(X=-1) + p(X=1) = \frac{1}{3} + \frac{1}{3} = \frac{2}{3}$
        $p(Y=0) = p(X=0) = \frac{1}{3}$
        $E[Y] = (1)(\frac{2}{3}) + (0)(\frac{1}{3}) = \frac{2}{3}$

    *   **$E[XY]$:**
        $XY = X \cdot X^2 = X^3$. The values for $XY$ are $(-1)^3=-1$, $(0)^3=0$, $(1)^3=1$.
        $E[XY] = E[X^3] = (-1)(\frac{1}{3}) + (0)(\frac{1}{3}) + (1)(\frac{1}{3}) = 0$

    *   **$\text{Cov}(X,Y)$:**
        $\text{Cov}(X,Y) = 0 - (0)(\frac{2}{3}) = 0$

**Conclusion:** We have found an example where `Cov(X,Y) = 0`, but the variables X and Y are clearly dependent.


---

### Question 25: Exponential Joint PDF & Independence Test

> Suppose joint PDF is given by:
> $f(x,y) = e^{-y}$ for $x>0, y>x$
> $f(x,y) = 0$ otherwise.
> Find the marginal pdf of $x$ and $y$. Examine for independence.
>
> **Answer**
>
> **Marginal PDF of x**
> $g(x) = \int_{-\infty}^{\infty} f(x,y) dy = \int_{x}^{\infty} e^{-y} dy$
> $= [-e^{-y}]_{y=x}^{\infty} = 0 - (-e^{-x}) = e^{-x}$
> So, $g(x) = e^{-x}$ for $x>0$.
>
> **Marginal PDF of y**
> The bounds for $x$ are $0 < x < y$.
> $h(y) = \int_{-\infty}^{\infty} f(x,y) dx = \int_{0}^{y} e^{-y} dx$
> $= e^{-y} [x]_{x=0}^{y} = e^{-y} (y-0) = ye^{-y}$
> So, $h(y) = ye^{-y}$ for $y>0$.
>
> **Examine for independence**
> To check for independence, we see if $f(x,y) = g(x)h(y)$.
> $g(x)h(y) = (e^{-x})(ye^{-y}) = ye^{-(x+y)}$
> This is not equal to the original joint PDF $f(x,y) = e^{-y}$.
> Therefore, $X$ and $Y$ are **not independent**.


### Team Question 16

Suppose the joint pdf of 2D RV $(x,y)$ is given by:
$f(x,y) = x^2 + \frac{xy}{3}$ for $0<x<1, 0<y<2$
Calculate the following:
(i) $P(X > \frac{1}{2})$
(ii) $P(Y < X)$
(iii) $P(X+Y > 1)$

**Answer**

(i) **$P(X > \frac{1}{2})$**
$\int_{x=\frac{1}{2}}^{1} \int_{y=0}^{2} (x^2 + \frac{xy}{3}) dy dx$
$= \int_{x=\frac{1}{2}}^{1} [x^2y + \frac{xy^2}{6}]_{y=0}^{2} dx$
$= \int_{x=\frac{1}{2}}^{1} (2x^2 + \frac{4x}{6}) dx = \int_{x=\frac{1}{2}}^{1} (2x^2 + \frac{2x}{3}) dx$
$= [\frac{2x^3}{3} + \frac{x^2}{3}]_{\frac{1}{2}}^{1}$
$= (\frac{2}{3} + \frac{1}{3}) - (\frac{2(1/8)}{3} + \frac{1/4}{3}) = 1 - (\frac{2}{24} + \frac{2}{24}) = 1 - \frac{4}{24} = 1 - \frac{1}{6} = \frac{5}{6}$

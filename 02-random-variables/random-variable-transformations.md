# Random Variable Transformations

[← Back to Course README](../README.md)

- [D.R.V (Discrete Case)](#drv-discrete-case)
  - [Question 28: Discrete Linear Transformation PMF](#question-28-discrete-linear-transformation-pmf)
  - [Question 29: Exponential Power Series Transformation](#question-29-exponential-power-series-transformation)
- [C.R.V (Continuous Case) - The CDF Method](#crv-continuous-case---the-cdf-method)
  - [Question 30: Continuous Quadratic Transformation PDF](#question-30-continuous-quadratic-transformation-pdf)
  - [Question 31: Piecewise Linear Continuous Transformation](#question-31-piecewise-linear-continuous-transformation)
  - [Question 32: Linear Function PDF Transformation](#question-32-linear-function-pdf-transformation)
  - [Question 33: Monotonic Function Transformation](#question-33-monotonic-function-transformation)
  - [Question 34: Standard Normal to Log-Normal Transformation](#question-34-standard-normal-to-log-normal-transformation)
  - [Question 35: Inverse CDF Transformation](#question-35-inverse-cdf-transformation)
- [C.R.V (Continuous Case) - The Monotonic Transformation Method](#crv-continuous-case---the-monotonic-transformation-method)
- [Theorem for Monotonic Functions](#theorem-for-monotonic-functions)
- [Example 1: Linear Transformation](#example-1-linear-transformation)
- [Example 2: Exponential Transformation](#example-2-exponential-transformation)
- [Example 3: Squaring Transformation](#example-3-squaring-transformation)

> **Topic**: Random Variable Transformations: D.R.V (Discrete Case), C.R.V (Continuous Case) - The CDF Method, C.R.V (Continuous Case) - The Monotonic Transformation Method, Theorem for Monotonic Functions

---

## D.R.V (Discrete Case)

Let $x$ be a discrete random variable (d.r.v) and let $y = H(X)$ be a function of $x$. Then Y is also a d.r.v.
If $x_1, x_2, \dots, x_n$ are the possible values of X with probabilities $p(x_i) = P[X=x_i]$, the probability distribution of Y can be found as follows:
1.  Find the possible values $y_j$ of Y by applying the function H to each possible value of X.
2.  For each possible value $y_j$, identify the set of all $x_i$ such that $H(x_i) = y_j$.
3.  The probability of $Y=y_j$, denoted $q(y_j)$, is the sum of the probabilities of all such $x_i$.
    $q(y_j) = P[Y=y_j] = \sum_{i \text{ s.t. } H(x_i)=y_j} p(x_i)$


---

### Question 28: Discrete Linear Transformation PMF

> Let X be a d.r.v that assumes the 3 values: -1, 0, 1 with the probabilities $\frac{1}{3}, \frac{1}{2}$ and $\frac{1}{6}$ respectively.
> Find the probability distribution for:
> (i) $Y = 3X + 1$
> (ii) $Y = X^2$
>
> **Answer**
>
> **(i) For Y = 3X + 1**
>
> *   **Concept:** We apply the transformation $Y = 3X + 1$ to each value of X to find the possible values of Y. Then, we map the probabilities.
>
> *   **Step 1: Find the possible values of Y.**
> *   If $X = -1$, then $Y = 3(-1) + 1 = -2$.
> *   If $X = 0$, then $Y = 3(0) + 1 = 1$.
> *   If $X = 1$, then $Y = 3(1) + 1 = 4$.
> The possible values for Y are $\{-2, 1, 4\}$.
>
> *   **Step 2: Find the probabilities for each value of Y.**
> *   $P(Y = -2) = P(X = -1) = \frac{1}{3}$.
> *   $P(Y = 1) = P(X = 0) = \frac{1}{2}$.
> *   $P(Y = 4) = P(X = 1) = \frac{1}{6}$.
>
> *   **Probability Distribution of Y:**
>
> | $y_j$ | -2 | 1 | 4 |
> | :--- | :---: | :-: | :-: |
> | $q(y_j)$ | $\frac{1}{3}$ | $\frac{1}{2}$ | $\frac{1}{6}$ |
>
> **(ii) For Y = X^2**
>
> *   **Concept:** We apply the transformation $Y = X^2$. Note that multiple values of X can map to the same value of Y.
>
> *   **Step 1: Find the possible values of Y.**
> *   If $X = -1$, then $Y = (-1)^2 = 1$.
> *   If $X = 0$, then $Y = (0)^2 = 0$.
> *   If $X = 1$, then $Y = (1)^2 = 1$.
> The possible values for Y are $\{0, 1\}$.
>
> *   **Step 2: Find the probabilities for each value of Y.**
> *   For $Y=0$: This only happens if $X=0$. So, $P(Y=0) = P(X=0) = \frac{1}{2}$.
> *   For $Y=1$: This happens if $X=-1$ or $X=1$. We sum their probabilities.
> $P(Y=1) = P(X=-1) + P(X=1) = \frac{1}{3} + \frac{1}{6} = \frac{2}{6} + \frac{1}{6} = \frac{3}{6} = \frac{1}{2}$.
>
> *   **Probability Distribution of Y:**
>
> | $y_j$ | 0 | 1 |
> | :--- | :-: | :-: |
> | $q(y_j)$ | $\frac{1}{2}$ | $\frac{1}{2}$ |
>
>
>
> ---


### Question 29: Exponential Power Series Transformation

> Let the RV X have the possible values $1, 2, \dots, n, \dots$. Suppose $P[X=n] = \frac{1}{2^n}$.
> Let $Y = 1$ if X is even, and $Y = -1$ if X is odd. Find the probability distribution of Y.
>
> **Answer**
>
> *   **Concept:** This is an infinite discrete distribution. We need to find the total probability for two cases: Y=1 (X is even) and Y=-1 (X is odd). This involves summing an infinite geometric series. The formula for the sum of an infinite geometric series is $S = \frac{a}{1-r}$, where \'a\' is the first term and \'r\' is the common ratio, provided $|r|<1$.
>
> *   **Step 1: Find the probability for Y = 1 (X is even).**
> $P(Y=1) = P(X \text{ is even}) = P(X=2) + P(X=4) + P(X=6) + \dots$
> $P(Y=1) = \frac{1}{2^2} + \frac{1}{2^4} + \frac{1}{2^6} + \dots$
> This is a geometric series with first term $a = \frac{1}{4}$ and common ratio $r = \frac{1}{4}$.
> $P(Y=1) = \frac{\frac{1}{4}}{1 - \frac{1}{4}} = \frac{\frac{1}{4}}{\frac{3}{4}} = \frac{1}{3}$.
>
> *   **Step 2: Find the probability for Y = -1 (X is odd).**
> $P(Y=-1) = P(X \text{ is odd}) = P(X=1) + P(X=3) + P(X=5) + \dots$
> $P(Y=-1) = \frac{1}{2^1} + \frac{1}{2^3} + \frac{1}{2^5} + \dots$
> This is a geometric series with first term $a = \frac{1}{2}$ and common ratio $r = \frac{1}{4}$.
> $P(Y=-1) = \frac{\frac{1}{2}}{1 - \frac{1}{4}} = \frac{\frac{1}{2}}{\frac{3}{4}} = \frac{2}{3}$.
>
> *   **Probability Distribution of Y:**
>
> | $y_j$ | -1 | 1 |
> | :--- | :-: | :-: |
> | $p(y_j)$ | $\frac{2}{3}$ | $\frac{1}{3}$ |
>
>
>
> ---


## C.R.V (Continuous Case) - The CDF Method

Let X be a continuous random variable (c.r.v) with PDF $f(x)$, and let $Y = H(X)$ be a function of X. The general procedure to find the PDF of Y, $g(y)$, is:

1.  **Find the CDF of Y:** Find $G(y) = P(Y  y)$. To do this, express the event $Y  y$ in terms of an equivalent event for X.
2.  **Integrate:** Calculate $G(y)$ by integrating the PDF of X, $f(x)$, over the region defined in the previous step.
3.  **Differentiate:** The PDF of Y is then found by differentiating its CDF: $g(y) = \frac{dG(y)}{dy}$.
4.  **Find the Support:** Determine the range of possible values for Y (the \"support\" of the distribution).


---

### Question 30: Continuous Quadratic Transformation PDF

> Let X be a c.r.v with PDF $f(x) = \begin{cases} 2x & 0 < x < 1 \\ 0 & \text{otherwise} \end{cases}$.
> Let $H(X) = 3X + 1$. Find the PDF of $Y = H(X)$.
>
> **Answer**
>
> *   **Concept:** We will use the CDF method described above.
>
> *   **Step 1: Find the support of Y.**
> Since X is defined on $(0, 1)$, the values of Y will be on $(3(0)+1, 3(1)+1) = (1, 4)$.
>
> *   **Step 2: Find the CDF of Y, G(y).**
> For any y in $(1, 4)$:
> $G(y) = P(Y  y) = P(3X + 1  y) = P(3X  y-1) = P(X  \frac{y-1}{3})$.
> To find this probability, we integrate the PDF of X from 0 up to $\frac{y-1}{3}$.
> $G(y) = \int_{0}^{\frac{y-1}{3}} 2x \,dx = [x^2]_{0}^{\frac{y-1}{3}} = (\frac{y-1}{3})^2 = \frac{(y-1)^2}{9}$.
>
> *   **Step 3: Differentiate G(y) to find the PDF of Y, g(y).**
> $g(y) = \frac{dG(y)}{dy} = \frac{d}{dy} \left( \frac{(y-1)^2}{9} \right) = \frac{2(y-1)}{9}$.
>
> *   **Step 4: State the final PDF.**
> The PDF of Y is:
> $g(y) = \begin{cases} \frac{2(y-1)}{9} & 1 < y < 4 \\ 0 & \text{otherwise} \end{cases}$
>
>
>
> ---


### Question 31: Piecewise Linear Continuous Transformation

> Suppose that X is uniformly distributed over the interval $(-1,1)$. A function Y is defined as $Y = (\frac{}{2} x)$. Find the PDF of Y.
>
> **Answer**
>
> *   **Concept:** The function $Y = (\frac{}{2} x)$ is strictly increasing (monotonic) on the interval $(-1, 1)$. We can use the CDF method. The PDF for X is $f(x) = \frac{1}{1 - (-1)} = \frac{1}{2}$ for $-1 < x < 1$.
>
> *   **Step 1: Find the support of Y.**
> As x varies from -1 to 1, $\frac{}{2}x$ varies from $-\frac{}{2}$ to $\frac{}{2}$.
> Therefore, $Y = (\frac{}{2} x)$ varies from $(-\frac{}{2}) = -1$ to $(\frac{}{2}) = 1$. The support of Y is $(-1, 1)$.
>
> *   **Step 2: Find the CDF of Y, G(y).**
> For any y in $(-1, 1)$:
> $G(y) = P(Y  y) = P((\frac{}{2} x)  y)$.
> Since $$ is invertible on this domain, we can apply $$ to both sides.
> $P(\frac{}{2} x  (y)) = P(x  \frac{2}{} (y))$.
> We now integrate the PDF of X:
> $G(y) = \int_{-1}^{\frac{2}{} (y)} \frac{1}{2} \,dx = \frac{1}{2} [x]_{-1}^{\frac{2}{} (y)} = \frac{1}{2} (\frac{2}{} (y) - (-1)) = \frac{1}{} (y) + \frac{1}{2}$.
>
> *   **Step 3: Differentiate G(y) to find the PDF of Y, g(y).**
> $g(y) = \frac{dG(y)}{dy} = \frac{d}{dy} \left( \frac{1}{} (y) + \frac{1}{2} \right) = \frac{1}{ \sqrt{1-y^2}}$.
>
> *   **Step 4: State the final PDF.**
> $g(y) = \begin{cases} \frac{1}{ \sqrt{1-y^2}} & -1 < y < 1 \\ 0 & \text{otherwise} \end{cases}$
>
>
> ---


### Question 32: Linear Function PDF Transformation

> A RV X has PDF $f(x) = \begin{cases} \frac{2x}{9} & 0 < x < 3 \\ 0 & \text{otherwise} \end{cases}$. Find the PDF of $Y = X^3$.
>
> **Answer**
>
> *   **Concept:** The function $Y=X^3$ is strictly increasing, so we can use the CDF method.
>
> *   **Step 1: Find the support of Y.**
> Since X is on $(0, 3)$, Y will be on $(0^3, 3^3) = (0, 27)$.
>
> *   **Step 2: Find the CDF of Y, G(y).**
> For any y in $(0, 27)$:
> $G(y) = P(Y  y) = P(X^3  y) = P(X  y^{1/3})$.
> $G(y) = \int_{0}^{y^{1/3}} \frac{2x}{9} \,dx = \frac{2}{9} [\frac{x^2}{2}]_{0}^{y^{1/3}} = \frac{1}{9} [(y^{1/3})^2 - 0] = \frac{y^{2/3}}{9}$.
>
> *   **Step 3: Differentiate G(y) to find the PDF of Y, g(y).**
> $g(y) = \frac{dG(y)}{dy} = \frac{d}{dy} (\frac{y^{2/3}}{9}) = \frac{1}{9} \cdot \frac{2}{3} y^{-1/3} = \frac{2}{27y^{1/3}}$.
>
> *   **Step 4: State the final PDF.**
> $g(y) = \begin{cases} \frac{2}{27y^{1/3}} & 0 < y < 27 \\ 0 & \text{otherwise} \end{cases}$
>
>
>
> ---


### Question 33: Monotonic Function Transformation

> Let X be a RV with PDF $f(x) = \frac{1}{}, \text{ for } -\frac{}{2} < x < \frac{}{2}$. Find the PDF of $Y = (x)$.
>
> **Answer**
>
> *   **Concept:** Since $Y = (X)$ is strictly monotonic on the given interval for X, we can use the shortcut formula: $g(y) = f_X(x) \left| \frac{dx}{dy} \right|$.
>
> *   **Step 1: Find x in terms of y and calculate the derivative.**
> $y = (x) ⇒ x = (y)$.
> $\frac{dx}{dy} = \frac{1}{1+y^2}$.
>
> *   **Step 2: Find the support of Y.**
> As x varies from $-\frac{}{2}$ to $\frac{}{2}$, $y = (x)$ varies from $-\infty$ to $\infty$.
>
> *   **Step 3: Apply the formula.**
> $g(y) = f_X((y)) \left| \frac{1}{1+y^2} \right|$.
> Since the PDF of X is a constant $\frac{1}{}$ on its domain, $f_X((y)) = \frac{1}{}$.
> $g(y) = \frac{1}{} \cdot \frac{1}{1+y^2}$.
>
> *   **Step 4: State the final PDF.**
> $g(y) = \frac{1}{(1+y^2)}$ for $-\infty < y < \infty$.
> (This is the PDF of a Cauchy distribution).
>
>
>
> ---


### Question 34: Standard Normal to Log-Normal Transformation

> Suppose that the radius R of a ball bearing is normally distributed with expected value 1 and variance 0.04. Find the PDF of the volume V.
>
> **Answer**
>
> *   **Concept:** This is another transformation of a continuous variable, $V = \frac{4}{3} R^3$. Since V is a strictly increasing function of R (for $R>0$), we can use the formula $g(v) = f_R(r) \left| \frac{dr}{dv} \right|$.
>
> *   **Step 1: Define the PDF of R.**
> Given $_R = 1$ and $_R^2 = 0.04$, so $_R = 0.2$.
> The PDF of R is $f_R(r) = \frac{1}{0.2\sqrt{2}} e^{-\frac{1}{2} \left(\frac{r-1}{0.2}\right)^2}$.
>
> *   **Step 2: Express r in terms of v and find the derivative.**
> $v = \frac{4}{3} r^3 ⇒ r^3 = \frac{3v}{4} ⇒ r = \left(\frac{3v}{4}\right)^{1/3}$.
> $\frac{dr}{dv} = \frac{1}{3} \left(\frac{3v}{4}\right)^{-2/3} \cdot \frac{3}{4} = \frac{1}{4} \left(\frac{3v}{4}\right)^{-2/3}$.
>
> *   **Step 3: Apply the transformation formula.**
> $g(v) = f_R\left(\left(\frac{3v}{4}\right)^{1/3}\right) \cdot \left| \frac{1}{4} \left(\frac{3v}{4}\right)^{-2/3} \right|$.
> Substitute the expressions for $f_R(r)$ and $\frac{dr}{dv}$:
> $g(v) = \frac{1}{0.2\sqrt{2}} e^{-\frac{1}{2} \left( \frac{(\frac{3v}{4})^{1/3} - 1}{0.2} \right)^2} \cdot \frac{1}{4} \left(\frac{3v}{4}\right)^{-2/3}$.
>
> *   **Step 4: Define the support of V.**
> Since R must be positive, V is also positive. The support is $v > 0$.
>
>
>
> ---


### Question 35: Inverse CDF Transformation

> Suppose X is uniformly distributed over $(-1,1)$. Find the PDF of $W = |X|$.
>
> **Answer**
>
> *   **Concept:** The function $W = |X|$ is not monotonic over the interval $(-1, 1)$, so we must use the CDF method. The PDF for X is $f(x) = \frac{1}{2}$ for $-1 < x < 1$.
>
> *   **Step 1: Find the support of W.**
> Since $X$ is in $(-1, 1)$, $W = |X|$ will be in $[0, 1)$.
>
> *   **Step 2: Find the CDF of W, G(w).**
> For any w in $[0, 1)$:
> $G(w) = P(W  w) = P(|X|  w) = P(-w  X  w)$.
> We integrate the PDF of X over this interval:
> $G(w) = \int_{-w}^{w} \frac{1}{2} \,dx = \frac{1}{2} [x]_{-w}^{w} = \frac{1}{2} (w - (-w)) = \frac{1}{2}(2w) = w$.
>
> *   **Step 3: Differentiate G(w) to find the PDF of W, g(w).**
> $g(w) = \frac{dG(w)}{dw} = \frac{d}{dw}(w) = 1$.
>
> *   **Step 4: State the final PDF.**
> $g(w) = \begin{cases} 1 & 0  w < 1 \\ 0 & \text{otherwise} \end{cases}$
> (This shows that W is uniformly distributed on $[0, 1)$).
>
>
>
> ---


## C.R.V (Continuous Case) - The Monotonic Transformation Method

When the function $Y=H(X)$ is strictly monotonic (either always increasing or always decreasing) and differentiable, there is a direct formula to find the PDF of Y.


---

## Theorem for Monotonic Functions

Let $X$ be a continuous random variable with PDF $f_X(x)$ where $f_X(x) > 0$ for $a < x < b$.
Let $Y = H(X)$ be a strictly monotonic and differentiable function of X.
The PDF of Y, $g_Y(y)$, is given by:

$g_Y(y) = f_X(x) \left| \frac{dx}{dy} \right|$

where $x$ is expressed in terms of $y$ (i.e., $x = H^{-1}(y)$).

1.  **Find the inverse function:** Solve $y = H(x)$ for $x$ to get $x = H^{-1}(y)$.
2.  **Calculate the Jacobian:** Find the derivative of the inverse function, $\frac{dx}{dy}$. The absolute value of this derivative is called the Jacobian of the transformation.
3.  **Substitute:** Replace $x$ in the original PDF $f_X(x)$ with its expression in terms of $y$, and multiply by the absolute value of the derivative.
4.  **Determine the support:** Find the range of Y values that correspond to the domain of X.


---

## Example 1: Linear Transformation

Suppose that $X$ is uniformly distributed on $(1, 3)$. Find the PDF of the random variable $Y = 3X + 1$.

*   **PDF of X:** $f_X(x) = \frac{1}{3-1} = \frac{1}{2}$ for $1 < x < 3$.

*   **Step 1: Find the inverse and derivative.**
    $y = 3x + 1 \implies x = \frac{y-1}{3}$.
    $\frac{dx}{dy} = \frac{1}{3}$. So, $\left| \frac{dx}{dy} \right| = \frac{1}{3}$.

*   **Step 2: Determine the support of Y.**
    If $x=1$, $y = 3(1)+1 = 4$.
    If $x=3$, $y = 3(3)+1 = 10$.
    So, the support of Y is $(4, 10)$.

*   **Step 3: Apply the formula.**
    $g_Y(y) = f_X(\frac{y-1}{3}) \left| \frac{dx}{dy} \right| = \frac{1}{2} \cdot \frac{1}{3} = \frac{1}{6}$.

*   **Final PDF:**
    $g_Y(y) = \begin{cases} \frac{1}{6} & 4 < y < 10 \\ 0 & \text{otherwise} \end{cases}$


---

## Example 2: Exponential Transformation

Let X be a c.r.v with PDF $f(x) = \begin{cases} 2x & 0 < x < 1 \\ 0 & \text{otherwise} \end{cases}$. Find the PDF of $Y = e^X$.

*   **Step 1: Find the inverse and derivative.**
    $y = e^x \implies x = \ln(y)$.
    $\frac{dx}{dy} = \frac{1}{y}$. Since the support of Y will be positive, $\left| \frac{dx}{dy} \right| = \frac{1}{y}$.

*   **Step 2: Determine the support of Y.**
    If $x=0$, $y = e^0 = 1$.
    If $x=1$, $y = e^1 = e$.
    The support of Y is $(1, e)$.

*   **Step 3: Apply the formula.**
    $g_Y(y) = f_X(\ln(y)) \left| \frac{dx}{dy} \right| = 2(\ln(y)) \cdot \frac{1}{y} = \frac{2\ln(y)}{y}$.

*   **Final PDF:**
    $g_Y(y) = \begin{cases} \frac{2\ln(y)}{y} & 1 < y < e \\ 0 & \text{otherwise} \end{cases}$


---

## Example 3: Squaring Transformation

Suppose that c.r.v $X$ has PDF $f(x) = e^{-x}$ for $x > 0$. Find the PDF of $Y = X^2$.

*   **Note:** For $x>0$, the function $Y=X^2$ is strictly increasing.

*   **Step 1: Find the inverse and derivative.**
    $y = x^2 \implies x = \sqrt{y}$ (since $x>0$).
    $\frac{dx}{dy} = \frac{1}{2\sqrt{y}}$.

*   **Step 2: Determine the support of Y.**
    If $x \to 0$, $y \to 0$.
    If $x \to \infty$, $y \to \infty$.
    The support of Y is $y > 0$.

*   **Step 3: Apply the formula.**
    $g_Y(y) = f_X(\sqrt{y}) \left| \frac{dx}{dy} \right| = e^{-\sqrt{y}} \cdot \frac{1}{2\sqrt{y}}$.

*   **Final PDF:**
    $g_Y(y) = \begin{cases} \frac{e^{-\sqrt{y}}}{2\sqrt{y}} & y > 0 \\ 0 & \text{otherwise} \end{cases}$

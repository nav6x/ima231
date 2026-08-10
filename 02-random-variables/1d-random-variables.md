# 1D Random Variables

[← Back to Course README](../README.md)

- [Types of Random Variables](#types-of-random-variables)
- [Mean, Variance, and Standard Deviation](#mean-variance-and-standard-deviation)
- [Cumulative Distribution Function (CDF)](#cumulative-distribution-function-cdf)
- [Questions and Answers (Random Variables)](#questions-and-answers-random-variables)
  - [Question 12: Probability Function Table](#question-12-probability-function-table)
  - [Question 13: Dice Throw Expectation and Variance](#question-13-dice-throw-expectation-and-variance)
  - [Question 14: Continuous Random Variable Expectation and Variance](#question-14-continuous-random-variable-expectation-and-variance)
  - [Question 15: Quadratic PDF Expectation and Variance](#question-15-quadratic-pdf-expectation-and-variance)
  - [Question 16: Rayleigh/Exponential-type PDF](#question-16-rayleighexponential-type-pdf)
  - [Question 17: Piecewise Continuous CDF](#question-17-piecewise-continuous-cdf)
- [Two-Dimensional Random Variables](#two-dimensional-random-variables)

> **Topic**: 1D Random Variables: Types of Random Variables, Mean, Variance, and Standard Deviation, Cumulative Distribution Function (CDF), Questions and Answers (Random Variables)

---

## Types of Random Variables

- **Discrete Random Variable (DRV):** If the possible values of a random variable $X$ are finite or countably infinite.
  - **Probability Mass Function (PMF):** The probability associated with every outcome $x_i$ is denoted by $P[X=x_i] = p(x_i)$.
    - $\sum p(x_i) = 1$

-   **Continuous Random Variable (CRV):** If the possible values of a random variable are given in ranges (e.g., $a < x < b$).
  -   **Probability Density Function (PDF):** Let $X$ be a continuous random variable with probability function $f(x)$ such that:
    1. $f(x) \ge 0$
    2. $\int_{-\infty}^{\infty} f(x)dx = 1$


---

## Mean, Variance, and Standard Deviation

-   **Mean (Expectation):**
  -   For a DRV: $E(X) = \sum x_i \cdot p(x_i)$
  -   For a CRV: $E(X) = \int_{-\infty}^{\infty} x \cdot f(x)dx$

-   **Variance:**
  -   $V(X) = E[(X - E(X))^2]$
  -   **Derivation:** $V(X) = E[X^2 - 2XE(X) + (E(X))^2] = E(X^2) - 2E(X)E(X) + (E(X))^2 = E(X^2) - [E(X)]^2$

-   **Standard Deviation:**
  -   $SD, \sigma = \sqrt{V(X)}$

-   **Properties:**
  -   If $X=c$ (a constant), then $E(X) = c$.
  -   **$E(ax+b) = aE(x) + b$**
    -   **Proof:** $E(ax+b) = \int_{-\infty}^{\infty} (ax+b)f(x)dx = a\int_{-\infty}^{\infty} xf(x)dx + b\int_{-\infty}^{\infty} f(x)dx = aE(x) + b$
  -   **$V(ax+b) = a^2V(x)$**
    -   **Proof:** $V(ax+b) = E[(ax+b) - E(ax+b)]^2 = E[ax+b - (aE(x)+b)]^2 = E[a(x-E(x))]^2 = a^2E[(x-E(x))^2] = a^2V(x)$


---

## Cumulative Distribution Function (CDF)

-   Let $X$ be a random variable, then the CDF $F(x) = P[X \le x]$.
  -   For a DRV: $F(x) = \sum_{x_i \le x} p(x_i)$
  -   For a CRV: $F(x) = \int_{-\infty}^{x} f(u)du$
-   **Note:** For a continuous random variable, the probability at a specific point is zero. $P[X=a] = 0$.


---

## Questions and Answers (Random Variables)


---

### Question 12: Probability Function Table

> The PF of RV X is given by the table:
>
> | x    | 0   | 1   | 2   | 3   | 4   | 5    | 6    |
> | ---- | --- | --- | --- | --- | --- | ---- | ---- |
> | p(x) | k   | 3k  | 5k  | 7k  | 9k  | 11k  | 13k  |
>
> (i) Find k. (ii) $P(X<4)$ (iii) $P(X \ge 5)$ (iv) $P(3 < X \le 6)$
> -   **Answer:**
> **(i) Find the value of k**
> *   **Concept:** For a valid discrete probability distribution, the sum of all probabilities for all possible outcomes must equal 1.
> *   **Step 1: Sum all probabilities in terms of k.**
> $P(X=0) + P(X=1) + \dots + P(X=6) = 1$
> $k + 3k + 5k + 7k + 9k + 11k + 13k = 1$
> *   **Step 2: Solve the equation for k.**
> $49k = 1 \implies k = \frac{1}{49}$
>
> **(ii) Find $P(X < 4)$**
> *   **Concept:** This is the probability that X takes on any of the values less than 4, which are 0, 1, 2, and 3.
> *   **Step 1: Sum the probabilities for the required values.**
> $P(X < 4) = P(X=0) + P(X=1) + P(X=2) + P(X=3)$
> $P(X < 4) = k + 3k + 5k + 7k = 16k$
> *   **Step 2: Substitute the value of k.**
> $P(X < 4) = 16 \times \frac{1}{49} = \frac{16}{49}$
>
> **(iii) Find $P(X \ge 5)$**
> *   **Concept:** This is the probability that X is 5 or 6.
> *   **Step 1: Sum the probabilities for the required values.**
> $P(X \ge 5) = P(X=5) + P(X=6) = 11k + 13k = 24k$
> *   **Step 2: Substitute the value of k.**
> $P(X \ge 5) = 24 \times \frac{1}{49} = \frac{24}{49}$
>
> **(iv) Find $P(3 < X \le 6)$**
> *   **Concept:** This is the probability that X is greater than 3 but less than or equal to 6, which includes the values 4, 5, and 6.
> *   **Step 1: Sum the probabilities for the required values.**
> $P(3 < X \le 6) = P(X=4) + P(X=5) + P(X=6) = 9k + 11k + 13k = 33k$
> *   **Step 2: Substitute the value of k.**
> $P(3 < X \le 6) = 33 \times \frac{1}{49} = \frac{33}{49}$
>
>
> ---


### Question 13: Dice Throw Expectation and Variance

> A pair of dice is thrown. RV X is the sum of numbers. Find the expectation and variance.
> -   **Answer:**
> *   **Concept:** We first need to establish the probability distribution for the sum of two dice. Then we use the formulas for expectation and variance.
> *   Expectation: $E[X] = \sum x_i p(x_i)$
> *   Variance: $V(X) = E[X^2] - (E[X])^2$
> *   **Step 1: Determine the probability distribution of the sum X.**
> The total number of outcomes is $6 \times 6 = 36$. The possible sums (X) range from 2 to 12.
> *   $P(X=2) = 1/36$ {(1,1)}
> *   $P(X=3) = 2/36$ {(1,2), (2,1)}
> *   $P(X=4) = 3/36$
> *   $P(X=5) = 4/36$
> *   $P(X=6) = 5/36$
> *   $P(X=7) = 6/36$
> *   $P(X=8) = 5/36$
> *   $P(X=9) = 4/36$
> *   $P(X=10) = 3/36$
> *   $P(X=11) = 2/36$
> *   $P(X=12) = 1/36$
> *   **Step 2: Calculate the Expectation, E[X].**
> $E[X] = \sum x_i p(x_i)$
> $E[X] = (2 \cdot \frac{1}{36}) + (3 \cdot \frac{2}{36}) + (4 \cdot \frac{3}{36}) + (5 \cdot \frac{4}{36}) + (6 \cdot \frac{5}{36}) + (7 \cdot \frac{6}{36}) + (8 \cdot \frac{5}{36}) + (9 \cdot \frac{4}{36}) + (10 \cdot \frac{3}{36}) + (11 \cdot \frac{2}{36}) + (12 \cdot \frac{1}{36})$
> $E[X] = \frac{1}{36}(2+6+12+20+30+42+40+36+30+22+12) = \frac{252}{36} = 7$
> *   **Step 3: Calculate E[X^2].**
> $E[X^2] = \sum x_i^2 p(x_i)$
> $E[X^2] = (2^2 \cdot \frac{1}{36}) + (3^2 \cdot \frac{2}{36}) + \dots + (12^2 \cdot \frac{1}{36})$
> $E[X^2] = \frac{1}{36}(4 \cdot 1 + 9 \cdot 2 + 16 \cdot 3 + 25 \cdot 4 + 36 \cdot 5 + 49 \cdot 6 + 64 \cdot 5 + 81 \cdot 4 + 100 \cdot 3 + 121 \cdot 2 + 144 \cdot 1)$
> $E[X^2] = \frac{1}{36}(4+18+48+100+180+294+320+324+300+242+144) = \frac{1974}{36} \approx 54.833$
> *   **Step 4: Calculate the Variance, V(X).**
> $V(X) = E[X^2] - (E[X])^2 = 54.833 - 7^2 = 54.833 - 49 = 5.833$
>
>
> ---


### Question 14: Continuous Random Variable Expectation and Variance

> Let X be a continuous RV with PDF:
> $f(x) = \begin{cases} 2x^{-2} & 1 < x < 2 \\ 0 & \text{otherwise} \end{cases}$
> Find E(X) and V(X).
> -   **Answer:**
> *   **Step 1: Calculate the Expectation, E(X).**
> $E(X) = \int_{-\infty}^{\infty} x \cdot f(x) dx = \int_1^2 x(2x^{-2})dx = \int_1^2 2x^{-1}dx$
> $E(X) = [2\ln|x|]_1^2 = 2\ln(2) - 2\ln(1) = 2\ln(2) - 0 \approx 1.386$
> *   **Step 2: Calculate E(X^2).**
> $E(X^2) = \int_{-\infty}^{\infty} x^2 \cdot f(x) dx = \int_1^2 x^2(2x^{-2})dx = \int_1^2 2dx$
> $E(X^2) = [2x]_1^2 = 2(2) - 2(1) = 4-2=2$
> *   **Step 3: Calculate the Variance, V(X).**
> $V(X) = E(X^2) - [E(X)]^2 = 2 - (2\ln(2))^2 \approx 2 - (1.386)^2 \approx 2 - 1.921 = 0.079$
>
>
> ---


### Question 15: Quadratic PDF Expectation and Variance

> Find E(X) and V(X) of the function pdf:
> $f(x) = \begin{cases} 6x(1-x) & 0 \le x \le 1 \\ 0 & \text{otherwise} \end{cases}$
> -   **Answer:**
> *   **Step 1: Calculate the Expectation, E(X).**
> $E(X) = \int_0^1 x \cdot [6x(1-x)] dx = \int_0^1 (6x^2 - 6x^3)dx$
> $E(X) = [2x^3 - \frac{6}{4}x^4]_0^1 = [2x^3 - \frac{3}{2}x^4]_0^1$
> $E(X) = (2(1)^3 - \frac{3}{2}(1)^4) - 0 = 2 - 1.5 = 0.5$
> *   **Step 2: Calculate E(X^2).**
> $E(X^2) = \int_0^1 x^2 \cdot [6x(1-x)] dx = \int_0^1 (6x^3 - 6x^4)dx$
> $E(X^2) = [\frac{6}{4}x^4 - \frac{6}{5}x^5]_0^1 = [\frac{3}{2}x^4 - \frac{6}{5}x^5]_0^1$
> $E(X^2) = (\frac{3}{2}(1)^4 - \frac{6}{5}(1)^5) - 0 = 1.5 - 1.2 = 0.3$
> *   **Step 3: Calculate the Variance, V(X).**
> $V(X) = E(X^2) - [E(X)]^2 = 0.3 - (0.5)^2 = 0.3 - 0.25 = 0.05$
>
>
> ---


### Question 16: Rayleigh/Exponential-type PDF

> Find the mean and variance for the pdf: $f(x) = \begin{cases} xe^{-x^2/2} & x > 0 \\ 0 & \text{otherwise} \end{cases}$
> -   **Answer:**
> *   **Concept:** This problem requires advanced integration techniques, specifically using a substitution that leads to the Gamma function, $\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt$.
> *   **Step 1: Calculate the Mean, E(X).**
> $E(X) = \int_0^\infty x(xe^{-x^2/2})dx = \int_0^\infty x^2e^{-x^2/2}dx$.
> Let $t = x^2/2$. Then $x = \sqrt{2t}$ and $dx = \frac{1}{\sqrt{2t}}dt$.
> $E(X) = \int_0^\infty (2t)e^{-t}\frac{1}{\sqrt{2t}}dt = \sqrt{2}\int_0^\infty t^{1/2}e^{-t}dt$
> This is $\sqrt{2} \cdot \Gamma(3/2)$. Using the property $\Gamma(z+1)=z\Gamma(z)$ and $\Gamma(1/2)=\sqrt{\pi}$:
> $E(X) = \sqrt{2} \cdot (\frac{1}{2}\Gamma(\frac{1}{2})) = \sqrt{2} \cdot \frac{\sqrt{\pi}}{2} = \sqrt{\frac{\pi}{2}}$.
> *   **Step 2: Calculate E(X^2).**
> $E(X^2) = \int_0^\infty x^2(xe^{-x^2/2})dx = \int_0^\infty x^3e^{-x^2/2}dx$.
> Using the same substitution $t = x^2/2$:
> $E(X^2) = \int_0^\infty (2t)^{3/2} e^{-t} \frac{1}{\sqrt{2t}}dt = \int_0^\infty 2t e^{-t} dt$
> This is $2 \cdot \Gamma(2)$. Since $\Gamma(n)=(n-1)!$ for integer n, $\Gamma(2)=1! = 1$.
> $E(X^2) = 2 \cdot 1 = 2$.
> *   **Step 3: Calculate the Variance, V(X).**
> $V(X) = E(X^2) - [E(X)]^2 = 2 - (\sqrt{\frac{\pi}{2}})^2 = 2 - \frac{\pi}{2}$.
>
>
> ---


### Question 17: Piecewise Continuous CDF

> Find the CDF of the RV X given the PDF:
> $f(x) = \begin{cases} ax & 0 < x < 1 \\ a & 1 \le x < 2 \\ -ax+3a & 2 \le x < 3 \\ 0 & \text{otherwise} \end{cases}$
> -   **Answer:**
> *   **Step 1: Find the value of 'a'.**
> For $f(x)$ to be a valid PDF, its total integral must be 1.
> $\int_0^1 ax dx + \int_1^2 a dx + \int_2^3 (-ax+3a)dx = 1$
> $[\frac{ax^2}{2}]_0^1 + [ax]_1^2 + [-\frac{ax^2}{2}+3ax]_2^3 = 1$
> $(\frac{a}{2} - 0) + (2a-a) + ((-\frac{9a}{2}+9a) - (-\frac{4a}{2}+6a)) = 1$
> $\frac{a}{2} + a + (\frac{9a}{2} - 4a) = 1$
> $\frac{3a}{2} + \frac{a}{2} = 1 \implies \frac{4a}{2} = 1 \implies 2a=1 \implies a=\frac{1}{2}$.
> *   **Step 2: Calculate the CDF, F(x), for each interval.**
> The CDF is $F(x) = \int_{-\infty}^x f(t)dt$.
> *   **For $x < 0$**: $F(x) = \int_{-\infty}^x 0 dt = 0$.
> *   **For $0 \le x < 1$**: $F(x) = \int_0^x \frac{1}{2}t dt = [\frac{t^2}{4}]_0^x = \frac{x^2}{4}$.
> *   **For $1 \le x < 2$**: $F(x) = F(1) + \int_1^x \frac{1}{2} dt = \frac{1^2}{4} + [\frac{t}{2}]_1^x = \frac{1}{4} + \frac{x}{2} - \frac{1}{2} = \frac{2x-1}{4}$.
> *   **For $2 \le x < 3$**: $F(x) = F(2) + \int_2^x (-\frac{1}{2}t+\frac{3}{2}) dt = \frac{2(2)-1}{4} + [-\frac{t^2}{4}+\frac{3t}{2}]_2^x = \frac{3}{4} + (-\frac{x^2}{4}+\frac{3x}{2}) - (-1+3) = \frac{-x^2+6x-5}{4}$.
> *   **For $x \ge 3$**: $F(x) = F(3) = \frac{-(3^2)+6(3)-5}{4} = \frac{-9+18-5}{4} = \frac{4}{4} = 1$.
> *   **Step 3: Combine the pieces into the final CDF.**
> $F(x) = \begin{cases} 0 & x<0 \\ \frac{x^2}{4} & 0 \le x < 1 \\ \frac{2x-1}{4} & 1 \le x < 2 \\ \frac{-x^2+6x-5}{4} & 2 \le x < 3 \\ 1 & x \ge 3 \end{cases}$
>
> **Team Question 15:** Calculate CDF for $f(x) = 6x(1-x)$ for $0 \le x \le 1$.
> -   **Answer:**
> *   **Concept:** The Cumulative Distribution Function (CDF), $F(x)$, is the integral of the PDF from the beginning of its domain up to a variable *x*.
> *   **Formula:** $F(x) = P(X \le x) = \int_{-\infty}^x f(t) dt$
> *   **Step 1: Handle the region before the domain ($x < 0$).**
> For any value of x less than 0, the PDF $f(x)$ is 0.
> $F(x) = \int_{-\infty}^{x} 0 dt = 0$
> *   **Step 2: Integrate within the domain ($0 \le x \le 1$).**
> For values of x in this interval, we integrate the PDF from 0 up to x.
> $F(x) = \int_{-\infty}^{x} f(t)dt = \int_{-\infty}^{0} 0 dt + \int_{0}^{x} 6t(1-t)dt$
> $F(x) = 0 + \int_{0}^{x} (6t - 6t^2)dt$
> $F(x) = \left[ 3t^2 - 2t^3 \right]_{0}^{x}$
> $F(x) = (3x^2 - 2x^3) - (0) = 3x^2 - 2x^3$
> *   **Step 3: Handle the region after the domain ($x > 1$).**
> For any value of x greater than 1, the CDF is the total accumulated probability, which must be 1. We can verify this by calculating F(1).
> $F(1) = 3(1)^2 - 2(1)^3 = 3 - 2 = 1$.
> *   **Step 4: Combine the cases into the final CDF definition.**
> $F(x) = \begin{cases} 0 & x<0 \\ 3x^2-2x^3 & 0 \le x \le 1 \\ 1 & x>1 \end{cases}$
>
>
>
>
> ---


## Two-Dimensional Random Variables

-   **Definition:** Let 'E' be an experiment and 'S' a sample space. Let X=X(s) and Y=Y(s) be two functions, each assigning a real number to each outcome $s \in S$. We call (X,Y) a two-dimensional random variable.
-   *Example: A: No. of heads, B: No. appearing on a die is even.*

-   **Joint PMF (Discrete):**
  -   $p(x_i, y_j) = P[X=x_i, Y=y_j]$
  -   $\sum_{i}\sum_{j} p(x_i, y_j) = 1$

-   **Joint PDF (Continuous):**
  -   $f(x,y)$ is the PDF notation (Joint PDF).
  -   $\int_{-\infty}^{\infty}\int_{-\infty}^{\infty} f(x,y)dxdy = 1$

-   **Expectation (Mean) for 2D DRV:**
  -   $E(XY) = \sum_i \sum_j (x_i y_j) p(x_i, y_j)$

-   **Marginal PMF/PDF:**
  -   **Discrete:**
    -   $p(x_i) = \sum_j p(x_i, y_j)$
    -   $q(y_j) = \sum_i p(x_i, y_j)$
  -   **Continuous:**
    -   $g(x) = \int_{-\infty}^{\infty} f(x,y)dy$
    -   $h(y) = \int_{-\infty}^{\infty} f(x,y)dx$

-   **Note on Independence:** If X and Y are independent, then the joint pdf is the product of the marginal pdfs: $f(x,y) = g(x)h(y)$. However, if $f(x,y) = g(x)h(y)$, it does not necessarily mean that X and Y are independent random variables.

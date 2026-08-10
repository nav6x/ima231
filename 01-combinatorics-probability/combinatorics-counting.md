# Combinatorics & Counting

[← Back to Course README](../README.md)

- [Definitions](#definitions)
- [Questions and Answers (Permutations & Combinations)](#questions-and-answers-permutations-combinations)
  - [Question 1: License Plates](#question-1-license-plates)
    - [Solution](#solution)
  - [Question 2: Distinguishable Words from "MISSISSIPPI"](#question-2-distinguishable-words-from-mississippi)
  - [Question 3: Selecting Shoes](#question-3-selecting-shoes)
  - [Question 4: National Flag](#question-4-national-flag)
- [Advanced Combinatorics](#advanced-combinatorics)
- [1. Binomial Identities](#1-binomial-identities)
    - [Core Identities](#core-identities)
- [2. Generating Functions](#2-generating-functions)
    - [Standard Generating Function Models](#standard-generating-function-models)
    - [Calculating Coefficients of Generating Functions](#calculating-coefficients-of-generating-functions)
- [3. Partitions of Integers](#3-partitions-of-integers)
    - [Generating Function for Partitions](#generating-function-for-partitions)
- [4. Exponential Generating Functions (EGFs)](#4-exponential-generating-functions-egfs)
    - [Standard EGF Models](#standard-egf-models)

> **Topic**: Combinatorics & Counting: Definitions, Questions and Answers (Permutations & Combinations), Advanced Combinatorics, 1. Binomial Identities

---

## Definitions

-   **Permutation Definition:** Arrangement of 'n' objects taken 'r' at a time without any repetition.
-   **Arrangement with Repetition:** Arrangement of 'n' objects taken 'r' at a time with repetition allowed is $n^r$.

-   **Permutation with multiple types of objects:**
  -   Suppose there are 'n' objects where $n_1$ is of one type, $n_2$ is of another type, ..., and $n_r$ is of the r-th type, then:
    -   $nPr = \frac{n!}{n_1!n_2!\dots n_r!}$

-   **Combination Definition:** Combination of 'n' objects taken 'r' at a time (order is not important).
  -   $nCr = \frac{n!}{(n-r)!r!}$


---

## Questions and Answers (Permutations & Combinations)


---

### Question 1: License Plates

> A license plate has two letters and 4 digits with the first digit $\ne$ 0. How many different license plates can be made if:
> i) all are distinct
> ii) repetition allowed

#### Solution

**Concept:** This problem uses the **Fundamental Counting Principle**. This principle states that if there are *m* ways to do one thing and *n* ways to do another, then there are $m \times n$ ways of doing both. We calculate the number of choices for each position on the plate and multiply them together.

**i) All characters are distinct (no repetition)**

*   **Step 1: First Letter:** There are 26 possible letters (A-Z).
    *   *Choices: 26*
*   **Step 2: Second Letter:** Since we cannot repeat the first letter, there are 25 letters remaining.
    *   *Choices: 25*
*   **Step 3: First Digit:** The digits are 0-9, but the first digit cannot be 0. So, there are 9 choices (1-9).
    *   *Choices: 9*
*   **Step 4: Second Digit:** We can now use 0. There were 10 digits, and we've used one, so there are 9 choices left.
    *   *Choices: 9*
*   **Step 5: Third Digit:** We have used two digits, so there are 8 choices left.
    *   *Choices: 8*
*   **Step 6: Fourth Digit:** We have used three digits, so there are 7 choices left.
    *   *Choices: 7*
*   **Final Calculation:** Multiply the choices for each position.
    $26 \times 25 \times 9 \times 9 \times 8 \times 7 = 2,948,400$

**ii) Repetition is allowed**

*   **Step 1: First Letter:** 26 choices.
*   **Step 2: Second Letter:** 26 choices (repetition is allowed).
*   **Step 3: First Digit:** 9 choices (1-9).
*   **Step 4: Second, Third, and Fourth Digits:** 10 choices for each position (0-9).
*   **Final Calculation:**
    $26 \times 26 \times 9 \times 10 \times 10 \times 10 = 6,084,000$


---

### Question 2: Distinguishable Words from "MISSISSIPPI"

> Find the number of distinguishable words that can be formed from the letters of "MISSISSIPPI".

#### Solution

**Concept:** This is a **Permutation with Repetitions** problem. When arranging items where some are identical, the total number of unique arrangements is the factorial of the total number of items divided by the factorial of the number of repetitions for each unique item.

*   **Formula:** $\frac{n!}{n_1! n_2! \dots n_k!}$
    *   Where *n* is the total number of items.
    *   $n_1, n_2, \dots$ are the counts of each repeated item.

*   **Step 1: Count the total letters (n):**
    *   MISSISSIPPI has 11 letters. So, $n = 11$.
*   **Step 2: Count the repetitions for each letter:**
    *   'M': 1 time
    *   'I': 4 times ($n_1 = 4$)
    *   'S': 4 times ($n_2 = 4$)
    *   'P': 2 times ($n_3 = 2$)
*   **Step 3: Apply the formula:**
    $\frac{11!}{4! \times 4! \times 2!} = \frac{39,916,800}{(24 \times 24 \times 2)} = \frac{39,916,800}{1,152} = 34,650$


---

### Question 3: Selecting Shoes

> How many ways may one right and one left shoe be selected from six pairs of shoes without obtaining a pair?

#### Solution

**Concept:** This is another application of the **Fundamental Counting Principle**.

*   **Step 1: Choose a right shoe.** There are 6 pairs, so there are 6 different right shoes to choose from.
    *   *Choices: 6*
*   **Step 2: Choose a left shoe.** After picking a right shoe, we cannot pick its matching left shoe. This leaves 5 other left shoes to choose from.
    *   *Choices: 5*
*   **Step 3: Calculate the total ways.**
    $6 \times 5 = 30$


---

### Question 4: National Flag

> A new National Flag is to be designed with six vertical strips in yellow, green, blue, and red. In how many ways can this be done so that no two adjacent strips have the same color?

#### Solution

**Concept:** This problem uses the **Fundamental Counting Principle** with a constraint on adjacent positions.

*   **Step 1: First Strip:** There are no restrictions, so we can use any of the 4 colors.
    *   *Choices: 4*
*   **Step 2: Second Strip:** The color must be different from the first strip's color. This leaves 3 choices.
    *   *Choices: 3*
*   **Step 3: Third Strip:** The color must be different from the second strip's color. The first strip's color can be used again. So, there are 3 choices.
    *   *Choices: 3*
*   **Step 4: Fourth, Fifth, and Sixth Strips:** The same logic applies. Each strip has 3 color choices (any color except the one immediately preceding it).
    *   *Choices: 3 for each*
*   **Final Calculation:**
    $4 \times 3 \times 3 \times 3 \times 3 \times 3 = 4 \times 3^5 = 972$


---

## Advanced Combinatorics


---

## 1. Binomial Identities

The **Binomial Theorem** states that for any non-negative integer $n$:
$$(x + y)^n = \sum_{k=0}^{n} \binom{n}{k} x^{n-k} y^k$$
where $\binom{n}{k} = \frac{n!}{k!(n-k)!}$ is the binomial coefficient.

#### Core Identities
*   **Sum of Coefficients**: Substituting $x=1, y=1$:
    $$\sum_{k=0}^{n} \binom{n}{k} = 2^n$$
*   **Alternating Sum**: Substituting $x=1, y=-1$:
    $$\sum_{k=0}^{n} (-1)^k \binom{n}{k} = 0 \implies \sum_{k \text{ even}} \binom{n}{k} = \sum_{k \text{ odd}} \binom{n}{k} = 2^{n-1}$$
*   **Pascal's Identity**: Represents the recurrence relation of Pascal's Triangle:
    $$\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$$
*   **Vandermonde's Identity**: Represents selecting a total of $r$ objects from two disjoint sets of sizes $m$ and $n$:
    $$\binom{m + n}{r} = \sum_{k=0}^{r} \binom{m}{k} \binom{n}{r-k}$$


---

## 2. Generating Functions

An **Ordinary Generating Function (OGF)** represents an infinite numerical sequence $(a_0, a_1, a_2, \dots)$ as the coefficients of a formal power series:
$$G(x) = \sum_{n=0}^{\infty} a_n x^n = a_0 + a_1 x + a_2 x^2 + a_3 x^3 + \dots$$

#### Standard Generating Function Models
*   **Constant Sequence $(1, 1, 1, \dots)$**:
    $$G(x) = \frac{1}{1 - x} = 1 + x + x^2 + x^3 + \dots \quad (|x| < 1)$$
*   **Finite Selection $\binom{n}{k}$**:
    $$G(x) = (1 + x)^n = \sum_{k=0}^{n} \binom{n}{k} x^k$$
*   **Selections with Repetition (r-combinations from n types)**:
    $$G(x) = \frac{1}{(1 - x)^n} = (1 - x)^{-n} = \sum_{r=0}^{\infty} \binom{r + n - 1}{r} x^r$$

#### Calculating Coefficients of Generating Functions
To find the $r$-th term $a_r$ of a sequence represented by $G(x)$, we find the coefficient of $x^r$, denoted as $[x^r] G(x)$.
*   **Method**: Expand $G(x)$ using algebraic manipulation, partial fractions, or the generalized binomial expansion:
    $$(1 - x)^{-n} = \sum_{r=0}^{\infty} \binom{r + n - 1}{r} x^r$$
    Thus:
    $$[x^r] \frac{1}{(1 - x)^n} = \binom{r + n - 1}{r}$$


---

## 3. Partitions of Integers

A **partition** of a positive integer $n$ is a way of writing $n$ as a sum of positive integers, where the order of the terms does not matter.
*   *Example*: The partitions of 4 are:
    1.  $4$
    2.  $3 + 1$
    3.  $2 + 2$
    4.  $2 + 1 + 1$
    5.  $1 + 1 + 1 + 1$
    *(So $P(4) = 5$)*

#### Generating Function for Partitions
The generating function for the number of partitions of $n$, denoted $P(x)$, is:
$$P(x) = \prod_{k=1}^{\infty} \frac{1}{1 - x^k} = \left(\frac{1}{1-x}\right)\left(\frac{1}{1-x^2}\right)\left(\frac{1}{1-x^3}\right)\dots$$


---

## 4. Exponential Generating Functions (EGFs)

For sequences $(a_0, a_1, a_2, \dots)$ where the order of arrangements matters (permutations), we use **Exponential Generating Functions (EGFs)**:
$$E(x) = \sum_{n=0}^{\infty} a_n \frac{x^n}{n!} = a_0 + a_1 \frac{x}{1!} + a_2 \frac{x^2}{2!} + a_3 \frac{x^3}{3!} + \dots$$

#### Standard EGF Models
*   **Constant Sequence $(1, 1, 1, \dots)$**:
    $$E(x) = e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$$
*   **Permutations of $n$ distinct objects taken $r$ at a time**:
    $$E(x) = \sum_{r=0}^{n} P(n, r) \frac{x^r}{r!} = (1 + x)^n$$
*   **EGF for arrangements of $r$ objects chosen from $n$ types with unlimited repetition**:
    $$E(x) = (e^x)^n = e^{nx} = \sum_{r=0}^{\infty} n^r \frac{x^r}{r!}$$
    Here, $[x^r/r!] E(x) = n^r$, representing the number of ways to arrange $r$ elements selected from $n$ types.

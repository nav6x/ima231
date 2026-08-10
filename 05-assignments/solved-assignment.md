# Solved Assignment Problems

[← Back to Course README](../README.md)

  - [Assignment Question 1: Two Children Family](#assignment-question-1-two-children-family)
    - [Solution](#solution)
  - [Assignment Question 2: Sum of Two Dice](#assignment-question-2-sum-of-two-dice)
  - [Assignment Question 3: Independent Events](#assignment-question-3-independent-events)
  - [Assignment Question 4: Conditional Probability Calculation](#assignment-question-4-conditional-probability-calculation)
  - [Assignment Question 5: Defective Bulbs](#assignment-question-5-defective-bulbs)
  - [Assignment Question 6: Students Passing Exam](#assignment-question-6-students-passing-exam)
  - [Assignment Question 7: Tossing Three Coins](#assignment-question-7-tossing-three-coins)
  - [Assignment Question 8: Drawing Balls of Same Color](#assignment-question-8-drawing-balls-of-same-color)
  - [Assignment Question 9: Arranging Letters](#assignment-question-9-arranging-letters)
  - [Assignment Question 10: Contradictory Statements](#assignment-question-10-contradictory-statements)

> **Topic**: Solved Assignment Problems: Core principles, modeling specifications, and practical implementations

---

### Assignment Question 1: Two Children Family

> Consider the selection with equal probabilities (1/4) of a family with two children: S = {bb, bg, gb, gg}. Let A be the event that both children are boys and let B be the event that at least one child is a boy. If it is known that the family selected has at least one boy, then the probability that the family has two boys is ____.

#### Solution

**Concept:** This is a **Conditional Probability** problem. We are asked for the probability of event A (both boys) given that event B (at least one boy) has occurred.

*   **Formula:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$

*   **Step 1: Define the Sample Space and Events.**
    *   Sample Space (S): {bb, bg, gb, gg}. Total outcomes = 4.
    *   Event A (both are boys): {bb}.
    *   Event B (at least one is a boy): {bb, bg, gb}.
*   **Step 2: Find the probabilities of the events.**
    *   $P(A) = \frac{1}{4}$.
    *   $P(B) = \frac{3}{4}$.
*   **Step 3: Find the intersection of A and B.**
    *   $A \cap B$ (both boys AND at least one boy) is {bb}.
    *   $P(A \cap B) = \frac{1}{4}$.
*   **Step 4: Apply the conditional probability formula.**
    *   $P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{1/4}{3/4} = \frac{1}{3}$.

**Answer:** The correct option is **1/3**.


---

### Assignment Question 2: Sum of Two Dice

> In a single throw with two dice, find the probability of getting the sum of 10.

#### Solution

**Concept:** This is a basic probability problem involving sample spaces.

*   **Step 1: Determine the total number of outcomes.**
    *   When two dice are thrown, there are $6 \times 6 = 36$ possible outcomes.
*   **Step 2: Identify the favorable outcomes (sum is 10).**
    *   The pairs that sum to 10 are: (4, 6), (5, 5), (6, 4).
    *   There are 3 favorable outcomes.
*   **Step 3: Calculate the probability.**
    *   Probability = $\frac{\text{Favorable Outcomes}}{\text{Total Outcomes}} = \frac{3}{36} = \frac{1}{12}$.

**Answer:** The correct option is **1/12**.


---

### Assignment Question 3: Independent Events

> Which of the following statement is NOT TRUE.
> (a) If A and B are independent events, then A' and B' are also independent events
> (b) If A and B are independent events, then A and B' are also independent events
> (c) If A, B, C are mutually independent events, then A U B and C are also independent
> (d) If the events A and B are such that $P(A) \ne 0, P(B) \ne 0$ and A is independent of B, then B is not independent of A.

#### Solution

**Concept:** This question tests the properties of independent events.

*   **(a) and (b):** If A and B are independent, then their complements (A', B') are also independent of each other and of the original events. So, (a) and (b) are TRUE.
*   **(c):** If A, B, and C are mutually independent, then the event (A U B) is also independent of C. This is TRUE.
*   **(d):** Independence is a symmetric relationship. If A is independent of B, it means $P(A \cap B) = P(A)P(B)$. This also means B is independent of A, because the formula is the same. The statement says B is *not* independent of A, which is FALSE.

**Answer:** The statement that is **NOT TRUE** is **(d)**.


---

### Assignment Question 4: Conditional Probability Calculation

> Let A and B be two events with $P(A) = \frac{1}{2}$, $P(B) = \frac{1}{3}$ and $P(A \cap B) = \frac{1}{4}$. Find $P(A'|B')$.

#### Solution

**Concept:** This requires using the formula for conditional probability and properties of complements.

*   **Formula:** $P(A'|B') = \frac{P(A' \cap B')}{P(B')}$

*   **Step 1: Find P(B').**
    *   $P(B') = 1 - P(B) = 1 - \frac{1}{3} = \frac{2}{3}$.
*   **Step 2: Find P(A' \cap B').**
    *   By De Morgan's laws, $P(A' \cap B') = P((A \cup B)') = 1 - P(A \cup B)$.
*   **Step 3: Find P(A U B).**
    *   $P(A \cup B) = P(A) + P(B) - P(A \cap B) = \frac{1}{2} + \frac{1}{3} - \frac{1}{4}$.
    *   $P(A \cup B) = \frac{6+4-3}{12} = \frac{7}{12}$.
*   **Step 4: Complete the calculation for P(A' \cap B').**
    *   $P(A' \cap B') = 1 - \frac{7}{12} = \frac{5}{12}$.
*   **Step 5: Calculate the final conditional probability.**
    *   $P(A'|B') = \frac{5/12}{2/3} = \frac{5}{12} \times \frac{3}{2} = \frac{15}{24} = \frac{5}{8}$.

**Answer:** The calculated answer is 5/8. *Note: This does not match the multiple-choice options, suggesting a possible error in the question's options.* Based on the visible checkmark in one image, the intended answer was likely 7/12, which would be P(A U B).


---

### Assignment Question 5: Defective Bulbs

> A basket contains 1000 bulbs. The probability that there is at least 1 defective bulb in the basket is 0.1, and the probability that there are at least 2 defective bulbs is 0.05. Find the probability that the basket contains exactly 1 defective bulb.

#### Solution

**Concept:** This problem involves using the relationship between "at least" probabilities.

*   **Step 1: Define Events.**
    *   A: At least 1 defective bulb. $P(A) = 0.1$.
    *   B: At least 2 defective bulbs. $P(B) = 0.05$.
*   **Step 2: Relate the events.**
    *   The event "at least 1 defective" is the union of "exactly 1 defective" and "at least 2 defective". These are mutually exclusive.
    *   $P(\text{at least 1}) = P(\text{exactly 1}) + P(\text{at least 2})$.
*   **Step 3: Rearrange the formula to solve for the desired probability.**
    *   $P(\text{exactly 1}) = P(\text{at least 1}) - P(\text{at least 2})$.
*   **Step 4: Substitute the given values.**
    *   $P(\text{exactly 1}) = 0.1 - 0.05 = 0.05$.

**Answer:** The correct option is **0.05**.


---

### Assignment Question 6: Students Passing Exam

> Three students A, B, C writes an entrance examination. Their chances of passing are 1/2, 1/3, and 1/4 respectively. Find the probability that at least one of them passes.

#### Solution

**Concept:** Use the **Complement Rule**. It's easier to find the probability that *none* of them pass and subtract that from 1.

*   **Step 1: Find the probability of each student failing.**
    *   $P(A') = 1 - P(A) = 1 - \frac{1}{2} = \frac{1}{2}$.
    *   $P(B') = 1 - P(B) = 1 - \frac{1}{3} = \frac{2}{3}$.
    *   $P(C') = 1 - P(C) = 1 - \frac{1}{4} = \frac{3}{4}$.
*   **Step 2: Find the probability that all of them fail.**
    *   Since the events are independent, we multiply the probabilities.
    *   $P(A' \cap B' \cap C') = P(A') \times P(B') \times P(C') = \frac{1}{2} \times \frac{2}{3} \times \frac{3}{4} = \frac{6}{24} = \frac{1}{4}$.
*   **Step 3: Use the complement rule to find the probability of at least one passing.**
    *   $P(\text{at least one passes}) = 1 - P(\text{all fail}) = 1 - \frac{1}{4} = \frac{3}{4}$.

**Answer:** The correct option is **3/4**.


---

### Assignment Question 7: Tossing Three Coins

> Three unbiased coins are tossed. What is the probability of getting at most two heads?

#### Solution

**Concept:** Use the **Complement Rule**. The opposite of "at most two heads" is "exactly three heads".

*   **Step 1: Determine the total sample space.**
    *   For 3 coins, there are $2^3 = 8$ outcomes (HHH, HHT, HTH, THH, HTT, THT, TTH, TTT).
*   **Step 2: Find the probability of the complement event (exactly 3 heads).**
    *   There is only one outcome with exactly 3 heads: HHH.
    *   $P(\text{3 heads}) = \frac{1}{8}$.
*   **Step 3: Subtract from 1 to find the desired probability.**
    *   $P(\text{at most 2 heads}) = 1 - P(\text{3 heads}) = 1 - \frac{1}{8} = \frac{7}{8}$.

**Answer:** The correct option is **7/8**.


---

### Assignment Question 8: Drawing Balls of Same Color

> A box contains 5 Red 3 Yellow 4 Green balls. If 3 balls are drawn, the number of ways of drawing them so that all of all same colour is ____.

#### Solution

**Concept:** This is a **Combination** problem. We find the number of ways to get 3 of each color and add them up, as these are mutually exclusive events.

*   **Total Balls:** 5 + 3 + 4 = 12.
*   **Case 1: All 3 are Red.**
    *   Ways to choose 3R from 5R: $\binom{5}{3} = \frac{5!}{3!2!} = 10$.
*   **Case 2: All 3 are Yellow.**
    *   Ways to choose 3Y from 3Y: $\binom{3}{3} = 1$.
*   **Case 3: All 3 are Green.**
    *   Ways to choose 3G from 4G: $\binom{4}{3} = 4$.
*   **Total Ways:** Add the ways from each case.
    *   $10 + 1 + 4 = 15$.

**Answer:** The correct option is **15**.


---

### Assignment Question 9: Arranging Letters

> The number of ways to arrange the letters of the word CHEESE are ____.

#### Solution

**Concept:** This is a **Permutation with Repetitions** problem.

*   **Formula:** $\frac{n!}{n_1! n_2! \dots n_k!}$
*   **Step 1: Count the total letters (n).**
    *   CHEESE has 6 letters. So, $n = 6$.
*   **Step 2: Count the repetitions for each letter.**
    *   'C': 1 time
    *   'H': 1 time
    *   'E': 3 times ($n_1 = 3$)
    *   'S': 1 time
*   **Step 3: Apply the formula.**
    *   $\frac{6!}{3!} = \frac{720}{6} = 120$.

**Answer:** The correct option is **120**.


---

### Assignment Question 10: Contradictory Statements

> A speaks the truth in 75% cases, and B in 80% of the cases. In what percentage of cases, are they likely to contradict each other in stating the same fact?

#### Solution

**Concept:** Contradiction occurs in two mutually exclusive scenarios: (A tells truth AND B lies) OR (A lies AND B tells truth).

*   **Step 1: List the probabilities of truth and lying for A and B.**
    *   $P(A_{truth}) = 0.75$, $P(A_{lie}) = 1 - 0.75 = 0.25$.
    *   $P(B_{truth}) = 0.80$, $P(B_{lie}) = 1 - 0.80 = 0.20$.
*   **Step 2: Calculate the probability of the first scenario.**
    *   $P(A_{truth} \cap B_{lie}) = P(A_{truth}) \times P(B_{lie}) = 0.75 \times 0.20 = 0.15$.
*   **Step 3: Calculate the probability of the second scenario.**
    *   $P(A_{lie} \cap B_{truth}) = P(A_{lie}) \times P(B_{truth}) = 0.25 \times 0.80 = 0.20$.
*   **Step 4: Add the probabilities of the two scenarios.**
    *   $P(\text{contradict}) = 0.15 + 0.20 = 0.35$.
*   **Step 5: Convert to percentage.**
    *   $0.35 \times 100\% = 35\%$.

**Answer:** They are likely to contradict each other in **35%** of cases. This corresponds to the fraction **7/20**. *Note: The options are not fully visible, but 35% is the correct calculation.*

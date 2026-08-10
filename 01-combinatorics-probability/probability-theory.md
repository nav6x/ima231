# Probability

[← Back to Course README](../README.md)

- [Types of Events](#types-of-events)
- [General Properties of Probability](#general-properties-of-probability)
- [Key Formulas & Proofs](#key-formulas-proofs)
  - [Question 5: Probability of Exactly One Event](#question-5-probability-of-exactly-one-event)
    - [Solution](#solution)
  - [Question 6: Union Inequality](#question-6-union-inequality)
- [Conditional Probability](#conditional-probability)
- [Partition of a Sample Space and Total Probability](#partition-of-a-sample-space-and-total-probability)
- [Bayes' Theorem](#bayes-theorem)
- [Questions and Answers (Probability)](#questions-and-answers-probability)
  - [Question 7: Good and Defective Articles](#question-7-good-and-defective-articles)
  - [Question 8: High Fidelity System](#question-8-high-fidelity-system)
  - [Question 9: Problem Solving](#question-9-problem-solving)
  - [Question 10: VC Appointment](#question-10-vc-appointment)
  - [Question 11: Misfiled Report](#question-11-misfiled-report)
- [Team Questions](#team-questions)
  - [Team Question 1: A and B Throw a Die](#team-question-1-a-and-b-throw-a-die)
  - [Team Question 2: 53 Sundays in a Year](#team-question-2-53-sundays-in-a-year)
  - [Team Question 3: Same Number of Heads](#team-question-3-same-number-of-heads)
  - [Team Question 4: Prime Given Odd](#team-question-4-prime-given-odd)
  - [Team Question 5: Gold and Silver Coins](#team-question-5-gold-and-silver-coins)
  - [Team Question 6: Defective Tubes](#team-question-6-defective-tubes)
  - [Team Question 7: Brown Hair and Eyes](#team-question-7-brown-hair-and-eyes)
  - [Team Question 8: First Head Wins](#team-question-8-first-head-wins)
  - [Team Question 9: Committee Selection](#team-question-9-committee-selection)
  - [Team Question 10: Real Roots of Quadratic](#team-question-10-real-roots-of-quadratic)
  - [Team Question 11: Two Balls of Same Color](#team-question-11-two-balls-of-same-color)
  - [Team Question 12: Doctor Diagnosis](#team-question-12-doctor-diagnosis)

> **Topic**: Probability: Types of Events, General Properties of Probability, Key Formulas & Proofs, Conditional Probability

---

## Types of Events

-   **Equally likely events:** Those events that have the same chance of occurrence/equal probabilities.
-   **Mutually Exclusive Events:** The probability of their intersection is 0; they have no common elements.
-   **Exhaustive Events:** Their union must be equal to the sample space.
-   **Independent Events:** Those events whose probabilities are not dependent on the occurrence of the other.


---

## General Properties of Probability

1.  $P(A) \ge 0$, $P(S) = 1$
2.  $0 \le P(A) \le 1$
3.  If A and B are mutually exclusive events, then $P(A \cup B) = P(A) + P(B)$ (Kolmogorov's Axiom)

-   **Additional Properties:**
  1. $P(\emptyset) = 0$
  2. If $A'$ or $A^c$ is the complement of event A, $P(A') = 1 - P(A)$
  3. If $A \subset B$, $P(A) \le P(B)$


---

## Key Formulas & Proofs

-   **For any two events A and B:**
  -   **Show that $P(A \cup B) = P(A) + P(B) - P(A \cap B)$**
  -   **Proof:**
    -   We can write $A \cup B = A \cup (B \cap A')$. Since $A$ and $(B \cap A')$ are mutually exclusive.
    -   $P(A \cup B) = P(A) + P(B \cap A')$
    -   We also know $B = (A \cap B) \cup (B \cap A')$. Since $(A \cap B)$ and $(B \cap A')$ are mutually exclusive.
    -   $P(B) = P(A \cap B) + P(B \cap A')$
    -   $P(B \cap A') = P(B) - P(A \cap B)$
    -   Substituting back, we get: $P(A \cup B) = P(A) + P(B) - P(A \cap B)$. **(Proved)**

-   **For three events A, B, and C:**
  -   $P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(B \cap C) - P(A \cap C) + P(A \cap B \cap C)$

-   **In general (Inclusion-Exclusion Principle):**
  -   $P(\cup_{i=1}^n A_i) = \sum_{i} P(A_i) - \sum_{i<j} P(A_i \cap A_j) + \sum_{i<j<k} P(A_i \cap A_j \cap A_k) - \dots + (-1)^{n-1} P(\cap_{i=1}^n A_i)$


---

### Question 5: Probability of Exactly One Event

> Show that the probability that exactly one of the events A or B occurs is $P(A) + P(B) - 2P(A \cap B)$.

#### Solution

**Concept:** This proof relies on the **axioms of probability** and the definition of mutually exclusive events. The event "exactly one of A or B" is the union of two mutually exclusive events: (A occurs and B does not) and (B occurs and A does not).

*   **Step 1: Define the event in set notation.**
    *   "A occurs and B does not" is $A \cap B'$.
    *   "B occurs and A does not" is $B \cap A'$.
    *   The event "exactly one" is $(A \cap B') \cup (B \cap A')$.
*   **Step 2: Use the addition rule for mutually exclusive events.**
    *   Since a case where A happens and B doesn't cannot overlap with a case where B happens and A doesn't, the events are mutually exclusive.
    *   $P((A \cap B') \cup (B \cap A')) = P(A \cap B') + P(B \cap A')$.
*   **Step 3: Express the terms using the intersection.**
    *   From set theory, we know $P(A) = P(A \cap B) + P(A \cap B')$. Rearranging gives:
        $P(A \cap B') = P(A) - P(A \cap B)$.
    *   Similarly, $P(B \cap A') = P(B) - P(A \cap B)$.
*   **Step 4: Substitute these back into the equation from Step 2.**
    *   $P(\text{exactly one}) = (P(A) - P(A \cap B)) + (P(B) - P(A \cap B))$
*   **Step 5: Simplify the expression.**
    *   $P(\text{exactly one}) = P(A) + P(B) - 2P(A \cap B)$. **(Proved)**


---

### Question 6: Union Inequality

> Show that for any two events, $P(A_1 \cup A_2) \le P(A_1) + P(A_2)$.

#### Solution

**Concept:** This proof uses the **General Addition Rule** for probability and the fact that probability cannot be negative.

*   **Step 1: State the General Addition Rule.**
    *   $P(A_1 \cup A_2) = P(A_1) + P(A_2) - P(A_1 \cap A_2)$.
*   **Step 2: Analyze the intersection term.**
    *   By the axioms of probability, the probability of any event must be non-negative. Therefore, $P(A_1 \cap A_2) \ge 0$.
*   **Step 3: Apply this to the addition rule.**
    *   Since we are subtracting a non-negative number ($P(A_1 \cap A_2)$) from the right side of the equation in Step 1, the value of the right side will either decrease or stay the same.
    *   This means the left side must be less than or equal to the sum of the first two terms.
*   **Conclusion:**
    *   $P(A_1 \cup A_2) \le P(A_1) + P(A_2)$. **(Proved)**


---

## Conditional Probability

-   The probability of an event B occurring when an event A has already occurred is called conditional probability.
  -   $P(B|A) = \frac{P(A \cap B)}{P(A)}$, provided $P(A) \ne 0$.

-   **Multiplication Theorem:**
  -   $P(A \cap B) = P(A) \cdot P(B|A)$
  -   $P(A \cap B) = P(B) \cdot P(A|B)$

-   **Independent Events:**
  -   If A and B are independent, the occurrence of A does not affect the occurrence of B.
  -   $P(B|A) = P(B)$ and $P(A|B) = P(A)$.
  -   $P(A \cap B) = P(A) \cdot P(B)$.


---

## Partition of a Sample Space and Total Probability

-   **Partition:** A set of events $A_1, A_2, \dots, A_n$ is a partition of the sample space S if:
  1. They are mutually exclusive: $A_i \cap A_j = \emptyset$ for $i \ne j$.
  2. They are exhaustive: $\cup_{i=1}^n A_i = S$.
-   An event 'E' can be considered as the union of its intersections with the partition events:
  -   $E = E \cap S = E \cap (A_1 \cup A_2 \cup \dots \cup A_n) = (E \cap A_1) \cup (E \cap A_2) \cup \dots \cup (E \cap A_n)$

-   **Theorem of Total Probability:** Let $A_1, A_2, \dots, A_n$ be a partition of the sample space S. Let E be any event associated with S. Then:
  -   $P(E) = \sum_{i=1}^n P(A_i)P(E|A_i)$
  -   **Derivation:**
    -   From the partition, the events $(E \cap A_i)$ are mutually exclusive.
    -   Therefore, $P(E) = P(\cup_{i=1}^n (E \cap A_i)) = \sum_{i=1}^n P(E \cap A_i)$.
    -   Using the multiplication rule, $P(E \cap A_i) = P(A_i)P(E|A_i)$.
    -   Substituting this gives the final theorem: $P(E) = \sum_{i=1}^n P(A_i)P(E|A_i)$.


---

## Bayes' Theorem

-   Let $A_1, A_2, \dots, A_n$ be a partition of the sample space S, and let E be any event with $P(E) > 0$. Then the posterior probability of $A_i$ given that E has occurred is:
  -   $P(A_i|E) = \frac{P(A_i)P(E|A_i)}{P(E)} = \frac{P(A_i)P(E|A_i)}{\sum_{j=1}^n P(A_j)P(E|A_j)}$
  -   **Derivation:**
    -   From the definition of conditional probability, $P(A_i|E) = \frac{P(A_i \cap E)}{P(E)}$.
    -   Using the multiplication rule, we can write the numerator as $P(A_i \cap E) = P(A_i)P(E|A_i)$.
    -   The denominator is given by the Theorem of Total Probability.
    -   Combining these gives Bayes' Theorem.


---

## Questions and Answers (Probability)


---

### Question 7: Good and Defective Articles

> A lot contains 10 good articles, 4 with minor defects, and 2 with major defects. 2 articles are randomly chosen. Find the probability that:
> (i) at least 1 is a good article
> (ii) at most 1 is a good article
> (iii) exactly 1 is a good article

#### Solution

**Concept:** This is a **Combination** problem because the order in which the articles are chosen does not matter. We find the number of ways for the desired event and divide by the total number of ways to choose 2 articles.

*   **Total Items:** 10 Good + 4 Minor Defect + 2 Major Defect = 16 articles.
*   **Defective Items:** 4 + 2 = 6.
*   **Total possible ways to choose 2 articles from 16:**
    *   $\binom{16}{2} = \frac{16!}{2!(16-2)!} = \frac{16 \times 15}{2} = 120$.

**(i) At least 1 is a good article**
This means the outcome is either (1 Good, 1 Defective) or (2 Good).

*   **Ways for (1 Good, 1 Defective):** $\binom{10}{1} \times \binom{6}{1} = 10 \times 6 = 60$.
*   **Ways for (2 Good):** $\binom{10}{2} = \frac{10 \times 9}{2} = 45$.
*   **Total Favorable Ways:** $60 + 45 = 105$.
*   **Probability:** $\frac{105}{120} = \frac{7}{8}$.

**(ii) At most 1 is a good article**
This means the outcome is either (1 Good, 1 Defective) or (0 Good, 2 Defective).

*   **Ways for (1 Good, 1 Defective):** $\binom{10}{1} \times \binom{6}{1} = 60$.
*   **Ways for (0 Good, 2 Defective):** $\binom{6}{2} = \frac{6 \times 5}{2} = 15$.
*   **Total Favorable Ways:** $60 + 15 = 75$.
*   **Probability:** $\frac{75}{120} = \frac{5}{8}$.

**(iii) Exactly 1 is a good article**
This means the outcome is (1 Good, 1 Defective).

*   **Step 1: Identify the required combination.**
    *   We need exactly 1 good article and 1 defective article.
*   **Step 2: Calculate the number of ways to choose 1 good article from 10.**
    *   $\binom{10}{1} = 10$
*   **Step 3: Calculate the number of ways to choose 1 defective article from 6.**
    *   $\binom{6}{1} = 6$
*   **Step 4: Calculate total favorable ways using the multiplication principle.**
    *   Total Favorable Ways = $\binom{10}{1} \times \binom{6}{1} = 10 \times 6 = 60$
*   **Step 5: Calculate the probability.**
    *   Probability = $\frac{\text{Favorable Ways}}{\text{Total Ways}} = \frac{60}{120} = \frac{1}{2}$


---

### Question 8: High Fidelity System

> The probability that a communication system will have high fidelity is 0.81 and the probability that it will have high fidelity & high selectivity is 0.18. Find the probability that the system will have high selectivity given that it has high fidelity.

#### Solution

**Concept:** This is a **Conditional Probability** problem. We are asked for the probability of one event *given* that another event has already occurred.

*   **Formula:** $P(B|A) = \frac{P(A \cap B)}{P(A)}$
    *   Where $P(B|A)$ is the probability of B given A.

*   **Step 1: Define the events.**
    *   A: The system has high fidelity.
    *   B: The system has high selectivity.
*   **Step 2: Identify the given probabilities.**
    *   $P(A) = 0.81$
    *   $P(A \cap B) = 0.18$
*   **Step 3: Apply the formula to find $P(B|A)$.**
    *   $P(B|A) = \frac{0.18}{0.81} \approx 0.222$


---

### Question 9: Problem Solving

> Probability of A, B, and C solving a problem are 1/3, 2/7, and 3/8 respectively. If all three try to solve the problem simultaneously, find the probability that:
> (i) exactly one will solve it
> (ii) the problem will be solved

#### Solution

**Concept:** This problem involves **Independent Events**. The success or failure of one person does not affect the others. We also need the concept of **Complementary Events**.

*   **Step 1: List the probabilities of success and failure for each person.**
    *   $P(A) = \frac{1}{3} \implies P(A') = 1 - \frac{1}{3} = \frac{2}{3}$
    *   $P(B) = \frac{2}{7} \implies P(B') = 1 - \frac{2}{7} = \frac{5}{7}$
    *   $P(C) = \frac{3}{8} \implies P(C') = 1 - \frac{3}{8} = \frac{5}{8}$

**(i) Exactly one will solve it**
This can happen in three mutually exclusive ways.

*   **Case 1: A solves, B and C fail.**
    *   $P(A \cap B' \cap C') = P(A) \times P(B') \times P(C') = \frac{1}{3} \times \frac{5}{7} \times \frac{5}{8} = \frac{25}{168}$
*   **Case 2: B solves, A and C fail.**
    *   $P(A' \cap B \cap C') = P(A') \times P(B) \times P(C') = \frac{2}{3} \times \frac{2}{7} \times \frac{5}{8} = \frac{20}{168}$
*   **Case 3: C solves, A and B fail.**
    *   $P(A' \cap B' \cap C) = P(A') \times P(B') \times P(C) = \frac{2}{3} \times \frac{5}{7} \times \frac{3}{8} = \frac{30}{168}$
*   **Total Probability:** Add the probabilities of the three cases.
    *   $\frac{25}{168} + \frac{20}{168} + \frac{30}{168} = \frac{75}{168}$

**(ii) The problem will be solved**
This is the complement of the event "no one solves the problem". It's easier to calculate the probability of failure and subtract it from 1.

*   **Step 1: Calculate the probability that no one solves it (all fail).**
    *   $P(A' \cap B' \cap C') = P(A') \times P(B') \times P(C') = \frac{2}{3} \times \frac{5}{7} \times \frac{5}{8} = \frac{50}{168}$
*   **Step 2: Use the complement rule.**
    *   $P(\text{solved}) = 1 - P(\text{no one solves})$
    *   $P(\text{solved}) = 1 - \frac{50}{168} = \frac{118}{168}$


---

### Question 10: VC Appointment

> Of three names, the chances that a politician, a businessman, and an academician will be appointed as VC of a university are 0.5, 0.3, and 0.2 respectively. Probability that research is promoted by these people if they are appointed as VC are 0.3, 0.7 and 0.8 respectively. If research is promoted in the university, what is the probability that VC is an academician?

#### Solution

**Concept:** This is a classic **Bayes' Theorem** problem. We are given prior probabilities (who the VC might be) and conditional probabilities (likelihood of promoting research), and we need to find a "reversed" or posterior probability (who the VC is, *given* that research was promoted).

*   **Formula:** $P(C|E) = \frac{P(C)P(E|C)}{P(E)}$
    *   Where $P(E)$ is found using the Law of Total Probability: $P(E) = P(A)P(E|A) + P(B)P(E|B) + P(C)P(E|C)$

*   **Step 1: Define Events.**
    *   A: VC is Politician, B: VC is Businessman, C: VC is Academician
    *   E: Research is promoted
*   **Step 2: List Prior Probabilities.**
    *   $P(A) = 0.5$, $P(B) = 0.3$, $P(C) = 0.2$
*   **Step 3: List Conditional Probabilities (Likelihoods).**
    *   $P(E|A) = 0.3$, $P(E|B) = 0.7$, $P(E|C) = 0.8$
*   **Step 4: Calculate the Total Probability of the evidence, P(E).**
    *   $P(E) = (0.5 \times 0.3) + (0.3 \times 0.7) + (0.2 \times 0.8)$
    *   $P(E) = 0.15 + 0.21 + 0.16 = 0.52$
*   **Step 5: Apply Bayes' Theorem to find P(C|E).**
    *   $P(C|E) = \frac{P(C)P(E|C)}{P(E)} = \frac{0.2 \times 0.8}{0.52} = \frac{0.16}{0.52} \approx 0.3077$


---

### Question 11: Misfiled Report

> An office has 4 secretaries handling respectively 20%, 60%, 15% and 5% of the files of the government reports. The P that they miss files, such reports are respectively 0.05, 0.10, 0.10 and 0.05. Find the P that a misfiled report is caused by the first secretary.

#### Solution

**Concept:** This is another **Bayes' Theorem** problem, structured identically to the previous one.

*   **Step 1: Define Events.**
    *   A, B, C, D: File handled by Secretary 1, 2, 3, 4 respectively.
    *   E: A file is misfiled.
*   **Step 2: List Prior Probabilities.**
    *   $P(A) = 0.20$, $P(B) = 0.60$, $P(C) = 0.15$, $P(D) = 0.05$
*   **Step 3: List Conditional Probabilities (Likelihoods).**
    *   $P(E|A) = 0.05$, $P(E|B) = 0.10$, $P(E|C) = 0.10$, $P(E|D) = 0.05$
*   **Step 4: Calculate the Total Probability of the evidence, P(E).**
    *   $P(E) = (0.20 \times 0.05) + (0.60 \times 0.10) + (0.15 \times 0.10) + (0.05 \times 0.05)$
    *   $P(E) = 0.01 + 0.06 + 0.015 + 0.0025 = 0.0875$
*   **Step 5: Apply Bayes' Theorem to find P(A|E).**
    *   $P(A|E) = \frac{P(A)P(E|A)}{P(E)} = \frac{0.20 \times 0.05}{0.0875} = \frac{0.01}{0.0875} \approx 0.1143$


---

## Team Questions

### Team Question 1: A and B Throw a Die

> A and B throw a die alternatively till one of them gets a 6 and wins the game. Find their respective probabilities of winning if A starts first.

#### Solution

**Concept:** This is an infinite **Geometric Series** problem. A can win on his first turn, or his second, or his third, and so on. Each subsequent turn for A requires that both A and B failed on their previous turns.

*   **Step 1: Define probabilities of success and failure on a single throw.**
    *   Success (S): Rolling a 6. $P(S) = \frac{1}{6}$.
    *   Failure (F): Not rolling a 6. $P(F) = \frac{5}{6}$.
*   **Step 2: List the ways A can win.**
    *   Turn 1: A rolls S. Probability = $\frac{1}{6}$.
    *   Turn 2: A rolls F, B rolls F, A rolls S. Probability = $(\frac{5}{6}) \times (\frac{5}{6}) \times (\frac{1}{6}) = (\frac{5}{6})^2 \times (\frac{1}{6})$.
    *   Turn 3: A, B, A, B all fail, then A succeeds. Probability = $(\frac{5}{6})^4 \times (\frac{1}{6})$.
*   **Step 3: Identify the geometric series.**
    *   The total probability is the sum: $\frac{1}{6} + (\frac{5}{6})^2 \frac{1}{6} + (\frac{5}{6})^4 \frac{1}{6} + \dots$
    *   First term $a = \frac{1}{6}$.
    *   Common ratio $r = (\frac{5}{6})^2 = \frac{25}{36}$.
*   **Step 4: Use the sum to infinity formula.**
    *   **Formula:** $S_\infty = \frac{a}{1-r}$
    *   $P(A \text{ wins}) = \frac{\frac{1}{6}}{1 - \frac{25}{36}} = \frac{\frac{1}{6}}{\frac{11}{36}} = \frac{1}{6} \times \frac{36}{11} = \frac{6}{11}$.
*   **Step 5: Find the probability for B.**
    *   Since either A or B must win, their probabilities sum to 1.
    *   $P(B \text{ wins}) = 1 - P(A \text{ wins}) = 1 - \frac{6}{11} = \frac{5}{11}$.


### Team Question 2: 53 Sundays in a Year

> What is the probability that a randomly selected year contains 53 Sundays?

#### Solution

**Concept:** This problem uses the **Law of Total Probability**. The event (53 Sundays) depends on the type of year (Normal or Leap), which form a partition.

*   **Step 1: Analyze a Normal Year.**
    *   365 days = 52 weeks + 1 extra day.
    *   The probability this 1 extra day is a Sunday is $\frac{1}{7}$.
*   **Step 2: Analyze a Leap Year.**
    *   366 days = 52 weeks + 2 extra days.
    *   The two extra days can be (Sat, Sun), (Sun, Mon), etc. There are 7 possibilities. A Sunday appears in 2 of them.
    *   The probability of having a Sunday is $\frac{2}{7}$.
*   **Step 3: Use the probabilities of a year being Normal or Leap.**
    *   A common approximation is that 1 in 4 years is a leap year.
    *   $P(\text{Leap}) = \frac{1}{4}$, $P(\text{Normal}) = \frac{3}{4}$.
*   **Step 4: Apply the Law of Total Probability.**
    *   $P(53S) = P(53S|\text{Normal})P(\text{Normal}) + P(53S|\text{Leap})P(\text{Leap})$
    *   $P(53S) = (\frac{1}{7} \times \frac{3}{4}) + (\frac{2}{7} \times \frac{1}{4}) = \frac{3}{28} + \frac{2}{28} = \frac{5}{28}$.


### Team Question 3: Same Number of Heads

> Each of two people A and B tosses three fair coins. Find the probability that they get the same number of heads.

#### Solution

**Concept:** This problem involves finding a **Discrete Probability Distribution** and then calculating the probability of joint events for two independent trials. A geometric series is not applicable here because the event is a one-time comparison, not a series of trials that continues until a condition is met.

*   **Step 1: Find the probability distribution for one person tossing 3 coins.**
    *   Total outcomes = $2^3 = 8$.
    *   P(0 Heads - TTT) = $\frac{1}{8}$.
    *   P(1 Head - HTT, THT, TTH) = $\frac{3}{8}$.
    *   P(2 Heads - HHT, HTH, THH) = $\frac{3}{8}$.
    *   P(3 Heads - HHH) = $\frac{1}{8}$.
*   **Step 2: Identify the mutually exclusive ways they can have the same number of heads.**
    *   Both get 0 heads OR both get 1 head OR both get 2 heads OR both get 3 heads.
*   **Step 3: Calculate the probability for each case and add them.**
    *   Since A and B are independent, we multiply their probabilities.
    *   $P(\text{A=0 and B=0}) = (\frac{1}{8}) \times (\frac{1}{8}) = \frac{1}{64}$.
    *   $P(\text{A=1 and B=1}) = (\frac{3}{8}) \times (\frac{3}{8}) = \frac{9}{64}$.
    *   $P(\text{A=2 and B=2}) = (\frac{3}{8}) \times (\frac{3}{8}) = \frac{9}{64}$.
    *   $P(\text{A=3 and B=3}) = (\frac{1}{8}) \times (\frac{1}{8}) = \frac{1}{64}$.
*   **Step 4: Sum the probabilities.**
    *   Total Probability = $\frac{1}{64} + \frac{9}{64} + \frac{9}{64} + \frac{1}{64} = \frac{20}{64} = \frac{5}{16}$.


### Team Question 4: Prime Given Odd

> A die is tossed. If the number is odd on the face, what is the probability that it is prime?

#### Solution

**Concept:** This is a **Conditional Probability** problem. The sample space is reduced by the given condition.

*   **Method 1: Reduced Sample Space**
    *   **Step 1:** The given condition is that the number is odd. The original sample space {1, 2, 3, 4, 5, 6} is reduced to {1, 3, 5}.
    *   **Step 2:** Within this new sample space, we look for the favorable outcomes (prime numbers). The prime numbers in {1, 3, 5} are {3, 5}.
    *   **Step 3:** The probability is the ratio of favorable outcomes to total outcomes in the reduced space: $\frac{2}{3}$.

*   **Method 2: Formula**
    *   **Formula:** $P(A|B) = \frac{P(A \cap B)}{P(B)}$
    *   **Events:** A = Number is prime {2, 3, 5}, B = Number is odd {1, 3, 5}.
    *   $A \cap B$ (Odd and Prime) = {3, 5}.
    *   $P(A \cap B) = \frac{2}{6}$.
    *   $P(B) = \frac{3}{6}$.
    *   $P(A|B) = \frac{\frac{2}{6}}{\frac{3}{6}} = \frac{2}{3}$.


### Team Question 5: Gold and Silver Coins

> A bag contains 10 gold coins & 8 silver coins. Two successive drawings of four coins are made. Find the P that the first drawing gave 4 gold coins & second drawing will give 4 silver coins if:
> (i) coins are replaced
> (ii) coins are not replaced

#### Solution

**Concept:** This problem contrasts **Independent Events** (with replacement) and **Dependent Events** (without replacement).

*   **Total coins:** 18.

**(i) Coins are replaced**
The two draws are independent events.

*   **Step 1: Probability of the first draw (4 gold).**
    *   $P(\text{4 Gold}) = \frac{\text{Ways to choose 4G from 10}}{\text{Ways to choose 4 from 18}} = \frac{\binom{10}{4}}{\binom{18}{4}} = \frac{210}{3060}$.
*   **Step 2: Probability of the second draw (4 silver).**
    *   Since the coins are replaced, the bag is reset to 18 coins.
    *   $P(\text{4 Silver}) = \frac{\text{Ways to choose 4S from 8}}{\text{Ways to choose 4 from 18}} = \frac{\binom{8}{4}}{\binom{18}{4}} = \frac{70}{3060}$.
*   **Step 3: Final Probability.**
    *   $P(\text{Total}) = P(\text{4 Gold}) \times P(\text{4 Silver}) = \frac{210}{3060} \times \frac{70}{3060}$.

**(ii) Coins are not replaced**
The second draw is dependent on the first.

*   **Step 1: Probability of the first draw (4 gold).**
    *   $P(\text{4 Gold}) = \frac{\binom{10}{4}}{\binom{18}{4}} = \frac{210}{3060}$.
*   **Step 2: State of the bag after the first draw.**
    *   There are now $18 - 4 = 14$ coins left in the bag (6 Gold, 8 Silver).
*   **Step 3: Probability of the second draw (4 silver) given the first.**
    *   $P(\text{4S | 4G}) = \frac{\text{Ways to choose 4S from 8}}{\text{Ways to choose 4 from 14}} = \frac{\binom{8}{4}}{\binom{14}{4}} = \frac{70}{1001}$.
*   **Step 4: Final Probability.**
    *   $P(\text{Total}) = P(\text{4 Gold}) \times P(\text{4S | 4G}) = \frac{210}{3060} \times \frac{70}{1001}$.


### Team Question 6: Defective Tubes

> Two defective tubes get mixed with 4 good ones. The tubes are tested one by one until both defective are found. What is the P that the last defective tube is obtained on the: (i) second test (ii) third test (iii) sixth test.

#### Solution

**Concept:** This is a permutation/arrangement problem. We are looking for the probability of specific sequences occurring.

*   **Total tubes:** 6 (2 Defective, 4 Good).

**(i) Second test**
This means the first two tubes tested must be the defective ones.

*   **Step 1:** P(1st is Defective) = $\frac{2}{6}$.
*   **Step 2:** P(2nd is Defective | 1st was Defective) = $\frac{1}{5}$.
*   **Probability:** $\frac{2}{6} \times \frac{1}{5} = \frac{2}{30} = \frac{1}{15}$.

**(ii) Third test**
This means one defective and one good were found in the first two tests (in any order), and the third test finds the second defective.

*   **Step 1: Probability of finding one D and one G in the first two tests.**
    *   P(DG) = $(\frac{2}{6}) \times (\frac{4}{5}) = \frac{8}{30}$.
    *   P(GD) = $(\frac{4}{6}) \times (\frac{2}{5}) = \frac{8}{30}$.
    *   Total P(one D in first two) = $\frac{8}{30} + \frac{8}{30} = \frac{16}{30}$.
*   **Step 2: Probability of the third test being the second D.**
    *   After two tests (one D, one G), there are 4 tubes left (1 D, 3 G).
    *   P(3rd is D) = $\frac{1}{4}$.
*   **Step 3: Final Probability.**
    *   $P(\text{Total}) = P(\text{one D in first two}) \times P(\text{3rd is D}) = \frac{16}{30} \times \frac{1}{4} = \frac{4}{30} = \frac{2}{15}$.

**(iii) Sixth test**
This means the last tube tested is the second defective one.

*   **Step 1:** This is equivalent to asking for the probability that the last tube in any random arrangement of the 6 tubes is defective.
*   **Step 2:** There are 2 defective tubes out of 6 total tubes. Any tube has an equal chance of being in the last position.
*   **Probability:** $\frac{2}{6} = \frac{1}{3}$.


### Team Question 7: Brown Hair and Eyes

> In a certain town, 40% have brown hair, 25% have brown eyes, 15% have both. A person is selected at random.
> (i) If he has brown hair, what is the P that he has brown eyes too?
> (ii) If he has brown eyes, what is the P that he does not have brown hair?
> (iii) Determine the P that he has neither brown hair nor brown eyes.

#### Solution

**Concept:** This problem uses **Conditional Probability** and the **Addition Rule**.

*   **Step 1: Define Events and Probabilities.**
    *   H: Brown Hair, $P(H) = 0.40$.
    *   E: Brown Eyes, $P(E) = 0.25$.
    *   $P(H \cap E) = 0.15$.

**(i) P(E|H) - Probability of brown eyes given brown hair.**

*   **Formula:** $P(E|H) = \frac{P(H \cap E)}{P(H)}$
*   **Calculation:** $\frac{0.15}{0.40} = 0.375$.

**(ii) P(H'|E) - Probability of NOT brown hair given brown eyes.**

*   **Formula:** $P(H'|E) = 1 - P(H|E)$.
*   **Step 1: First find P(H|E).**
    *   $P(H|E) = \frac{P(H \cap E)}{P(E)} = \frac{0.15}{0.25} = 0.6$.
*   **Step 2: Calculate the complement.**
    *   $P(H'|E) = 1 - 0.6 = 0.4$.

**(iii) P(H' \cap E') - Probability of neither brown hair nor brown eyes.**

*   **Formula:** By De Morgan's laws, $P(H' \cap E') = P((H \cup E)') = 1 - P(H \cup E)$.
*   **Step 1: First find P(H U E).**
    *   $P(H \cup E) = P(H) + P(E) - P(H \cap E) = 0.40 + 0.25 - 0.15 = 0.50$.
*   **Step 2: Calculate the complement.**
    *   $1 - 0.50 = 0.50$.


### Team Question 8: First Head Wins

> Six people toss a fair coin one by one. The game is won by the player who throws heads first. Find the P of success of the fourth player.

#### Solution

**Concept:** This problem implies the game continues in rounds if no one wins. This requires summing an infinite **Geometric Series**.

*   **Step 1: Define the event for Player 4 (P4) to win in any given round.**
    *   For P4 to win, Players 1, 2, and 3 must get Tails (T), and Player 4 must get Heads (H).
    *   The probability of this sequence (TTTH) is: $P(\text{P4 wins in a round}) = (\frac{1}{2})^3 \times \frac{1}{2} = \frac{1}{16}$. This is the base probability of P4 winning, assuming they get a turn.

*   **Step 2: Define the event that allows the game to continue for another round.**
    *   For the game to repeat, all 6 players must get Tails.
    *   The probability of this is: $P(\text{all fail}) = (\frac{1}{2})^6 = \frac{1}{64}$.

*   **Step 3: Formulate the geometric series.**
    *   P4 can win in Round 1, OR Round 2, OR Round 3, and so on.
    *   $P(\text{Win in R1}) = \frac{1}{16}$.
    *   $P(\text{Win in R2}) = P(\text{all fail in R1}) \times P(\text{Win in R1}) = \frac{1}{64} \times \frac{1}{16}$.
    *   $P(\text{Win in R3}) = P(\text{all fail in R1 and R2}) \times P(\text{Win in R1}) = (\frac{1}{64})^2 \times \frac{1}{16}$.
    *   This forms a geometric series with first term $a = \frac{1}{16}$ and common ratio $r = \frac{1}{64}$.

*   **Step 4: Use the sum to infinity formula.**
    *   **Formula:** $S_\infty = \frac{a}{1-r}$
    *   $P(\text{P4 wins}) = \frac{\frac{1}{16}}{1 - \frac{1}{64}} = \frac{\frac{1}{16}}{\frac{63}{64}} = \frac{1}{16} \times \frac{64}{63} = \frac{4}{63}$.


### Team Question 9: Committee Selection

> A committee of four people is to be appointed from three offices of production department, four offices from purchase dept, two offices from Sales dept and one chartered accountant. Find the P of:
> (i) Choosing one from each category.
> (ii) It should have at least 1 from purchase dept.
> (iii) The CA must be in the committee.

#### Solution

**Concept:** This is a **Combination** problem. The order of selection for a committee does not matter.

*   **Total People:** 3 (Prod) + 4 (Purch) + 2 (Sales) + 1 (CA) = 10 people.
*   **Total ways to choose a committee of 4:**
    *   $\binom{10}{4} = \frac{10!}{4!6!} = 210$.

**(i) Choosing one from each category**

*   **Favorable Ways:** Choose 1 from each of the 4 groups.
    *   $\binom{3}{1} \times \binom{4}{1} \times \binom{2}{1} \times \binom{1}{1} = 3 \times 4 \times 2 \times 1 = 24$.
*   **Probability:** $\frac{24}{210} = \frac{4}{35}$.

**(ii) At least 1 from purchase dept**

*   **Concept:** Use the **Complement Rule**. It's easier to find the probability of the opposite event ("none from purchase") and subtract from 1.
*   **Step 1: Find ways to choose a committee with NO one from purchase.**
    *   This means we choose 4 people from the remaining $10 - 4 = 6$ people.
    *   $\binom{6}{4} = \frac{6!}{4!2!} = 15$.
*   **Step 2: Find the probability of this opposite event.**
    *   $P(\text{none from purchase}) = \frac{15}{210}$.
*   **Step 3: Subtract from 1.**
    *   $P(\text{at least one}) = 1 - \frac{15}{210} = \frac{195}{210} = \frac{13}{14}$.

**(iii) The CA must be in the committee**

*   **Step 1: Fix one spot for the CA.**
    *   This is certain, so there is $\binom{1}{1} = 1$ way.
*   **Step 2: Choose the remaining 3 members.**
    *   We need to choose 3 more people from the remaining 9 people.
    *   $\binom{9}{3} = \frac{9 \times 8 \times 7}{3 \times 2 \times 1} = 84$.
*   **Step 3: Calculate the probability.**
    *   $P(\text{CA is in}) = \frac{84}{210} = \frac{2}{5}$.


### Team Question 10: Real Roots of Quadratic

> The coefficients a, b, c of the quadratic equation $ax^2 + bx + c = 0$ are determined by throwing a die 3 times. Find the P that the roots are real.

#### Solution

**Concept:** For a quadratic equation, the roots are real if the **discriminant is non-negative**. We must count the number of outcomes from rolling a die that satisfy this condition.

*   **Condition for Real Roots:** $b^2 - 4ac \ge 0$, or $b^2 \ge 4ac$.
*   **Total Outcomes:** Each die roll has 6 outcomes. For three rolls, the total number of outcomes is $6 \times 6 \times 6 = 216$.
*   **Favorable Outcomes:** We must manually count the combinations of (a, b, c) from {1, 2, 3, 4, 5, 6} that satisfy $b^2 \ge 4ac$.
    *   **b=1:** $1 \ge 4ac$. (No solutions)
    *   **b=2:** $4 \ge 4ac \implies 1 \ge ac$. Only (a=1, c=1). (1 case)
    *   **b=3:** $9 \ge 4ac \implies 2.25 \ge ac$. (a=1,c=1), (a=1,c=2), (a=2,c=1). (3 cases)
    *   **b=4:** $16 \ge 4ac \implies 4 \ge ac$. (a=1,c=1..4), (a=2,c=1..2), (a=3,c=1), (a=4,c=1). (4+2+1+1=8 cases)
    *   **b=5:** $25 \ge 4ac \implies 6.25 \ge ac$. (a=1,c=1..6), (a=2,c=1..3), (a=3,c=1..2), (a=4,c=1), (a=5,c=1), (a=6,c=1). (6+3+2+1+1+1=14 cases)
    *   **b=6:** $36 \ge 4ac \implies 9 \ge ac$. (a=1,c=1..6), (a=2,c=1..4), (a=3,c=1..3), (a=4,c=1..2), (a=5,c=1), (a=6,c=1). (6+4+3+2+1+1=17 cases)
*   **Total Favorable Outcomes:** $1 + 3 + 8 + 14 + 17 = 43$.
*   **Probability:** $\frac{43}{216}$.


### Team Question 11: Two Balls of Same Color

> A bag contains 8 white & 6 red balls. What is the P of drawing two balls of the same colour?

#### Solution

**Concept:** This involves calculating the probability of two **mutually exclusive events** (drawing two white OR drawing two red) and adding them together. We use combinations as the order doesn't matter.

*   **Total Balls:** 8 + 6 = 14.
*   **Total ways to draw 2 balls:** $\binom{14}{2} = \frac{14 \times 13}{2} = 91$.

*   **Case 1: Drawing 2 White Balls**
    *   Ways to choose 2W from 8W: $\binom{8}{2} = \frac{8 \times 7}{2} = 28$.
    *   $P(2W) = \frac{28}{91}$.
*   **Case 2: Drawing 2 Red Balls**
    *   Ways to choose 2R from 6R: $\binom{6}{2} = \frac{6 \times 5}{2} = 15$.
    *   $P(2R) = \frac{15}{91}$.
*   **Final Probability:**
    *   $P(\text{same color}) = P(2W) + P(2R) = \frac{28}{91} + \frac{15}{91} = \frac{43}{91}$.


### Team Question 12: Doctor Diagnosis

> The chances that doctor A will diagnose a disease X correctly is 60%. The chance that a patient will die by his treatment after correct diagnosis is 40% and the chances of death by wrong diagnosis is 70%. A patient of a doctor A, who had disease X, died. What is the chance that his disease was diagnosed correctly?

#### Solution

**Concept:** This is a **Bayes' Theorem** problem. We are given that the patient died (the evidence) and we want to find the probability that the diagnosis was correct (the cause).

*   **Step 1: Define Events.**
    *   A: Diagnosis is correct.
    *   A': Diagnosis is wrong.
    *   D: The patient died.
*   **Step 2: List Prior Probabilities.**
    *   $P(A) = 0.60$
    *   $P(A') = 1 - 0.60 = 0.40$
*   **Step 3: List Conditional Probabilities (Likelihoods).**
    *   $P(D|A) = 0.40$ (Prob. of death given correct diagnosis)
    *   $P(D|A') = 0.70$ (Prob. of death given wrong diagnosis)
*   **Step 4: Calculate the Total Probability of the evidence, P(D).**
    *   $P(D) = P(A)P(D|A) + P(A')P(D|A')$
    *   $P(D) = (0.60 \times 0.40) + (0.40 \times 0.70) = 0.24 + 0.28 = 0.52$.
*   **Step 5: Apply Bayes' Theorem to find P(A|D).**
    *   $P(A|D) = \frac{P(A)P(D|A)}{P(D)} = \frac{0.60 \times 0.40}{0.52} = \frac{0.24}{0.52} \approx 0.4615$.

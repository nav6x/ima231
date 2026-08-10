<div align="center">

# Applied Mathematics & Probability Theory
### Course Code: IMA 231 | ICAS, MAHE
**Combinatorics & counting techniques, probability spaces & conditional probability, Bayes' Theorem, discrete & continuous random variables (Binomial, Poisson, Uniform, Exponential, Normal/Gaussian), 2D joint distributions, covariance & correlation coefficient, Central Limit Theorem (CLT), and linear programming & optimization algorithms.**

[![Institution](https://img.shields.io/badge/Institution-ICAS_%7C_MAHE-orange?style=flat-square)](https://manipal.edu/icas.html)
[![Course Code](https://img.shields.io/badge/Course_Code-IMA_231-blueviolet?style=flat-square)](#academic-course-information)
[![Academic Level](https://img.shields.io/badge/Level-2nd_Year_%7C_Semester_III-brightgreen?style=flat-square)](#academic-course-information)
[![Domain](https://img.shields.io/badge/Domain-Mathematics_%7C_Probability-00599C?style=flat-square)](https://manipal.edu/icas.html)
[![Tools](https://img.shields.io/badge/Tools-Python_%7C_SciPy_%7C_LaTeX-3776AB?style=flat-square&logo=scipy&logoColor=white)](https://scipy.org/)

<br/>

<table width="100%">
  <tr align="center">
    <td>
      <b>5 Modules</b><br/>
      <sub>Applied Math Curriculum</sub>
    </td>
    <td>
      <b>48 Hours</b><br/>
      <sub>Course Hours</sub>
    </td>
    <td>
      <b>15 Notes & Solved Files</b><br/>
      <sub>Applied Math Modules</sub>
    </td>
    <td>
      <b>Python / SciPy</b><br/>
      <sub>Applied Mathematics Stack</sub>
    </td>
  </tr>
</table>

</div>

---

### Academic Course Information

| Academic Attribute | Course Details & Specs |
| :--- | :--- |
| **Course Structure (L-T-P-C)** | 3-1-0-4 (3 Lecture Credits, 1 Tutorial Credit, 0 Practical Credits, 4 Total Course Credits) |
| **Contact Hours** | 48 Theory & Problem Solving Hours |
| **Curriculum Distribution** | 48 Hours (14h Combinatorics + 10h Probability + 8h Distributions + 10h 2D RVs + 6h Optimization) |
| **Academic Level & Semester** | 2nd Year, Semester III (Applied Mathematics) |

---

### Project Metrics

```toml
[academic.course_info]
institution       = "International Centre for Applied Sciences (ICAS)"
university        = "Manipal Academy of Higher Education (MAHE)"
course_code       = "IMA 231"
course_title      = "Applied Mathematics & Probability Theory"
credits_structure = "3-1-0-4"
academic_level    = "2nd Year"
semester          = "Semester III"

[repository.metadata]
mathematical_modules = 5
total_lecture_hours  = 48
notes_files_count    = 15
notation_standards   = "KaTeX / LaTeX"
curriculum_status    = "100% [████████████████████████████████████████]"

[curriculum.distribution.hours]
combinatorics_and_counting = 14
probability_foundations    = 10
distributions_theory       = 8
functions_of_random_variables = 10
optimization_simplex_kkt   = 6
```

---

### Coursework Pipeline

```mermaid
flowchart LR
    %% Styles
    classDef primary fill:#2a2b36,stroke:#007acc,stroke-width:1.5px,color:#ffffff;

    A["Combinatorics<br/>(14h: Counting & EGFs)"]:::primary
    B["Probability Theory<br/>(10h: Axioms & Bayes)"]:::primary
    C["Random Variables<br/>(10h: MGFs & 2D Vectors)"]:::primary
    D["Distributions<br/>(8h: Discrete & Continuous)"]:::primary
    E["Optimization<br/>(6h: Simplex & KKT)"]:::primary

    A --> B
    B --> C
    C --> D
    D --> E
```

---

### Course Modules Directory

| Chapter Module | Covered Syllabus Concepts | Key Markdown Notes |
| :--- | :--- | :--- |
| **Combinatorics (14 Hours)** | Two basic counting principles, arrangements & selections (with/without repetitions), distributions, binomial identities, generating function models, calculating coefficients, partitions, exponential generating functions (EGFs). | [combinatorics-counting.md](01-combinatorics-probability/combinatorics-counting.md) |
| **Probability Foundations (10 Hours)** | Basic set theory, axioms of probability, sample space, conditional probability, total probability theorem, Bayes' theorem, 1D & 2D random variables, mean & variance, Chebyshev's inequality, correlation coefficient. | [probability-theory.md](01-combinatorics-probability/probability-theory.md) • [1d-random-variables.md](02-random-variables/1d-random-variables.md) • [2d-joint-distributions.md](02-random-variables/2d-joint-distributions.md) |
| **Distributions (8 Hours)** | Binomial, Poisson, Exponential, Normal, and Chi-square distributions. | [binomial-distribution.md](03-distributions/binomial-distribution.md) • [normal-distribution.md](03-distributions/normal-distribution.md) • [uniform-distribution.md](03-distributions/uniform-distribution.md) |
| **Functions of Random Variables (10 Hours)** | Transformations of 1D and 2D random variables, Moment Generating Functions (MGFs). | [random-variable-transformations.md](02-random-variables/random-variable-transformations.md) • [moment-generating-functions.md](02-random-variables/moment-generating-functions.md) |
| **Optimization (6 Hours)** | Basic solution, convex sets and functions, Simplex Method, constrained optimization (Lagrange Multipliers, KKT conditions). | [optimization-methods.md](04-optimization/optimization-methods.md) |

---

### Text / Reference Books
1. **P.L. Meyer**, *Introduction to Probability and Statistical Applications*, 2nd Edition, Oxford & IBH Publishing, 1980.
2. **Miller, Freund and Johnson**, *Probability and Statistics for Engineers*, 8th Edition, PHI, 2011.
3. **Ross Sheldon M.**, *Introduction to Probability and Statistics for Engineers and Scientists*, Elsevier, 2010.
4. **Alan Tucker**, *Applied Combinatorics*, Wiley Publishers, 2012.
5. **Marc Peter Deisenroth, A. Aldo Faisal, Cheng Soon Ong**, *Mathematics for Machine Learning*, Cambridge University Press, 2020.
6. **Hamdy A. Taha**, *Operations Research: An Introduction*, 8th Edition, Pearson Education, 2008.
7. **E. S. Page, L. B. Wilson**, *An Introduction to Computational Combinatorics*, Cambridge University Press.

---

### Technical Guide

<details>
<summary><b>Equation Render Support</b></summary>

All equations are written using standard LaTeX/KaTeX delimiters:
*   **Inline Math**: Wrapped in single dollar signs (e.g., `$P(A|B) = \frac{P(A \cap B)}{P(B)}$`).
*   **Block Math**: Wrapped in double dollar signs (e.g., `$$M_X(t) = E[e^{tX}]$$`).
</details>

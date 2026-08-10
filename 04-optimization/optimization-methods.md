# Optimization Theory and Methods

[← Back to Course README](../README.md)

- [Convex Sets and Convex Functions](#convex-sets-and-convex-functions)
- [Convex Sets](#convex-sets)
- [Convex Functions](#convex-functions)
- [Linear Programming & Basic Solutions](#linear-programming-basic-solutions)
- [Standard Form of LPP](#standard-form-of-lpp)
- [Basic Feasible Solutions (BFS)](#basic-feasible-solutions-bfs)
- [The Simplex Method](#the-simplex-method)
  - [Step-by-Step Tabular Simplex Algorithm](#step-by-step-tabular-simplex-algorithm)
    - [Example Problem](#example-problem)
    - [Step 1: Standardize with Slack Variables](#step-1-standardize-with-slack-variables)
    - [Step 2: Set Up Initial Simplex Table](#step-2-set-up-initial-simplex-table)
    - [Perform First Row Operations](#perform-first-row-operations)
    - [Second Simplex Table](#second-simplex-table)
    - [Perform Second Row Operations](#perform-second-row-operations)
    - [Final Simplex Table (Optimal)](#final-simplex-table-optimal)
- [Constrained Optimization](#constrained-optimization)
- [Lagrange Multipliers (Equality Constraints)](#lagrange-multipliers-equality-constraints)
- [Karush-Kuhn-Tucker (KKT) Conditions (Inequality Constraints)](#karush-kuhn-tucker-kkt-conditions-inequality-constraints)

> **Topic**: Optimization Theory and Methods: Convex Sets and Convex Functions, Convex Sets, Convex Functions, Linear Programming & Basic Solutions

---

## Convex Sets and Convex Functions


---

## Convex Sets
A set $C \subseteq \mathbb{R}^n$ is called **convex** if, for any two points $x, y \in C$, the line segment connecting them also lies entirely within $C$.
Mathematically:
$$\forall x, y \in C, \quad \forall \alpha \in [0, 1]: \quad \alpha x + (1 - \alpha)y \in C$$

*   **Example of Convex Set**: A solid circle, a sphere, or a half-space.
*   **Example of Non-Convex Set**: A crescent shape or a donut (torus).


---

## Convex Functions
Let $C \subseteq \mathbb{R}^n$ be a convex set. A function $f: C \to \mathbb{R}$ is called **convex** if the line segment connecting any two points on the graph of the function lies above or on the graph.
Mathematically:
$$\forall x, y \in C, \quad \forall \alpha \in [0, 1]: \quad f(\alpha x + (1 - \alpha)y) \le \alpha f(x) + (1 - \alpha)f(y)$$

*   **Theorem**: If $f$ is a convex function defined on a convex set $C$, then any local minimum of $f$ is also a global minimum.
*   **Strict Convexity**: If the inequality is strict ($<$) for all $x \ne y$ and $\alpha \in (0, 1)$, the function has a unique global minimum.


---

## Linear Programming & Basic Solutions

A Linear Programming Problem (LPP) is an optimization problem where the objective function and all constraints are linear.


---

## Standard Form of LPP
$$\text{Maximize } Z = c^T x$$
$$\text{Subject to } A x = b, \quad x \ge 0$$
where $A$ is an $m \times n$ matrix of rank $m$ (with $n > m$), $b \ge 0$ is a vector of size $m$, and $c, x$ are vectors of size $n$.


---

## Basic Feasible Solutions (BFS)
A **basic solution** is obtained by setting $n - m$ variables (called **non-basic variables**) to zero, and solving the remaining $m$ linear equations for the $m$ variables (called **basic variables**).
*   **Feasible Solution**: Any vector $x$ that satisfies $Ax = b$ and $x \ge 0$.
*   **Basic Feasible Solution (BFS)**: A basic solution that is also feasible ($x \ge 0$). A BFS corresponds geometrically to an extreme point (vertex) of the feasible region.


---

## The Simplex Method

The Simplex Method is an iterative algebraic algorithm that moves along the vertices of the feasible polyhedral region, improving the objective value at each step until an optimal solution is found.

### Step-by-Step Tabular Simplex Algorithm

#### Example Problem
$$\text{Maximize } Z = 3x_1 + 2x_2$$
$$\text{Subject to:}$$
$$2x_1 + x_2 \le 18$$
$$2x_1 + 3x_2 \le 42$$
$$x_1, x_2 \ge 0$$

#### Step 1: Standardize with Slack Variables
Convert inequalities to equalities by introducing slack variables $s_1, s_2 \ge 0$:
$$2x_1 + x_2 + s_1 = 18$$
$$2x_1 + 3x_2 + s_2 = 42$$
$$\text{Objective: } Z - 3x_1 - 2x_2 - 0s_1 - 0s_2 = 0$$

#### Step 2: Set Up Initial Simplex Table
Set non-basic variables $x_1 = 0, x_2 = 0$. The initial basic variables are $s_1 = 18, s_2 = 42$.

| Basic | $x_1$ | $x_2$ | $s_1$ | $s_2$ | Solution ($b$) | Ratio Test ($b / x_j$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| $s_1$ | **2** | 1 | 1 | 0 | 18 | $18 / 2 = 9$ (Minimum) |
| $s_2$ | 1 | 3 | 0 | 1 | 42 | $42 / 1 = 42$ |
| **Row $Z$** | **-3** | -2 | 0 | 0 | 0 | |

*   **Entering Variable**: $x_1$ (most negative coefficient in Row $Z$, $-3$).
*   **Leaving Variable**: $s_1$ (smallest non-negative ratio, $9$).
*   **Pivot Element**: **2**.

#### Perform First Row Operations
1.  Divide Row 1 by 2 to make the pivot element 1:
    $$R_1 \leftarrow \frac{1}{2} R_1 \implies [1, \frac{1}{2}, \frac{1}{2}, 0, 9]$$
2.  Eliminate $x_1$ from Row 2:
    $$R_2 \leftarrow R_2 - 1 \cdot R_1 \implies [0, \frac{5}{2}, -\frac{1}{2}, 1, 33]$$
3.  Eliminate $x_1$ from Row $Z$:
    $$R_Z \leftarrow R_Z + 3 R_1 \implies [0, -\frac{1}{2}, \frac{3}{2}, 0, 27]$$

#### Second Simplex Table

| Basic | $x_1$ | $x_2$ | $s_1$ | $s_2$ | Solution ($b$) | Ratio Test |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| $x_1$ | 1 | 1/2 | 1/2 | 0 | 9 | $9 / (1/2) = 18$ |
| $s_2$ | 0 | **5/2** | -1/2 | 1 | 33 | $33 / (5/2) = \frac{66}{5} = 13.2$ (Minimum) |
| **Row $Z$** | 0 | **-1/2** | 3/2 | 0 | 27 | |

*   **Entering Variable**: $x_2$ (coefficient $-\frac{1}{2}$).
*   **Leaving Variable**: $s_2$ (smallest ratio, $13.2$).
*   **Pivot Element**: **5/2**.

#### Perform Second Row Operations
1.  Multiply Row 2 by $\frac{2}{5}$ to make the pivot element 1:
    $$R_2 \leftarrow \frac{2}{5} R_2 \implies [0, 1, -\frac{1}{5}, \frac{2}{5}, \frac{66}{5}]$$
2.  Eliminate $x_2$ from Row 1:
    $$R_1 \leftarrow R_1 - \frac{1}{2} R_2 \implies [1, 0, \frac{3}{5}, -\frac{1}{5}, \frac{12}{5}]$$
3.  Eliminate $x_2$ from Row $Z$:
    $$R_Z \leftarrow R_Z + \frac{1}{2} R_2 \implies [0, 0, \frac{7}{5}, \frac{1}{5}, \frac{168}{5}]$$

#### Final Simplex Table (Optimal)

| Basic | $x_1$ | $x_2$ | $s_1$ | $s_2$ | Solution ($b$) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| $x_1$ | 1 | 0 | 3/5 | -1/5 | 12/5 = 2.4 |
| $x_2$ | 0 | 1 | -1/5 | 2/5 | 66/5 = 13.2 |
| **Row $Z$** | 0 | 0 | 7/5 | 1/5 | 168/5 = 33.6 |

Since all Row $Z$ coefficients are non-negative ($\ge 0$), the optimal solution is reached:
$$x_1 = \frac{12}{5} = 2.4, \quad x_2 = \frac{66}{5} = 13.2 \implies \text{Maximum } Z = \frac{168}{5} = 33.6$$


---

## Constrained Optimization

Constrained optimization involves optimizing an objective function subject to boundary conditions.


---

## Lagrange Multipliers (Equality Constraints)
To find local extrema of a function $f(x)$ subject to equality constraints $g_i(x) = 0$:

1.  **Formulate the Lagrangian Function**:
    $$\mathcal{L}(x, \lambda) = f(x) - \sum_{i=1}^k \lambda_i g_i(x)$$
    where $\lambda_i$ are called the **Lagrange Multipliers**.
2.  **Solve the System of Equations**:
    $$\nabla \mathcal{L}(x, \lambda) = 0 \implies \frac{\partial \mathcal{L}}{\partial x_j} = 0, \quad \frac{\partial \mathcal{L}}{\partial \lambda_i} = 0$$


---

## Karush-Kuhn-Tucker (KKT) Conditions (Inequality Constraints)
To optimize $f(x)$ subject to inequality constraints $g_i(x) \le 0$ and equality constraints $h_j(x) = 0$, the optimal solution $x^*$ must satisfy the KKT conditions:

1.  **Stationarity**:
    $$\nabla f(x^*) + \sum_{i} \mu_i \nabla g_i(x^*) + \sum_{j} \lambda_j \nabla h_j(x^*) = 0$$
2.  **Primal Feasibility**:
    $$g_i(x^*) \le 0, \quad h_j(x^*) = 0 \quad \forall i, j$$
3.  **Dual Feasibility**:
    $$\mu_i \ge 0 \quad \forall i$$
4.  **Complementary Slackness**:
    $$\mu_i g_i(x^*) = 0 \quad \forall i$$
    *(This implies either the constraint is inactive ($g_i(x^*) < 0 \implies \mu_i = 0$), or the constraint is active ($g_i(x^*) = 0 \implies \mu_i \ge 0$).)*

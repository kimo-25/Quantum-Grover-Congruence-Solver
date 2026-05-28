# Quantum Grover Cost Estimator & Exponential Congruence Solver

An algorithmic tool designed to solve exponential congruence equations of the form: 

$$a \cdot f^x + b \cdot g^y \equiv c \pmod{q}$$

The project utilizes a classical **Meet-in-the-Middle (Baby-step Giant-step)** optimization technique to map the solution space, and provides a theoretical complexity comparison against **Grover's Quantum Search Algorithm**.

---

## 📌 Theoretical Background

### 1. Classical Search Space (N)
Given a maximum exponent boundary (`max_exp`), the total size of the exhaustive brute-force search space for pairs (x, y) is:
$$N = (\text{max.exp} + 1)^2$$

Instead of a brute-force $O(N)$ check, this solver builds a Hash-Table mapping for the left-hand side, reducing the classical solver time complexity asymptotically to $O(\sqrt{N})$.

### 2. Quantum Speedup (Grover's Oracle)
If the equation has $M$ valid solutions within the search space, **Grover's Quantum Search Algorithm** can locate a solution with a quadratic speedup over pure unstructured search. The theoretical number of required quantum oracle evaluations is estimated using:
$$\text{Grover Cost} \approx \frac{\pi}{4} \sqrt{\frac{N}{M}}$$

---

## 🚀 Features
* **Meet-in-the-Middle Solver:** High-performance modular exponentiation parsing using Python default dictionaries.
* **Quantum Complexity Modeling:** Computes theoretical Grover oracle iterations based on actual solution density (M).
* **Statistical Benchmarking:** Automatically evaluates the average number of classical trials versus quantum upper bounds using `tabulate` interface.

---

## 💻 Sample Output

```text
======================================================================
 📌 PROJECT CASE: EXAMPLE 1 → 2^X + 3^Y ≡ 10 (MOD 17)
======================================================================
+---------------------------+----------------------------------------+
| Parameter                 | Value                                  |
+---------------------------+----------------------------------------+
| Target Equation           | 1·2^x + 1·3^y ≡ 10 (mod 17)            |
| Search Bound              | x, y ∈ [0, 15]                         |
| Total Search Space (N)    | 256 combinations                       |
| Total Solutions Found (M) | 16                                     |
+---------------------------+----------------------------------------+
```
## 🛠️ Requirements & Execution
pip install tabulate 

python Quantum_Grover_Solver.ipynb

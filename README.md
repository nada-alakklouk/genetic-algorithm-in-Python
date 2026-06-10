# 🧬 Mathematical Function Optimization Using Genetic Algorithms (GA)

An artificial intelligence project implementing a **Genetic Algorithm (GA)** from scratch in Python to find the global maximum of a given mathematical fitness function. Inspired by natural selection, this evolutionary computing project maps continuous numerical spaces into discrete binary chromosomes to execute selection, crossover, and mutation workflows.

---

## 📂 Project Assets & Structure

* 💻 **[View Core Optimization Notebook](./main.ipynb)** – Interactive Jupyter Notebook containing the full pipeline setup, chromosome encoding functions, and generation log traces.
* 🧮 **Target Optimization Function:**
  $$f(x) = x^2 - 3y + 4 \quad \text{where } x \in [-10, 10] \text{ and } y \text{ is anchored to } 0$$

---

## 🛠️ Tech Stack & Theoretical Components

* **Programming Language:** Python 🐍
* **Core Concepts Applied:**
  * **Genotype-Phenotype Mapping:** Translating continuous values of $x$ into a 10-bit binary string chromosome ($2^{10} = 1024$ possible state intervals).
  * **Tournament Selection:** Randomly sampling $k$-individuals ($k=5$) to compete for parenting rights based on fitness dominance, reducing selection pressure artifacts.
  * **Single-Point Crossover:** Slicing and recombining binary substrings from two parent genotypes to breed structural offspring.
  * **Bit-Flip Mutation:** Applying a stochastic probability ($\text{Rate} = 0.1$) to invert individual bits, introducing population diversity and preventing premature convergence on local extrema.

---

## 🚀 Evolutionary Pipeline Workflow

1. **Population Initialization:** Spawning a baseline generation of 50 random binary strings, decoding them into real numbers within $[-10, 10]$ using the mapping formula:
   $$x = X_{\min} + \frac{\text{int}(x_{\text{bin}}, 2)}{2^{\text{Gene\_Length}} - 1} \times (X_{\max} - X_{\min})$$
2. **Fitness Calculation:** Scoring each decoded individual through the objective function $f(x)$.
3. **Mating Selection:** Executing Tournament loops to filter high-performing vectors.
4. **Reproduction & Mutation:** Splicing parent bitstrings at a random index and checking each bit sequentially against the mutation probability to flip it (`0` $\leftrightarrow$ `1`).
5. **Generation Replacement:** Swapping out the old population matrix for the newly generated offspring generation.
6. **Termination Check:** Halting evolution automatically if an individual scores a fitness metric $\ge 100$ or when the generation ceiling (100 epochs) is breached.

---

## 📊 Performance Analytics & Convergence

* **Execution Result:** The algorithm converged instantly in **Generation 0**, isolating an optimal individual value of $x \approx 9.9804$, yielding an outstanding maximum fitness yield of **$103.609$**.
* **Interpretation:** This demonstrates how evolutionary heuristics can rapidly map boundaries and pinpoint extreme maximum regions without requiring mathematical derivative gradients.

---

## 👤 Developed by:
* **Nada Alaklook**
* 🔗 [Connect with me on LinkedIn](https://linkedin.com/in/nada-alaklook-725049252)

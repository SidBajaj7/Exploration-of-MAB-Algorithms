# 🎯 Exploration of Multi‑Armed Bandit Algorithms

This project explores the Multi‑Armed Bandit problem with a focus on **Best Arm Identification**. We implement and compare three algorithms:

- **Sequential Halving (SH)**
- **Exponential‑Gap Elimination (EGE)**
- **Median Elimination (ME)**

---

## 🧪 What We've Done So Far

- **Implemented** SH, EGE, and recently **added Median Elimination** to the `scripts/` directory.
- **Organized notebooks** into two sub‑folders for clean experimentation:
  - `notebooks/EGE and SH/`
  - `notebooks/Median Elimination/`
- **Ran 5 000 simulated cases** per scenario (each case has 6 arms, 1 500 pulls per arm) across four reward distributions.
- **Logged** for every run:
  - **Average pulls & cost**
  - **Observed confidence**
  - **Accuracy of best‑arm recovery**
  - **Early‑stopping rate**

---

## 📊 Summary of Results

| Distribution     | Δ   | Method                   | Target Conf./Cost* | Avg. Pulls | Avg. Cost | Avg. Conf. | Accuracy (%) | Stopped Early (%) |
|------------------|-----|--------------------------|---------------------|------------|-----------|-------------|----------------|---------------------|
| **Uniform**       | 0.1 | Exponential Gap Elimination | 95%              | 9000       | 1125      | 0.16        | 16.20          | 100                 |
|                   | —   | Sequential Halving          | —                | 7685.29    | 960.29    | 0.83        | 87.00          | 50.88               |
|                   | —   | Median Elimination          | 95%              | 9000       | 1125.03   | 0.34        | 33.72          | 100                 |
|                   | 0.1 | Exponential Gap Elimination | 90%              | 9000       | 1124.95   | 0.16        | 15.86          | 100                 |
|                   | —   | Sequential Halving          | —                | 9000       | 1124.95   | 1.00        | 100.00         | 100                 |
|                   | —   | Median Elimination          | 90%              | 9000       | 1124.91   | 0.33        | 33.40          | 100                 |
| **Normal**        | 0.1 | Exponential Gap Elimination | 95%              | 9000       | 1124.95   | 0.16        | 16.38          | 100                 |
|                   | —   | Sequential Halving          | —                | 7677.76    | 959.35    | 0.80        | 81.22          | 52.14               |
|                   | —   | Median Elimination          | 95%              | 9000       | 1124.95   | 0.33        | 33.10          | 100                 |
|                   | 0.2 | Exponential Gap Elimination | 95%              | 8417.15    | 1052.16   | 0.77        | 76.58          | 42.02               |
|                   | —   | Sequential Halving          | —                | 7681.46    | 959.85    | 0.87        | 86.78          | 51.10               |
|                   | —   | Median Elimination          | 95%              | 9000       | 1124.97   | 0.32        | 32.48          | 100                 |
| **Mixture Normal**| 0.1 | Exponential Gap Elimination | 95%              | —          | —         | —           | —              | —                   |
|                   | —   | Sequential Halving          | —                | 1000       | —         | —           | —              | —                   |
|                   | —   | Median Elimination          | 95%              | —          | —         | —           | —              | —                   |
|                   | 0.1 | Exponential Gap Elimination | 90%              | —          | —         | —           | —              | —                   |
|                   | —   | Sequential Halving          | —                | 2000       | —         | —           | —              | —                   |
|                   | —   | Median Elimination          | 90%              | —          | —         | —           | —              | —                   |
| **Gamma**         | 0.1 | Exponential Gap Elimination | 95%              | 9000       | 1124.97   | 0.16        | 17.14          | 100                 |
|                   | —   | Sequential Halving          | —                | 7674.69    | 958.97    | 0.72        | 69.08          | 52.76               |
|                   | —   | Median Elimination          | 95%              | 9000       | 1125.03   | 0.28        | 32.60          | 100                 |
|                   | 0.1 | Exponential Gap Elimination | 90%              | 9000       | 1124.85   | 0.16        | 17.12          | 100                 |
|                   | —   | Sequential Halving          | —                | 9000       | 1124.85   | 0.96        | 99.96          | 100                 |
|                   | —   | Median Elimination          | 90%              | 9000       | 1124.95   | 0.29        | 33.30          | 100                 |

<sub>*For SH the value in this column denotes the **target budget** rather than a confidence level.</sub>

---

## 🧠 Next Steps

- **Complete Mixture‑Normal runs** for all three algorithms.
- **Visualize** the table above with scatter and bar plots (accuracy vs. cost, etc.).
- **Write an analysis section** in `reports/` summarising where each algorithm shines.
- **Add unit tests** ensuring parity across implementations.

---

## 📁 Repository Layout

├── scripts/
│ ├── ege.py
│ ├── sequential_halving.py
│ └── median_elimination.py ← NEW
├── notebooks/
│ ├── EGE and SH/
│ └── Median Elimination/ ← NEW
├── results/
└── data/


---

## 🚧 Work in Progress

We’re iterating quickly—expect frequent updates as the Mixture‑Normal experiments finish and plots land. Stay tuned!

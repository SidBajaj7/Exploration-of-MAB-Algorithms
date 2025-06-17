# 🎯 Exploration of Multi-Armed Bandit Algorithms

This project explores the Multi-Armed Bandit problem with a focus on **Best Arm Identification**. We implement and compare two popular algorithms:

- **Sequential Halving (SH)**
- **Exponential-Gap Elimination (EGE)**

---

## 🧪 What We've Done So Far

- **Implemented** both SH and EGE from scratch in Python.
- **Tested** them on synthetic datasets using various reward distributions:
  - Uniform
  - Normal
  - Mixture Normal
  - Gamma
- **Evaluated** key metrics across 5000+ simulations:
  - Accuracy
  - Confidence level
  - Budget/Cost
  - Early stopping behavior

---

## 📊 Summary of Results

| Distribution     | Δ (Avg Reward Diff) | Method                  | Target Confidence | Avg. Pulls | Avg. Cost | Avg. Confidence | Accuracy (%) | Stopped Early (%) |
|------------------|---------------------|-------------------------|-------------------|------------|-----------|------------------|----------------|---------------------|
| **Uniform**       | 0.1                 | Exponential Gap Elimination | 95%              | 9000       | 1125      | 0.16             | 16.2           | 100                 |
|                  |                     | Sequential Halving          | —                | 7685.29    | 960.29    | 0.83             | 87             | 50.88               |
|                  | 0.1                 | Exponential Gap Elimination | 90%              | 9000       | 1124.95   | 0.16             | 15.86          | 100                 |
|                  |                     | Sequential Halving          | —                | 9000       | 1124.95   | 1.00             | 100            | 100                 |
| **Normal**        | 0.1                 | Exponential Gap Elimination | 95%              | 9000       | 1124.95   | 0.16             | 16.38          | 100                 |
|                  |                     | Sequential Halving          | —                | 7677.76    | 959.35    | 0.80             | 81.22          | 52.14               |
|                  | 0.2                 | Exponential Gap Elimination | 95%              | 8417.15    | 1052.16   | 0.77             | 76.58          | 42.02               |
|                  |                     | Sequential Halving          | —                | 7681.46    | 959.85    | 0.87             | 86.78          | 51.1                |
| **Mixture Normal**| 0.1                 | Exponential Gap Elimination | 95%              | —          | —         | —                | —              | —                   |
|                  |                     | Sequential Halving          | —                | 1000       | —         | —                | —              | —                   |
|                  | 0.1                 | Exponential Gap Elimination | 90%              | —          | —         | —                | —              | —                   |
|                  |                     | Sequential Halving          | —                | 2000       | —         | —                | —              | —                   |
| **Gamma**         | 0.1                 | Exponential Gap Elimination | 95%              | 9000       | 1124.97   | 0.16             | 17.14          | 100                 |
|                  |                     | Sequential Halving          | —                | 7674.69    | 958.97    | 0.72             | 69.08          | 52.76               |
|                  | 0.1                 | Exponential Gap Elimination | 90%              | 9000       | 1124.85   | 0.16             | 17.12          | 100                 |
|                  |                     | Sequential Halving          | —                | 9000       | 1124.85   | 0.96             | 99.96          | 100                 |

---

## 🧠 Current Focus

We are now running the algorithms across **5000+ simulated cases** per scenario to assess how well they perform in different settings.

The goal is to systematically analyze their **robustness and efficiency** under various conditions.

---

## 📁 Structure

- `scripts/` → Core algorithm code  
- `notebooks/` → Exploratory runs & visualization  
- `results/` → Simulation outputs and summaries  
- `data/` → Synthetic data (if stored) 

---

## 🚧 Work in Progress

We’ll be adding:
- Comparative graphs & stats
- Final summaries of performance

Stay Tuned!

# 🎯 Exploration of Multi-Armed Bandit Algorithms

This project explores the **Multi-Armed Bandit** problem with a focus on **Best Arm Identification (BAI)**. We implement and compare three algorithms:

- **Sequential Halving (SH)**
- **Exponential-Gap Elimination (EGE)**
- **Median Elimination (ME)**

---

## 🧪 What’s New

Since the last update, we have:

- **Added two additional performance metrics**:
  - **Standard Error (%) for Cost**
  - **Standard Error (%) for Confidence**
- **Extended experiments** to **real-time generated data** (no cap on pulls per arm) in addition to **pre-generated datasets**.
- Maintained the same 5 000-case simulation framework across both setups.

---

## 📊 Experimental Setups

### 1. Pre-Generated Data
- Four reward distributions: **Uniform, Normal, Mixture Normal, Gamma**
- **6 arms per run**
- **Cap**: 1 500 pulls per arm
- Logged metrics:
  - Average Pulls & Cost
  - Standard Error (%) for Cost
  - Average Confidence
  - Standard Error (%) for Confidence
  - Accuracy (%)
  - Stopping Early (%)

### 2. Real-Time Data Generation
- Same **5 000 cases** per distribution
- **No cap** on pulls per arm — algorithms decide when to stop
- Allows studying behaviour under unconstrained exploration

---

## 📈 Results (Summary)

### 1️⃣ Pre-Generated Data

| Distribution | Δ | Method | Target Conf./Cost* | Avg. Pulls | Avg. Cost | StdErr Cost (%) | Avg. Conf. | StdErr Conf. (%) | Accuracy (%) | Stopped Early (%) |
|--------------|---|--------|--------------------|------------|-----------|-----------------|------------|------------------|--------------|-------------------|
| Uniform | 0.1 | EGE | 95% | 9000 | 1125.06 | 0.01 | 0.17 | 3.15 | 16.78 | 100 |
| Uniform | 0.1 | SH | 1000 | 7677 | 959.37 | 0.07 | 0.83 | 0.57 | 86.46 | 51.38 |
| Uniform | — | ME | 95% | 9000 | 1125.06 | 0.01 | 0.34 | 1.96 | 34.22 | 100 |
| … | … | … | … | … | … | … | … | … | … | … | … |

<sub>*For SH, the value in this column denotes the **target budget** rather than confidence level.</sub>

---

### 2️⃣ Real-Time Data

Here, the cap is removed — notice how pull counts and costs change significantly.

| Method | About | Reward Gap | Target Conf./Cost | Avg. Pulls | Avg. Cost | StdErr Cost (%) | Avg. Conf. | StdErr Conf. (%) | Accuracy (%) | Stopped Early (%) |
|--------|-------|------------|-------------------|------------|-----------|-----------------|------------|------------------|--------------|-------------------|
| EGE | Avg. Arm Mean = 0.626, Avg. Std = 0.1 | 0.1 | 95% | 37897 | 4737.07 | 0.30 | 1.00 | 0.00 | 100 | 0 |
| SH | — | 0.1 | 1000 | 8000.07 | 999.94 | 0.00 | 0.83 | 0.64 | 15.94 | 81.64 |
| ME | Avg. Mean = 0.624, Avg. Std = 0.1 | 0.1 | 95% | 620672 | 77583.50 | 0.00 | 1.00 | 0.00 | 100 | 0 |
| EGE | Avg. Arm Mean = 0.625, Avg. Std = 0.1 | 0.1 | 90% | 42164.06 | 5270.42 | 0.30 | 1.00 | 0.00 | 100 | 0 |
| SH | — | 0.1 | 2000 | 15999.51 | 1999.94 | 0.00 | 0.84 | 0.62 | 16.52 | 81.58 |
| ME | Avg. Mean = 0.624, Avg. Std = 0.1 | 0.1 | 90% | 542356 | 67795.05 | 0.00 | 1.00 | 0.00 | 100 | 0 |

---

## 🧠 Next Steps

- Complete further **real-time runs** on all distributions
- **Visualize** the table above with scatter and bar plots (accuracy vs. cost, etc.)
- **Write an analysis section** in `reports/` summarising where each algorithm shines
- **Add unit tests** ensuring parity across implementations
- **Research and prototype a new algorithm** that can **jointly optimize for confidence and cost**, potentially outperforming current methods

---

## 🚧 Work in Progress

We’re iterating quickly — expect frequent updates as the real-time experiments expand, the new algorithm evolves, and plots land.

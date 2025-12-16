# Max-Profit-Problem
# Mars Land Development - Max Profit Algorithm

## 📋 Project Overview
This project contains a Python solution for the "Max Profit Problem" (Interview Assignment). The algorithm calculates the optimal mix of properties (Theatres, Pubs, and Commercial Parks) to build within a specific time constraint to maximize total earnings.

The solution utilizes **Dynamic Programming** to explore all possible building combinations and operational durations efficiently.

## 💡 The Problem
[cite_start]Mr. X owns a large strip of land in Mars Land[cite: 4]. He wants to develop properties to maximize his earnings over a period of `n` time units.

### Constraints & Rules:
* [cite_start]**Sequential Development:** Only one property can be developed at a time (no parallel building)[cite: 14].
* [cite_start]**Operational Earnings:** Money is earned only for the time a building is operational (Total Time - Build Time)[cite: 12].
* [cite_start]**Infinite Capacity:** Land area is infinite; the limiting factor is **Time**[cite: 5].

### Property Data
| Establishment | Build Time (Units) | Earnings (per unit) |
| :--- | :--- | :--- |
| **Theatre (T)** | 5 | $1500 |
| **Pub (P)** | 4 | $1000 |
| **Commercial Park (C)** | 10 | $2000 |
[cite_start]*(Data Source: [cite: 9-11, 13])*

---

## 🚀 Solution Approach
The problem is solved using a **Dynamic Programming (DP)** approach.

### The Algorithm
We treat this as a variation of the "Unbounded Knapsack Problem," but instead of filling a bag, we are filling a timeline.
1.  **State Definition:** Let `dp[t]` be the maximum profit achievable with `t` units of time.
2.  **Recurrence Relation:** For every time unit `t`, we check all building options `b`. If we build `b`, the profit is:
    $$\text{Profit} = (\text{Operational Time} \times \text{Rate}) + dp[\text{Remaining Time}]$$
    $$\text{Profit} = ((t - \text{cost}_b) \times \text{rate}_b) + dp[t - \text{cost}_b]$$
3.  **Optimal Mix:** We maintain a parallel structure to track the count of each building type that led to the optimal `dp[t]`.

---

## 💻 Installation & Usage

### Prerequisites
* Python 3.x

### Running the Code
1.  Clone the repository:
    ```bash
    git clone [https://github.com/yourusername/mars-land-profit.git](https://github.com/yourusername/mars-land-profit.git)
    ```
2.  Navigate to the directory:
    ```bash
    cd mars-land-profit
    ```
3.  Run the script:
    ```bash
    python max_profit.py
    ```

---

## 📊 Test Cases & Results
[cite_start]The algorithm has been verified against the provided test cases[cite: 19].

| Input (Time Units) | Expected Output | Calculated Output | Logic |
| :--- | :--- | :--- | :--- |
| **7** | $3000 | **$3000** | Build 1 Theatre (Operational 2 units) OR 1 Pub (Op 3 units). |
| **8** | $4500 | **$4500** | Build 1 Theatre (Operational 3 units). |
| **13** | $16500 | **$16500** | Build 2 Theatres. (T1 Op 8 units + T2 Op 3 units). |

---

## 📂 File Structure
```text
.
├── max_profit.py       # Main algorithm implementation
├── README.md           # Project documentation
└── Algorithm - Max Profit.pdf # Problem statement source

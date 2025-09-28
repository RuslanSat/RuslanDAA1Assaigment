# RuslanDAA1Assaigment
# Divide-and-Conquer Algorithms Project

## Overview
This project implements and analyses classic divide-and-conquer algorithms with careful recursion control.  
It measures performance metrics and compares empirical results with theoretical recurrence analysis.

## Implemented Algorithms (40%)
1. **MergeSort**  
   *Linear merge with reusable buffer and insertion-sort cutoff for small n.*  
   *Recurrence:* T(n) = 2T(n/2) + Θ(n) → **Θ(n log n)** (Master Theorem, Case 2).

2. **QuickSort**  
   *Randomised pivot selection; recurses on the smaller partition and iterates on the larger to guarantee a bounded stack (~O(log n)).*  
   *Expected Recurrence:* T(n) = T(k) + T(n−k−1) + Θ(n) → **Θ(n log n)** average case.

3. **Deterministic Select (Median-of-Medians)**  
   *Groups of 5, median-of-medians pivot, in-place partition; recurses only on the required side, preferring the smaller side.*  
   *Recurrence:* T(n) = T(n/5) + T(7n/10) + Θ(n) → **Θ(n)**.

4. **Closest Pair of Points (2D)**  
   *Sorts by x, splits recursively, checks the “strip” in y-order with a 7–8 neighbour scan.*  
   *Recurrence:* T(n) = 2T(n/2) + Θ(n) → **Θ(n log n)**.
   ## Metrics and Experiments
We collect:
* **Running time**
* **Recursion depth**
* **Comparisons and allocations**

Results are exported to CSV and visualised in plots of:
* `time vs n`
* `depth vs n`

The analysis discusses constant-factor effects such as CPU cache behaviour and Java GC overhead.
## Repository Workflow (GitHub)
**Branches**
* Step1-step9
* ver 1.0
* Commit Storyline**
* `init`: maven, junit5, README
* `feat(metrics)`: counters, depth tracker, CSV writer
* `feat(mergesort)`: baseline + buffer reuse + cutoff + tests
* `feat(quicksort)`: smaller-first recursion, randomized pivot + tests
* `refactor(util)`: partition, swap, shuffle, guards
* `feat(select)`: deterministic select (MoM5) + tests
* `feat(closest)`: divide-and-conquer + tests
* `feat(cli)`: parse args, run algorithms, emit CSV
* `bench(jmh)`: benchmark select vs sort
* `docs(report)`: master cases & AB intuition, plots
* `fix`: edge cases (duplicates, tiny arrays)
* `release`: v1.0
* ## How to Run
Build project

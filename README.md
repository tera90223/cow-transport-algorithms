# Greedy vs Brute Force vs Dynamic Programming (MIT 6.0002)
## 🚀 Part A: Cow Transport Algorithms: Greedy vs Brute Force
This project implements and compares Greedy and Brute Force algorithmic strategies to solve the classic **Cow Transport Problem** from MIT 6.0002: *Introduction to Computational Thinking and Data Science*.

The problem involves transporting cows with different weights using the fewest number of trips without exceeding a set weight limit (10 units per trip).

---

## 🧠 Algorithms Implemented

### ✅ Greedy Algorithm
- Selects the heaviest available cow that fits into the current trip.
- Fills a trip until the weight limit is reached, then starts a new trip.
- Fast and simple, but doesn't guarantee the most efficient solution.

### 🔍 Brute Force Algorithm
- Generates all possible partitions of the cow list into valid trips.
- Evaluates each partition to find the one with the minimum number of trips.
- Guarantees optimality but is computationally expensive for larger inputs.

---

## 📊 Results

| Algorithm     | Trips Used | Runtime (sec)        |
|---------------|------------|----------------------|
| Greedy        | 6          | ~0.00005             |
| Brute Force   | 5          | ~0.53                |

- The **Greedy Algorithm** was significantly faster.
- The **Brute Force Algorithm** found a better (optimal) solution.
- *Caveat*: The runtime above is based on my first run. The code has been ran more than once, and the runtime will vary.

---

## 🔍 Understanding the `partitions()` Generator

This function powers the brute-force solution by generating **all unique partitions** of a set of cows.

### How it works:
- Uses **bitwise logic** to split cows into two groups in all unique ways.
- Recursively partitions one subset to build all full combinations.
- Uses `yield` to return each partition lazily as a generator—saving memory and enabling streaming.

### Why it's useful:
- Enables brute-force evaluation without storing all combinations at once.
- Helps demonstrate how generators and recursion can be combined to solve complex combinatorics problems efficiently.

---

## 🛠️ Skills Used

- Algorithm analysis and comparison  
- Recursive function design  
- Bitwise operations for partitioning  
- Python generators and `yield`  
- Performance benchmarking with `time`  
- Writing clean, well-commented code  
- Technical journaling and reflection  
- Git/GitHub version control and documentation

---

## 🔄 Part B – Dynamic Programming Approach

This section explores how dynamic programming compares to greedy and brute-force strategies for solving the minimum egg problem (similar to the unbounded knapsack problem).

I implemented a **bottom-up dynamic programming solution** to find the minimum number of eggs needed to reach a target weight using unlimited quantities of the given egg weights.

### Highlights:
- Used a 1D memoization table:  
  `dp[w] = min(dp[w - e] + 1 for e in egg_weights if e <= w)`
- Avoids redundant computation by storing subproblem results
- Guarantees an optimal solution, unlike greedy
- Scales efficiently where brute force fails

This addition builds on Part A by showing how dynamic programming balances optimality and performance in ways that greedy or brute force alone cannot.

---

## 📚 Course Reference

This project is part of **MIT 6.0002 – Introduction to Computational Thinking and Data Science**  
You can find the full course on MIT OpenCourseWare:  
🔗 https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/

---

## 🧠 Personal Note

This project challenged me to move beyond implementation and really *understand* the logic behind each algorithm. I took time to explore recursion, generators, and bit manipulation to grasp how the brute-force partitioning works. Rather than just solving the problem, I used this as an opportunity to reflect on how I learn, where I get stuck, and how I grow.

This is part of a larger summer goal to deepen my understanding of algorithmic thinking and machine learning—and apply it meaningfully to real-world scientific problems like cancer data analysis.

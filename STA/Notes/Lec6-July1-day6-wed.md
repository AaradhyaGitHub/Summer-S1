# STA 013 — Elementary Statistics
## Lecture Notes — Day 6
**Professor Max**

---

> 📌 **Exam note from professor:** Practice problems mentioned for next exam:
> - **#1** Probability intersection
> - **#2** Probability distribution table
> - **#3** Dot plot or box plot
>
> Drill these problem types specifically.

---

## 1. Variance — Measuring Variability

> 📖 **Variance** is a measure of variability that uses **all** measurements in the data set. It measures the average squared deviation of the measurements about their mean.

### Notation

| Symbol | Meaning |
|---|---|
| $\sigma^2_x$ | **Population variance** |
| $s^2_x$ | **Sample variance** |
| $\mu_x$ | Population mean |
| $\bar{x}$ | Sample mean |
| $x_i$ | Individual observation (i = 1, 2, ..., n) |
| $N$ | Population size |
| $n$ | Sample size |

### Formulas

**Population variance:**
$$\sigma^2_x = \frac{\sum(x_i - \mu_x)^2}{N}$$

**Sample variance:**
$$s^2_x = \frac{\sum(x_i - \bar{x})^2}{n-1}$$

> ⚠️ **Why n−1 and not n?**
> The sample variance $s^2_x$ is often used to estimate the population variance $\sigma^2_x$. Dividing by $n-1$ (instead of $n$) produces a **better, less biased estimate** of the true population variance. This is a standard statistical correction.

> 📌 **Key properties of $s$ (standard deviation = $\sqrt{s^2_x}$):**
> - The value of $s$ is **always positive** (or zero).
> - The **larger** $s^2$ or $s$ is, the **more variable** the data set.

---

## 2. Computing Sample Variance — Step-by-Step

### Worked Example
**Data:** $x_1 = 2,\quad x_2 = 0,\quad x_3 = -1$ &nbsp;&nbsp;&nbsp; ($n = 3$, this is a **sample**)

**Step 1 — Compute the sample mean $\bar{x}$:**
$$\bar{x} = \frac{\sum x_i}{n} = \frac{2 + 0 + (-1)}{3} = \frac{1}{3}$$

**Step 2 — Build the deviation table:**

| $i$ | $x_i$ | $x_i - \bar{x}$ | $(x_i - \bar{x})^2$ |
|---|---|---|---|
| 1 | 2 | $2 - \frac{1}{3} = \frac{5}{3}$ | $\frac{25}{9}$ |
| 2 | 0 | $0 - \frac{1}{3} = -\frac{1}{3}$ | $\frac{1}{9}$ |
| 3 | −1 | $-1 - \frac{1}{3} = -\frac{4}{3}$ | $\frac{16}{9}$ |
| **Sum** | | | $\frac{25}{9} + \frac{1}{9} + \frac{16}{9} = \frac{42}{9} = \frac{14}{3}$ |

> ⚠️ **Note:** $42/9 = 14/3$ — same value, just simplified. Both are correct to write.

**Step 3 — Compute $s^2_x$:**
$$s^2_x = \frac{\sum(x_i - \bar{x})^2}{n-1} = \frac{14/3}{2} = \frac{14}{6} = \frac{7}{3} \approx 2.333$$

**Step 4 — Standard deviation:**
$$s_x = \sqrt{s^2_x} = \sqrt{\frac{7}{3}} \approx 1.528$$

---

## 3. Shortcut Formula for Sample Variance

> 📌 **This formula was repeated 3 times by the professor — important:**

$$s^2_x = \frac{\displaystyle\sum x_i^2 - \frac{(\sum x_i)^2}{n}}{n-1}$$

This is algebraically identical to the definition formula but avoids computing each individual deviation. Use this when you're given $\sum x_i^2$, $\sum x_i$, and $n$ directly.

### Worked Example — Given Summary Values

**Given:** $\sum x_i^2 = 10$, $\sum x_i = 2$, $n = 10$

$$s^2_x = \frac{10 - \frac{(2)^2}{10}}{10-1} = \frac{10 - \frac{4}{10}}{9} = \frac{10 - 0.4}{9} = \frac{9.6}{9} \approx 1.067$$

$$s_x = \sqrt{1.067} \approx 1.033$$

### Quick note on $\bar{x}$

$$\bar{x} = \frac{\sum x_i}{n}$$

If $\sum x_i = 50$ and $n = 10$, then $\bar{x} = 5$. This is just a reminder that $\bar{x}$ is always derivable from the given summary values — no need to treat it as a separate formula.

---

## 4. Units of Variance and Standard Deviation

- If data is measured in **cm**, variance has units **cm²** and standard deviation has units **cm**.
- This is why standard deviation ($s$) is often more interpretable than variance ($s^2$) — it's in the same units as the original data.

---

## 5. Tchebysheff's Theorem

> 📖 **Tchebysheff's Theorem:** Given a number $k \geq 1$ and a set of $n$ measurements, **at least** $1 - \frac{1}{k^2}$ of the measurements will lie within $k$ standard deviations of the mean.

$$P\left(\mu - k\sigma \leq x \leq \mu + k\sigma\right) \geq 1 - \frac{1}{k^2}$$

- Works for **any** distribution shape — no assumptions required.
- Can be applied to both samples ($\bar{x}$ and $s$) and populations ($\mu$ and $\sigma$).

### Key Results

| $k$ | Formula | At least... | Interval |
|---|---|---|---|
| $k = 2$ | $1 - \frac{1}{4}$ | **75%** | $\mu \pm 2\sigma$ |
| $k = 3$ | $1 - \frac{1}{9}$ | **≈ 88.9%** | $\mu \pm 3\sigma$ |

> 💡 Tchebysheff gives a **minimum guarantee** — the actual percentage could be higher depending on distribution shape.

---

## 6. The Empirical Rule (68-95-99.7 Rule)

> 📖 **The Empirical Rule** applies **only** when the distribution is approximately **mound-shaped (bell-shaped)**. Gives tighter estimates than Tchebysheff.

```
                    Empirical Rule — Bell Curve
                    ===========================

        0.15%  2.35%   13.5%    34%  34%   13.5%   2.35%  0.15%
          |------|--------|--------|----|----|--------|------|------|
        
                        .  . * * * .  .
                     .  *           *  .
                   . *               * .
                  .*                   *.
                 *|         68%         |*
               * |                     | *
             *   |        ←————→       |   *
           *     |                     |     *
    ......*......|.......................|......*......
         |       |                     |       |
       μ-2σ    μ-σ                   μ+σ    μ+2σ
                  \___________________/
                           95%
         \____________________________________________/
                           99.7%
```

| Interval | % of Measurements | Breakdown |
|---|---|---|
| $\mu \pm \sigma$ | **≈ 68%** | 34% on each side of mean |
| $\mu \pm 2\sigma$ | **≈ 95%** | 13.5% in each middle band beyond ±σ |
| $\mu \pm 3\sigma$ | **≈ 99.7%** | 2.35% in each outer band, 0.15% in each tail |

### Worked Example — Using the Empirical Rule

**Setup:** Symmetrical mound-shaped distribution, $\mu = 2$, $\sigma = 1$.

**Q1: What proportion of data lies between 1 and 3?**

$$1 = \mu - \sigma = 2 - 1 \qquad\qquad 3 = \mu + \sigma = 2 + 1$$

This is the $\mu \pm \sigma$ interval → **≈ 68%**

**Q2: What proportion of data is larger than 3?**

- 68% falls between 1 and 3 → 32% falls outside.
- By symmetry, that 32% splits evenly: **16% below 1, 16% above 3**.

$$P(x > 3) \approx 16\%$$

> 💡 **Symmetry trick:** For any mound-shaped distribution, anything outside a symmetric interval splits **50/50** — half below the left bound, half above the right bound. Start from the total (100%), subtract what you know (68%), divide the rest by 2.

---

## 7. Approximating the Standard Deviation

From Tchebysheff and the Empirical Rule, roughly 4–6 standard deviations span the full data range $R$:

$$s \approx \frac{R}{4} \quad \text{(range is small/moderate)}$$
$$s \approx \frac{R}{6} \quad \text{(range is large)}$$

> 📌 **You will be told whether to use R/4 or R/6.** This is an **approximation**, not an exact computation.

### Worked Example — Faculty Ages

Ages of 50 tenured faculty:
```
34 48 70 63 52 52 35 50 37 43 53 43 52 44 42 31 36 48 43 26
58 62 49 34 48 53 39 45 34 59 34 66 40 59 36 41 35 36 62 34
38 28 43 50 30 43 32 44 58 53
```

$$R = 70 - 26 = 44 \qquad s \approx \frac{44}{4} = 11$$

**Actual $s = 10.73$** — approximation is very close.

---

## 8. Z-Score

> 📖 **Z-score:** How many standard deviations a measurement lies away from the mean.

$$z = \frac{x - \bar{x}}{s} \quad \text{(sample)} \qquad \text{or} \qquad z = \frac{x - \mu}{\sigma} \quad \text{(population)}$$

| z-score | Meaning |
|---|---|
| Positive | Value is **above** the mean |
| Negative | Value is **below** the mean |
| 0 | Value **equals** the mean |
| 2 | Value is **2 standard deviations above** the mean |

---

## 9. Quartiles and IQR

> 📖 **Q1 (Lower Quartile):** Larger than 25% of the ordered measurements.
> 📖 **Q2 (Median):** Larger than 50% of the ordered measurements.
> 📖 **Q3 (Upper Quartile):** Larger than 75% of the ordered measurements.
> 📖 **IQR:** $Q3 - Q1$ — the range of the middle 50%.

### Position Formulas — Midpoint Rule

> ⚠️ This class uses the **midpoint rule**, NOT interpolation. The textbook may differ — use the midpoint rule as taught.

$$\text{Position of } Q1 = 0.25(n+1)$$
$$\text{Position of } Q2 = 0.50(n+1)$$
$$\text{Position of } Q3 = 0.75(n+1)$$

If the position is non-integer (e.g., 2.75), average the two surrounding observations.

### Worked Example

**Data:** 2, 10, 6, 1, 7, 3, 12, 0, 1, 3 &nbsp; ($n = 10$)

**Step 1 — Sort:**
```
Position:  1   2   3   4   5   6   7   8    9   10
Value:     0   1   1   2   3   3   6   7   10   12
```

**Step 2 — Q1:** Position = $0.25 \times 11 = 2.75$ → between positions 2 and 3 (both = 1)
$$Q1 = \frac{1+1}{2} = 1$$

**Step 3 — Q2:** Position = $0.50 \times 11 = 5.5$ → between positions 5 and 6 (both = 3)
$$Q2 = \frac{3+3}{2} = 3$$

**Step 4 — Q3:** Position = $0.75 \times 11 = 8.25$ → between positions 8 and 9 (7 and 10)
$$Q3 = \frac{7+10}{2} = 8.5$$

**Step 5 — IQR:**
$$IQR = 8.5 - 1 = 7.5$$

---

## 10. Box Plot (Box-and-Whisker Plot)

### Five-Number Summary

$$\text{Min} \quad Q1 \quad Q2\text{ (Median)} \quad Q3 \quad \text{Max}$$

### Fences

> 📌 **Formula will be provided on the exam — but Q1, Q2, Q3 must be correct or everything downstream is wrong.**

$$\text{Lower Fence} = Q1 - 1.5 \times IQR$$
$$\text{Upper Fence} = Q3 + 1.5 \times IQR$$

Data outside a fence = **outlier**, marked with **\***.

### Construction Rules

1. Draw a **box from Q1 to Q3**, with a line at **Q2**.
2. Whiskers extend to the **most extreme data point still inside the fence** — not to the fence itself.
3. Points outside the fence are plotted as **\*** — whisker does **not** touch the outlier.

### Worked Example — No Outliers

Data: $0, 1, 1, 2, 3, 3, 6, 7, 10, 12$ &nbsp;&nbsp; $Q1=1,\ Q2=3,\ Q3=8.5,\ IQR=7.5$

$$\text{Lower Fence} = 1 - 1.5(7.5) = -10.25 \qquad \text{Upper Fence} = 8.5 + 1.5(7.5) = 19.75$$

No data outside fences → **no outliers**. Left whisker → Min=0, Right whisker → Max=12.

```
                  Box Plot — No Outliers
                  ======================

   Min=0   Q1=1     Q2=3              Q3=8.5         Max=12
     |       |        |                  |               |
     |       +--------+------------------+               |
  ---+-------+        |                  +---------------+---
     |       +--------+------------------+               |
     |       |        |                  |               |
     0       1        3                8.5              12

  <---left whisker-->|<-------  box  ------->|<--right whisker--->

  Right whisker is longer → RIGHT SKEWED
```

### Worked Example — With Outlier

Lower fence = 3, Upper fence = 19. One data point beyond upper fence.

```
              Box Plot — With Outlier
              =======================

  LF=3  Q1=5    Q2=8         Q3=14    UF=19         *=23
   |     |        |              |       |              |
   |     +--------+--------------+       |
 --+-----+        |              +-------+          *
   |     +--------+--------------+       |
   |     |        |              |       |
   3     5        8             14      19             23

         |<------ box ---------->|
   |<-lw->|                      |<---- rw ---->|    * = outlier

  Whisker stops at last data point INSIDE fence (≤19), NOT at the outlier.
  Outlier (23) is plotted separately as *.
  Whisker does NOT connect to *.
```

> 💡 **Key rule:** If any data point falls outside a fence, the whisker on that side extends only to the **last value still inside the fence**, and the outlier floats separately as **\***.

---

## Summary of Key Formulas — Day 6

| Concept | Formula |
|---|---|
| Sample mean | $\bar{x} = \dfrac{\sum x_i}{n}$ |
| Sample variance (definition) | $s^2_x = \dfrac{\sum(x_i-\bar{x})^2}{n-1}$ |
| Sample variance (shortcut) | $s^2_x = \dfrac{\sum x_i^2 - (\sum x_i)^2/n}{n-1}$ |
| Standard deviation | $s = \sqrt{s^2_x}$ |
| Z-score | $z = \dfrac{x - \bar{x}}{s}$ |
| Q1 position | $0.25(n+1)$ |
| Q2 position | $0.50(n+1)$ |
| Q3 position | $0.75(n+1)$ |
| IQR | $Q3 - Q1$ |
| Lower fence | $Q1 - 1.5 \times IQR$ |
| Upper fence | $Q3 + 1.5 \times IQR$ |
| Approx. std dev | $s \approx R/4$ or $R/6$ |
| Tchebysheff $k=2$ | At least **75%** within $\mu \pm 2\sigma$ |
| Tchebysheff $k=3$ | At least **88.9%** within $\mu \pm 3\sigma$ |
| Empirical Rule | **68% / 95% / 99.7%** within $1\sigma / 2\sigma / 3\sigma$ |

# STA 013 — Elementary Statistics
## Lecture Notes — June 23 (Day 2)
**Professor Max**

---

## 1. Dotplots

> 📖 **Definition:** A **dotplot** is the simplest graph for quantitative data. It plots each measurement as a point along a horizontal axis, stacking points when a value is duplicated.

**Worked Example:** Data = 4, 5, 5, 7, 6 (sample size *n* = 5)

![Dotplot of the data 4, 5, 5, 7, 6](sta013_day2_images/dotplot.png)

> ❓ **Question raised in class:** *Is this data a population or a sample?*
>
> **Answer: Neither.** We don't have enough context to say. It is simply **data** at this point. You can only call something a "sample" once you've identified the **population** it's meant to represent — you cannot have a sample without first defining the population it came from.
>
> 💡 The professor has repeated this distinction multiple times across lectures — it is clearly a recurring exam concept. **Practice this distinction explicitly.**

---

## 2. Stem-and-Leaf Plots

> 📖 **Definition:** A **stem-and-leaf plot** is another simple graph for quantitative data. The data is divided into a **stem** (leading digit(s)) and a **leaf** (trailing digit).

### Padding Rule
To divide numbers with different digit-lengths consistently, pad with leading zeros so all numbers have the same number of digits.

**Example:** Data = 2, 10, 7 → pad to 2 digits each → 02, 10, 07
- Stem = left digit(s), Leaf = right digit

**Example:** Data = 0, 11, 300 → pad to 3 digits each → 000, 011, 300
- Stem = first two digits (00, 01, 30), Leaf = last digit

### Full Worked Example
Data: 90, 70, 70, 70, 65, 68, 60

**Step 1 — Sort:** 60, 65, 68, 70, 70, 70, 90

**Step 2 — Split into stem (tens digit) and leaf (ones digit):**

```
Stem | Leaf
-----|----------
  6  | 0  5  8
  7  | 0  0  0
  8  | (none)
  9  | 0
```

> ⚠️ **Note on the empty stem "8":** Even though there is no data between 80–89, the stem row is still listed with no leaves. This isn't arbitrary — it's a convention that **preserves the true shape and spacing of the distribution**. Omitting an empty stem would visually compress the gap and misrepresent the data.

> 📌 **Exam Alert:** Stem-and-leaf plot construction (sorting, padding, splitting into stem/leaf) **will be on the midterm.** Practice building these from raw data sets.

---

## 3. Interpreting Graphs: Location and Spread

**Location** = where the data is centered (on the horizontal axis).
**Spread** = how far the data extends out from that center.

> ❓ **Key guiding question (from slide):** *Where is the data centered on the horizontal axis, and how does it spread out from the center?*

### Shape Vocabulary

![Four histogram shapes: symmetric wide, right-skewed, symmetric narrow, left-skewed](sta013_day2_images/skew_shapes.png)

- **Unimodal:** *(corrected term — not "unit model")* A distribution with a **single peak / single mode**. The top-left and bottom-left shapes above are both unimodal and symmetric — there is one peak, and the data is balanced on both sides of it.
- **Right-Skewed (Right Tail):** More data is concentrated on the **left**, with a long trailing "tail" of fewer, more spread-out measurements extending to the **right**. The bulk/mode of the data sits on the left.
- **Left-Skewed (Left Tail):** The mirror image — data is concentrated on the **right**, with a tail trailing off to the **left**.
- **Spread comparison:** The top-left and bottom-left shapes are both symmetric and unimodal, but the **bottom-left has a smaller spread** — its values are more tightly clustered around the center, with less tail on either side, compared to the top-left.
- **Bimodal:** When a distribution has **two distinct peaks** (two local modes) rather than one. More generally, a distribution with multiple peaks is called **multimodal**.

---

## 4. Outliers

> 📖 **Definition:** An **outlier** is a data point that does not represent the rest of the data — it sits apart from the rest of the cluster, on its own.

> ⚠️ **Important wording distinction:** Until we've actually investigated *why* a point is separated from the rest, we should call it a **potential outlier**, not a confirmed outlier. We haven't verified the cause yet.

- Outliers are **very sensitive** — they can heavily distort summary statistics. Always **examine outliers** and try to understand *why* they occurred before deciding how to treat them.

### Example: Why Units/Scale Matter When Spotting Outliers
- **Salary data** (unit: dollars): e.g., $10,000 vs. $20,000,000 — large numbers, but easy to represent and compare visually because the scale is simple.
- **Lab measurement data** (unit: mg or similar): e.g., 0.001 vs. 0.000015943 — much harder to represent visually because **precision must be preserved**; small absolute differences can still be meaningful.

### Worked Example: Gear Diameter Quality Control

> A quality control process measures the diameter of a gear being made by a machine (in cm). The technician records 15 diameters, but inadvertently makes a typing mistake on the second entry.

**Recorded data (cm):**
1.991, **1.891**, 1.991, 1.988, 1.993, 1.989, 1.990, 1.988, 1.988, 1.993, 1.991, 1.989, 1.989, 1.993, 1.990, 1.994

![Gear diameter measurements with one outlier from a typing mistake](sta013_day2_images/gear_outlier.png)

Nearly all measurements cluster tightly around **1.988–1.994 cm**. The single value **1.891** sits far to the left, isolated from the rest — a clear **potential outlier**, caused here by a **typing mistake** (likely meant to be 1.991).

> 💡 This is a good real-world illustration of *why* we investigate outliers rather than just removing them blindly — here, the root cause is a data-entry error, not a true unusual measurement.

---

## 5. Histograms

> 📖 **Definition:** A **relative frequency histogram** for a quantitative data set is a bar graph in which the height of each bar shows how often (as a proportion, or relative frequency) measurements fall into a particular **class** or **subinterval**.

### Clarifying Bar Graphs vs. Histograms
- **Bar graphs** are generally used for **qualitative data** — *unless* you are comparing a quantitative variable across entirely different populations/categories (recall the Big Mac price example from Day 1).
- To represent **qualitative** data with a bar graph, gaps are left between bars.
- To represent **quantitative** data with a histogram, the gaps between bars are **closed** — bars touch, since the data is continuous along the number line.

### Key Terminology
> ⚠️ **Correct term: "bin"** (also called a **class**, **interval**, or **subinterval**) — *not* "bind" or "beam." A **bin** is the width of an individual subinterval used to group the data.

- All bins must have the **equal width** (same length).
- The number of bins is a judgment call — typically **choose between 5 and 12 bins**.
  - Too few bins → you lose detail (see nothing).
  - Too many bins → too much noise (see everything, no clear pattern).

### Step-by-Step Histogram Construction

**Data:** 2, 2, 1, 1, 4, 8, 5, 10 → **n = 8**

**Step 1 — Sort the data:**
1, 1, 2, 2, 4, 5, 8, 10

**Step 2 — Decide on the number of bins.**
For this example, the professor deliberately chose **3 bins** (even though 5–12 is the generally recommended range) to keep the arithmetic simple.

**Step 3 — Compute bin width:**

$$\text{Bin Width} = \frac{\text{Max} - \text{Min}}{\#\text{Bins}} = \frac{10 - 1}{3} = \frac{9}{3} = 3$$

**Step 4 — Use left-inclusion for each interval.**
> 📖 **Left-inclusion rule:** For an interval **[2, 4)** — the left endpoint **2 is included**, but the right endpoint **4 is NOT included** in that bin (it belongs to the next bin instead).

**Step 5 — Build the bin boundaries**, starting at the minimum value (1) and adding the bin width (3) repeatedly:

$$1,\ 4,\ 7,\ 10,\ 13$$
*(1 + 3 = 4, 4 + 3 = 7, 7 + 3 = 10, 10 + 3 = 13)*

**Step 6 — Count how many data points fall in each bin (left-inclusive):**

| Bin (interval) | Data points included | Frequency |
|---|---|---|
| [1, 4) | 1, 1, 2, 2 | 4 |
| [4, 7) | 4, 5 | 2 |
| [7, 10) | 8 | 1 |
| [10, 13) | 10 | 1 |

![Relative frequency histogram for data 1,1,2,2,4,5,8,10 with 3 bins of width 3](sta013_day2_images/histogram_example.png)

### Frequency Histogram vs. Relative Frequency Histogram
- The plain **histogram** (sometimes called a **frequency histogram**) shows the **raw counts** on the y-axis.
- A **relative frequency histogram** shows the **proportion** — divide every y-axis value by the total sample size, **n**.

> 💡 **For this professor specifically:** if he just says "histogram," he means the plain frequency version. If he says **"relative frequency histogram,"** simply take all the y-axis (frequency) values and divide each by **n**.

### Total Area = 1
Since relative frequencies must sum to 1, **the total area under a relative frequency histogram always equals 1**:

$$\frac{4}{8} + \frac{2}{8} + \frac{1}{8} + \frac{1}{8} = 1$$

### Reading Probabilities/Proportions off the Histogram
Using the example above (n = 8):

| Question | Calculation | Answer |
|---|---|---|
| Proportion of measurements between 1 and 4 | 4/8 | **4/8 = 1/2** |
| Proportion of measurements between 7 and 10 | 1/8 | **1/8** |
| Probability measurement is larger than 7 (i.e., 7 and up) | 1/8 + 1/8 | **2/8 = 1/4** |
| Probability measurement is smaller than 4 (i.e., 4 and below) | 4/8 | **4/8 = 1/2** |
| Probability measurement is between 4 and 7 | 2/8 | **2/8 = 1/4** |

> 📌 **Important generalization:** Based on a histogram's shape, we can describe the data as **skewed** or comment on where the **mean** likely falls relative to the **median**, just like in Section 3 above.

### Second Histogram Example (3 bars, bin width = 4 each)
Bin boundaries: 0, 4, 8, 12 → y-axis (relative frequency) heights: 0.2, 0.3, 0.5

| Question | Calculation | Answer |
|---|---|---|
| P(value < 4) | first bar height | **0.2**... *(note: check against given values — see flag below)* |
| P(4 ≤ value < 8) | middle bar height | **0.3 or 0.5** *(see flag below)* |

> ⚠️ **Flag for verification:** Your notes list the bin heights as 0.2, 0.3, 0.5 but then state P(smaller than 4) = 0.3 and P(between 4 and 8) = 0.5. This doesn't match a simple "first bar = first interval" reading — it's possible the bars were given in a different order than the bins, or a detail from the board wasn't fully captured. **Recommend double-checking this specific example against your photo/board notes before the exam**, since the other histogram examples in this lecture all follow the straightforward "each bar height = its interval's relative frequency" rule.

---

## 6. Introduction to Probability

### Relative Frequency vs. Probability

$$\text{Relative Frequency} = \frac{f}{n}$$

> 📌 **Key distinction:**
> - If you have a **population** → use **probability**.
> - If you have a **sample** → use **relative frequency**.

### Core Definitions

> 📖 **Experiment:** The process by which an observation (or measurement) is obtained.
> **Examples:** record an age, toss a die, record an opinion, toss 2 coins.

> 📖 **Simple Event:** The outcome that is observed on a single repetition of the experiment. Denoted by **E** with a subscript (e.g., E₁, E₂, ...).
> **Example:** Flip a coin → Heads is one simple event, Tails is another simple event. Each simple event has its own probability.

> 📖 **Sample Space (S):** The set of **all** simple events of an experiment.
> **Example:** For a fair coin toss, S = {H, T}, or equivalently S = {E₁, E₂}.

> ⚠️ **Wording trap to watch for:** If the professor says *"roll a die, what is the probability of getting a 1?"* — without specifying the die is fair, **we don't actually know** the probability (the die could be weighted/loaded). But if he says **"toss a *fair* die,"** then we can say P(1) = 1/6, because fairness guarantees equally likely outcomes.

> 📖 **Event:** A collection of **one or more** simple events.
> **Example (die toss):**
> - Event A = "an odd number" = {1, 3, 5}
> - Event B = "a number larger than 2" = {3, 4, 5, 6}

> 📖 **Mutually Exclusive:** Two events are mutually exclusive if, when one event occurs, the other **cannot** occur (and vice versa).

### Probability Formulas

**Long-run relative frequency interpretation** (conceptual definition of probability):

$$P(A) = \lim_{n \to \infty} \frac{f}{n}$$

**Equally-likely outcomes formula** (only valid when every simple event in the sample space is equally likely — e.g., a *fair* coin/die):

$$P(\text{event}) = \frac{\#\text{ of simple events in the event}}{\#\text{ of simple events in the sample space}}$$

> ⚠️ **Important distinction:** These are **two different (related) ideas** — the first is the theoretical definition of probability as a long-run limit; the second is a shortcut formula that only works under the **equally likely outcomes** assumption. This is exactly why the professor's "fair vs. not fair" wording trap above matters: the shortcut formula breaks down the moment outcomes aren't equally likely.

### Worked Examples (Fair Die)

Roll a fair die: S = {E₁, E₂, E₃, E₄, E₅, E₆}

**Example A:** Event A = "observe an even number" = {2, 4, 6}
$$P(A) = \frac{3}{6} = \frac{1}{2}$$

**Example B (version 1):** Event B = "observe a number larger than 2" = {3, 4, 5, 6}
$$P(B) = \frac{4}{6} = \frac{2}{3}$$

**Example B (version 2):** Event B = "observe a number larger than 1 and less than 5" = {2, 3, 4}
$$P(B) = \frac{3}{6} = \frac{1}{2}$$

> 📌 **Probability bounds (fundamental rules):**
> - $0 \le P(A) \le 1$ for any event A.
> - $P(S) = 1$ (the probability of the entire sample space is always 1).

### Worked Example: Two Coin Tosses

**Question:** Toss a fair coin twice. What is the probability of observing **at least one head**?

> 📌 **Exam Alert:** This *exact style* of question will be on the midterm — but the professor will very likely **change it from coins to something else**, and/or make the coin **unfair**.

**Setup:**
- Toss 1 → H or T
- Toss 2 → H or T
- Sample Space: S = {HH, HT, TH, TT}

**"At least one head"** includes: HH, HT, TH (all outcomes except TT)

$$P(\text{at least one head}) = \frac{3}{4}$$

> ⚠️ **Variation to expect on the exam:** Suppose the coin is *not* fair — e.g., P(H) = 0.4 and P(T) = 0.6. The professor is **"90% sure"** a version of this will appear on the exam using an **unfair coin**, and will use qualifying language like **"at least"** and **"at most."** When the coin is unfair, you **cannot** just count outcomes — you must multiply the actual probabilities of each individual outcome (e.g., P(HH) = 0.4 × 0.4, etc.) rather than assuming all 4 outcomes are equally likely.

---

## Summary of Key Takeaways — Day 2
- **Dotplots and stem-and-leaf plots** are simple ways to visualize quantitative data; stem-and-leaf requires consistent digit-padding and must include empty stems to preserve shape.
- Data is not automatically a "sample" — it only becomes a sample once a **population** has been defined.
- Distribution shape vocabulary: **unimodal**, **bimodal/multimodal**, **symmetric**, **right-skewed**, **left-skewed**, and **spread**.
- **Potential outliers** must be investigated, not just removed — they are often caused by real, identifiable issues (e.g., data entry errors).
- **Histograms** require equal-width **bins** (5–12 recommended), built using a **left-inclusive** interval rule; the **total area always equals 1** under a relative frequency histogram.
- **Probability** applies to populations; **relative frequency** applies to samples.
- The **equally-likely-outcomes formula** for probability only works when the experiment is explicitly **fair** — watch for wording traps ("a die" vs. "a *fair* die").
- Expect **midterm questions on**: stem-and-leaf construction, histogram construction (bins/left-inclusion), and a "fair coin"-style probability question reworked with an **unfair** scenario and "at least/at most" phrasing.
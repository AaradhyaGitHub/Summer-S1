# STA 013 — Elementary Statistics
## Lecture Notes — June 30 (Day 5)
**Professor Max**

> ⚠️ **Source note:** I missed this lecture — these notes are reconstructed from a friend's handwritten photos, not from being in class. Some board context (verbal explanations, exact exam-alert phrasing) may be missing compared to my other days' notes. Flagged wherever something in the handwriting was ambiguous.

---

## 1. Probability Distribution of a Discrete Random Variable

> 📖 **Definition:** The **probability distribution of a discrete random variable x** is a table (or listing) that pairs every possible value of *x* with its probability.

**General table form:**

| $x$ | $x_1$ | $x_2$ | $\dots$ | $x_n$ |
|---|---|---|---|---|
| $P(x)$ | | | | |

---

## 2. Mean of a Random Variable

> 📖 **Definition:** The **mean of x** (also called the **average of x**) is the long-run average value you'd expect if you repeated the experiment many times, weighted by how likely each outcome is.

$$\text{Avg}(x) = \mu_x = E_x = x_1 P(x_1) + x_2 P(x_2) + \dots + x_n P(x_n)$$

### Notation Equivalences
> ⚠️ **Notation to memorize — these all mean the same thing:**
> $$M \equiv \mu \quad (\text{"mu"})$$
> - $E_x$ = **Expected value** of $x$
> - $\sigma$ = **"sigma"**

---

## 3. Variance of a Random Variable

> 📖 **Definition (conceptual formula):**

$$\sigma_x^2 = (x_1 - \mu)^2 P(x_1) + (x_2 - \mu)^2 P(x_2) + \dots + (x_n - \mu)^2 P(x_n)$$

*(Variance of x)*

> 💡 **What variance measures:** Variance measures **how far your data is from the center**.

$$\text{Variance} = (\text{standard deviation})^2$$

### Shortcut Formula (Used in Practice)

> 📖 **In practice**, instead of the conceptual $(x-\mu)^2$ formula above, use this computational shortcut:

$$\sigma_x^2 = x_1^2 P(x_1) + x_2^2 P(x_2) + \dots + x_n^2 P(x_n) - \mu_x^2$$

> ⚠️ **Note:** This is algebraically the same formula as the conceptual one above — it's just expanded out and rearranged so you don't have to subtract $\mu$ from every single $x_i$ before squaring. This is the version to actually use when computing by hand.

---

## 4. Worked Example: Flip a Fair Coin Twice

**Setup:** Flip a fair coin 2 times. Define $x$ = the number of heads obtained.

### (a) Construct the probability distribution of x

**Step 1 — List all 4 equally likely outcomes and the value of x for each:**

| Outcome | $x$ | $P(x)$ |
|---|---|---|
| HH | 2 | 1/4 |
| HT | 1 | 1/4 |
| TH | 1 | 1/4 |
| TT | 0 | 1/4 |

**Step 2 — Combine outcomes that give the same value of x into the actual probability distribution table:**

| $x$ | 0 | 1 | 2 |
|---|---|---|---|
| $P(x)$ | 1/4 | 1/2 | 1/4 |

> 📌 **Rule reminder (carried over from Day 1):** A probability distribution table **always sums to 1** — here: $\frac{1}{4} + \frac{1}{2} + \frac{1}{4} = 1$. ✓

### (b) Compute $\mu_x$ and $\sigma_x$

**Mean:**

$$\mu_x = x_1 P(x_1) + x_2 P(x_2) + x_3 P(x_3)$$
$$= 0 \times \frac{1}{4} + 1 \times \frac{1}{2} + 2 \times \frac{1}{4}$$
$$= \frac{1}{2} + \frac{1}{2} = 1$$

$$\boxed{\mu_x = 1}$$

**Variance (using the shortcut formula from Section 3):**

$$\sigma_x^2 = \frac{x_1^2 P(x_1) + x_2^2 P(x_2) + x_3^2 P(x_3)}{} - \mu_x^2$$

$$= 0^2 \times \frac{1}{4} + 1^2 \times \frac{1}{2} + 2^2 \times \frac{1}{4} - (1)^2$$

$$= 0 + \frac{1}{2} + 1 - 1$$

$$\boxed{\sigma_x^2 = \frac{1}{2}}$$

> ⚠️ **Flag for verification:** The photo of this step has a stray mark that looks like "1²22" written near the $-\mu_x^2$ term — this appears to just be messy handwriting/scratch work and not an actual part of the calculation, since the final answer written directly after it is $\frac{1}{2} + 1 - 1 = \frac{1}{2}$, which is correct. Worth double-checking against your own copy if you have one, but the final boxed answer ($\sigma_x^2 = 1/2$) is right either way.

---

## Chapter 2: Data Collection

## 5. Sampling Variation

> 📖 **Core distinction:**
> - **Population values are fixed.**
> - **Sample values are random.**

> 💡 This connects back to Day 1's population vs. sample distinction — the population doesn't change depending on who measures it, but *which* sample you happen to draw (and therefore what values you get) changes every time due to chance.

---

## 6. Arithmetic Mean and Summation Notation

> 📖 **Definition:**

$$\bar{x} = \frac{\sum x_i}{n} \qquad \bar{x} \equiv \text{"x-bar"}$$

- $n$ = number of measurements.
- $\sum x_i$ = sum of all measurements.

### Reading Summation Notation

$$\sum_{i=1}^{10} x_i = x_1 + x_2 + x_3 + \dots + x_9 + x_{10}$$

- **Bottom of the $\Sigma$** ($i = 1$) → **starting index**.
- **Top of the $\Sigma$** ($10$) → **ending index**.

### Worked Example — Basic Sum

**Given:** $x_1 = 2,\ x_2 = -1,\ x_3 = 0$

$$\sum_{i=1}^{3} x_i = x_1 + x_2 + x_3 = 2 + (-1) + 0 = 1$$

### Worked Example — Sum of Squares

$$\sum_{i=1}^{3} x_i^2 = x_1^2 + x_2^2 + x_3^2 = (2)^2 + (-1)^2 + (0)^2 = 4 + 1 + 0 = 5$$

### Worked Example — Sum, Then Subtract a Constant

> ⚠️ **Important distinction to notice** — this is different from the next example below. Here, the constant is subtracted **once, at the end**, *outside* the summation:

$$\left(\sum_{i=1}^{3} x_i\right) - 3 = (x_1 + x_2 + x_3) - 3 = 2 + (-1) + 0 - 3 = 1 - 3 = -2$$

### Worked Example — Constant Subtracted Inside the Summation

> ⚠️ **Compare directly to the example above** — here the $-3$ is **inside** the summation, so it gets subtracted from **each individual term** before adding them up. This gives a different answer than subtracting 3 only once at the end:

$$\sum_{i=1}^{3} (x_i - 3) = (x_1 - 3) + (x_2 - 3) + (x_3 - 3)$$
$$= (2-3) + (1-3) + (0-3)$$
$$= -1 - 2 - 3 = -6$$

> 💡 **Takeaway:** $\sum (x_i - 3) \ne \left(\sum x_i\right) - 3$. Whether the constant is inside or outside the summation symbol completely changes the arithmetic ($-6$ vs. $-2$ here) — pay close attention to parentheses placement when reading/writing summation expressions.

### Worked Example — Expression Involving x Inside the Summation

$$\sum_{i=1}^{3} (2 - x_i)^2 = (2-x_1)^2 + (2-x_2)^2 + (2-x_3)^2$$
$$= (2-2)^2 + (2-1)^2 + (2-0)^2$$
$$= 0 + 1 + 4 = 5$$

> 📌 **Skill being built here:** These four summation examples in a row are clearly designed to drill the difference between: summing plain $x_i$, summing $x_i^2$, subtracting a constant **outside** vs. **inside** the sum, and summing an **expression** of $x_i$ rather than $x_i$ itself. Expect a summation-notation question that tests whether you can tell these apart.

---

## 7. Measures of Center: Median

### Worked Example

**Data:** 4, 1, 6, 7

**Step 1 — Sort:** 1, 4, 6, 7

**Step 2 — Find the position of the median:**

$$\text{Position} = 0.5(n+1) = 0.5(4+1) = 0.5 \times 5 = 2.5$$

> 💡 The median sits at **position 2.5**, meaning it's located **between the 2nd and 3rd observations** in the sorted data (since 2.5 falls halfway between position 2 and position 3).

**Step 3 — Apply the midpoint rule:**

> 📖 **Midpoint rule:** When the median position isn't a whole number, take the **average of the two surrounding values**.

$$\text{Median} = \frac{4+6}{2} = \frac{10}{2} = \boxed{5}$$

---

## 8. Mode

> 📖 **Definition:** The **mode** is the measurement that occurs **most frequently**.

> 📖 **Bimodal:** A distribution with **two modes** (two values that tie for most frequent).

---

## 9. When to Use Median vs. Mean

> 📌 **Guidelines:**
> - When the distribution is **skewed**, the **median** is often preferred over the mean.
> - The median is **robust** (unaffected by outliers) — this is precisely *why* it's preferred for skewed data, since skewed distributions typically have extreme values pulling the mean away from where most of the data actually sits.

> 💡 **Connects back to Day 2:** This is the same robustness idea from the outliers discussion — a single extreme/mistaken value can heavily distort the **mean**, but the **median** barely moves.

---

## 10. Mean vs. Median Under Different Skew Patterns

> 📖 **Rules to memorize:**

$$\text{Symmetric:} \quad \text{Mean} = \text{Median}$$
$$\text{Skewed Right:} \quad \text{Mean} > \text{Median}$$
$$\text{Skewed Left:} \quad \text{Mean} < \text{Median}$$

> 💡 **Why this makes sense:** In a right-skewed distribution, the long tail of large, spread-out values on the right pulls the **mean** upward, while the **median** — being based on position/rank rather than magnitude — isn't dragged by how extreme the tail values are. Same logic in reverse for left-skewed. This directly ties back to the **right-skewed / left-skewed** shape vocabulary from Day 2, Section 3.

> 📌 **Likely exam connection:** Given a histogram or dotplot shape, you should be able to say **immediately** whether mean > median, mean < median, or mean = median, without being given the actual numbers — just from the skew direction. This was previewed back in Day 2 ("we can describe... where the mean likely falls relative to the median") and now has the exact rule attached to it.

---

## Summary of Key Takeaways — Day 5

- **Probability distribution of a discrete r.v.**: a table pairing each value of $x$ with $P(x)$; probabilities always sum to 1.
- **Mean of x**: $\mu_x = E_x = \sum x_i P(x_i)$ — same idea as "expected value."
- **Variance of x**: conceptual formula $\sum (x_i-\mu)^2 P(x_i)$, but use the **shortcut**: $\sum x_i^2 P(x_i) - \mu_x^2$ for actual computation.
- Coin-flip worked example: for $x$ = # heads in 2 flips, $\mu_x = 1$, $\sigma_x^2 = \frac{1}{2}$.
- **Chapter 2 begins:** population values are fixed, sample values are random.
- **Summation notation** ($\sum x_i$): starting index on bottom, ending index on top. Critical distinction — a constant subtracted **inside** vs. **outside** the summation gives different results ($\sum(x_i-3) \ne (\sum x_i) - 3$).
- **Median**: sort data, find position via $0.5(n+1)$, use midpoint rule (average the two middle values) if the position isn't a whole number.
- **Mode**: most frequent value; **bimodal** = two modes.
- **Median is robust to outliers** — preferred over the mean for skewed distributions.
- **Skew rules**: Symmetric → Mean = Median; Skewed Right → Mean > Median; Skewed Left → Mean < Median.

---

## ⚠️ Gaps / Things to Confirm With Professor or Classmates

Since I wasn't in class for this one, flagging a few things that are worth double-checking against the actual lecture (unlike my other notes, I can't cross-reference against my own memory of what was said):

1. Whether there was a **formal exam alert** given for this lecture's content (summation notation, median/mode, or the coin-flip variance example) — my other four days consistently have explicit "will be on the exam" flags from the professor, and none were visible in these photos, so it's unclear whether that's because none were given, or because it happened at a point not captured in the pictures.
2. Whether **Chapter 2** continues directly from where these notes leave off (median/mode/skew) into new material like range or standard deviation — worth asking a classmate what came right after, since the photos end mid-chapter.
3. The stray "1²22" mark in the variance calculation (Section 4) — confirmed it doesn't affect the final answer, but flagging in case it was meant to represent something I'm not accounting for.

# STA 013 — Elementary Statistics
## Lecture Notes — June 24 (Day 3)
**Professor Max**

---

> 📌 **EXAM ALERT:** The following will be on Monday's exam: **experimental unit, variable, continuous, discrete, permutations, combinations** — and their **definitions** specifically will be tested, not just calculations.

> 📌 **EXAM ALERT:** **Conditional probability will NOT be on Monday's exam.** It will appear on the *next* exam. (Still recorded in full below for future reference.)

---

## 1. Continuing with Probability — The Basics

- **A** denotes an event.
- **P(A)** is the *likelihood* that we observe event A.
  - If we **never** observe the event, P(A) = **0**.
  - If we **always** observe the event, P(A) = **1**.

> 📖 **Fundamental rule:** $0 \le P(A) \le 1$ — **always**, for any event A.

---

## 2. Parameter vs. Statistic

> ⚠️ Professor explicitly noted: **Parameter will NOT be on Monday's exam** — included here for completeness/future reference.

> 📖 **Parameter:** A characteristic measured on a **population**.
> 📖 **Statistic:** A characteristic measured on a **sample**.

> 💡 **Simple rule of thumb:** Anything you measure on a **sample** → **statistic**. Anything you measure on the **population** → **parameter**.

---

## 3. With Replacement vs. Without Replacement

**Setup:** A bowl has 3 M&Ms: 1 Red, 1 Blue, 1 Green.

- P(any specific color on a single draw) = **1/3** for each color.

### Question: If we select 2 M&Ms randomly, what is the probability that *at least 1* is red?

First, define the event: **A = "an M&M is red."**

### With Replacement
"With replacement" means: pick one, observe it, **put it back**, then pick again. Each draw is **independent**, and probabilities are **multiplied**.

**Sample space (with replacement)** — order matters here because each pick is its own independent trial, and we can repeat colors:
$$S = \{RR,\ RB,\ RG,\ BR,\ BB,\ BG,\ GR,\ GB,\ GG\}$$
*(9 total outcomes — this matches the simplified listing from lecture: {RR, RB, RG, BG, BB, GG} only shows 6 of the 9 if we don't separately list reversed orders, but with independent replacement draws, all 9 ordered outcomes are technically possible.)*

> ⚠️ **Clarifying the "1/9" comment from lecture:** $\left(\frac{1}{3}\right) \times \left(\frac{1}{3}\right) = \frac{1}{9}$ — but this is **P(both red)**, not **P(at least one red)**. These are two different questions:

| Question | Calculation | Answer |
|---|---|---|
| P(both are red) | $\frac{1}{3} \times \frac{1}{3}$ | **1/9** |
| P(at least one is red) | $1 - P(\text{no red at all}) = 1 - \left(\frac{2}{3}\right)^2$ | **5/9** |

> 💡 **Why subtract from 1?** "At least one red" is the complement of "no red at all" (i.e., both non-red). It's much easier to calculate the complement ($\frac{2}{3} \times \frac{2}{3} = \frac{4}{9}$) and subtract from 1: $1 - \frac{4}{9} = \frac{5}{9}$.

### Without Replacement
Now we pick 2 candies **at once** (or equivalently, pick one and don't put it back before picking the second). Each individual pick is no longer independent of the other.

**Sample space (without replacement):**
$$S = \{RB,\ RG,\ BR,\ BG,\ GB,\ GR\}$$
*(6 total outcomes — no repeated letters, since a candy can't be drawn twice.)*

> P(at least one red) here = $\frac{4}{6} = \frac{2}{3}$ (the outcomes RB, RG, BR, GR all contain a red; only BG and GB do not).

---

## 4. Counting Rules

> 📖 **General probability formula using counting:**
$$P(A) = \frac{n_A}{N} = \frac{\text{number of simple events in } A}{\text{total number of simple events}}$$

### The mn-Rule (Multiplication Rule)
> 📖 **Definition:** If an experiment has **2 stages**, where stage 1 can happen in **m** ways and stage 2 can happen in **n** ways, then the total number of ways both stages can happen together is $m \times n$.

**Example:** Building an outfit from a closet containing:
- 4 pairs of pants
- 3 shirts
- 6 hats

**Total possible outfits:**
$$4 \times 3 \times 6 = 72$$

*(This extends the 2-stage mn-rule to 3 stages — multiply across all stages.)*

---

## 5. Permutations

> 📖 **Definition:** A **permutation** is the number of ways to **arrange** *n* distinct objects, taking *r* of them at a time, **where order matters**.

$$_nP_r = \frac{n!}{(n-r)!}$$

**Requirement:** $r \le n$

### Worked Example: Red, Blue, Green — choose 2
$n = 3,\ r = 2 \Rightarrow n - r = 1$

$$_3P_2 = \frac{3!}{1!} = \frac{1 \times 2 \times 3}{1} = 6$$

### Factorial Reminder
$$n! = 1 \times 2 \times 3 \times \cdots \times (n-1) \times n$$
*(equivalently, written in reverse: $n \times (n-1) \times (n-2) \times \cdots \times 2 \times 1$)*

> 📖 **Special case:** $0! = 1$ *(by definition)*

### Worked Example: 3-Digit Lock Code
A lock uses digits 1, 2, 3, 4. How many possible 3-digit codes can be created (no repeated digits, **order matters**)?

$n = 4,\ r = 3$

$$_4P_3 = \frac{4!}{(4-3)!} = \frac{4!}{1!} = \frac{1 \times 2 \times 3 \times 4}{1} = 24$$

**Total possible codes = 24**

### Worked Example: Assembly Order Testing
A lock has 5 parts that can be assembled in any order. A QA engineer wants to test every possible order for assembly efficiency. How many distinct orders are there?

$n = 5,\ r = 5$ *(using all 5 parts, order matters)*

$$_5P_5 = 5! = 1 \times 2 \times 3 \times 4 \times 5 = 120$$

**Total possible assembly orders = 120**

---

## 6. Combinations

> 📖 **Definition:** A **combination** is the number of ways to choose *r* objects from *n* distinct objects, where **order does NOT matter**.

$$_nC_r = \frac{n!}{r!\,(n-r)!}$$

### Worked Example
$n = 5,\ r = 2 \Rightarrow n - r = 3$

$$_5C_2 = \frac{5!}{2!\,3!}$$

### Worked Example: M&M Box — "Exactly 1 Red"

**Setup:** A box contains 4 red M&Ms and 2 green M&Ms (6 total). A child selects 2 M&Ms at random.

**Question: P(exactly 1 red)?**

**Step 1 — Total number of ways to select 2 M&Ms from the box (order doesn't matter):**

$n = 6,\ r = 2 \Rightarrow n-r = 4$

$$_6C_2 = \frac{6!}{2!\,4!} = \frac{6 \times 5 \times 4!}{2! \times 4!} = \frac{6 \times 5}{2} = \frac{30}{2} = 15$$

**Total possible 2-candy selections = 15**

**Step 2 — Number of ways to get *exactly* 1 red (and therefore exactly 1 green):**

"Exactly 1 red" means **1 red AND 1 green simultaneously** — so we choose 1 from the reds, **and** 1 from the greens, then multiply (this is the mn-rule again, nested inside the combinations problem):

$$_4C_1 \times {_2C_1} = 4 \times 2 = 8$$

> ⚠️ **Correction from lecture:** The in-class number "2" only accounted for the green side ($_2C_1 = 2$) and missed multiplying by the red side ($_4C_1 = 4$). Since both a red **and** a green must be chosen together, the two counts multiply rather than standing alone.

**Step 3 — Final probability:**

$$P(\text{exactly 1 red}) = \frac{_4C_1 \times {_2C_1}}{_6C_2} = \frac{8}{15}$$

> ✅ **This matches the worksheet's answer of 8/15.**

---

## 7. Set Operations: Union, Intersection, Complement

> 📖 **Union (A ∪ B):** All elements that are in **A or B** (or both).

**Example:**
$A = \{1, 2, 4, 6\}$
$B = \{1, 5, 2, 7\}$
$$A \cup B = \{1, 2, 4, 5, 6, 7\}$$

> 📖 **Intersection (A ∩ B):** Elements that are in **both A and B**.

Using the same sets:
$$A \cap B = \{1, 2\}$$

> 📖 **Complement (Aᶜ):** Everything in the sample space that is **NOT** in A. Denoted with a subscript/superscript "c."

### The Addition Rule
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Example setup:**
$S = \{1, 3, 5, 6, 7, 10\}$
$A = \{1, 3, 7\}$
$B = \{1, 5, 7\}$

---

## 8. Worked Example: Classifying Students

> Suppose there are students in a class, classified as follows:

| | Brown Hair | Not Brown Hair |
|---|---|---|
| **Male** | 20 | 40 |
| **Female** | 30 | 30 |

**Total sample size = 120**

Let **A = "Brown hair"** and **B = "Male."**

$$P(A) = \frac{50}{120} \quad \text{(20 Male-Brown + 30 Female-Brown)}$$
$$P(B) = \frac{60}{120} \quad \text{(20 Male-Brown + 40 Male-Not-Brown)}$$

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

> ⚠️ **Flag for verification:** In lecture, $P(A \cap B)$ was stated as **30/120**. However, based on the table above, the "Male AND Brown hair" cell is **20**, which would make $P(A \cap B) = 20/120$, not 30/120. Using 20/120 gives $P(A \cup B) = \frac{50}{120} + \frac{60}{120} - \frac{20}{120} = \frac{90}{120} = 0.75$. Using the lecture's stated 30/120 instead gives $P(A \cup B) = \frac{80}{120} \approx 0.667$. **Recommend double-checking this specific number against the board/slide** — the practice problems below use the table-consistent value (20/120) since it matches the actual data given, but flag this with your professor if the discrepancy matters for the exam.

### Practice (as requested in lecture):
$$P(A^c) = 1 - P(A) = 1 - \frac{50}{120} = \frac{70}{120}$$
$$P(B^c) = 1 - P(B) = 1 - \frac{60}{120} = \frac{60}{120} \quad \text{(this is the "Female" probability)}$$

---

## 9. Conditional Probability
> ⚠️ **Will NOT be on Monday's exam — will be on the next exam.** Recorded here for completeness.

> 📖 **Definition:**
$$P(A \mid B) = \frac{P(A \cap B)}{P(B)}$$
$$P(B \mid A) = \frac{P(A \cap B)}{P(A)}$$

### Worked Example: Two Fair Coin Tosses
- **A** = "Heads on the second toss" → P(A) = 0.5
- **B** = "Heads on the first toss" → P(B) = 0.5

**A and B are independent events** *(the outcome of the first toss has no effect on the second).*

### Worked Example: Pass/Fail Table

| | Pass | Fail |
|---|---|---|
| **Male** | 20 | 30 |
| **Female** | 10 | 20 |

**Total = 80**

Let **M = Male**, **P = Pass**.

$$P(M \cap P) = \frac{20}{80}$$
$$P(P) = \frac{30}{80} \quad \text{(20 Male-Pass + 10 Female-Pass)}$$

$$P(M \mid P) = \frac{P(M \cap P)}{P(P)} = \frac{20/80}{30/80} = \frac{20}{30} = \frac{2}{3}$$

> 💡 **Interpretation:** Given that a randomly selected student **passed**, the probability that the student is **male** is 2/3.

> 📌 This style of 2×2 table question (build the table, compute joint/marginal/conditional probabilities) is expected to be a recurring question format — practice constructing and reading these tables.

---

## Summary of Key Takeaways — Day 3
- **Exam-critical definitions** (will be tested directly): experimental unit, variable, continuous, discrete, permutations, combinations.
- **Parameter** = measured on population; **Statistic** = measured on sample. *(Not on Monday's exam.)*
- **With replacement** → draws are independent → multiply probabilities directly; sample space allows repeats.
- **Without replacement** → draws affect each other → sample space has no repeats.
- **"At least one"** problems are almost always easier solved via the **complement**: $1 - P(\text{none})$.
- **Permutations** ($_nP_r = \frac{n!}{(n-r)!}$): order **matters**.
- **Combinations** ($_nC_r = \frac{n!}{r!(n-r)!}$): order **does NOT matter**.
- When a problem requires multiple independent sub-choices (e.g., "1 red AND 1 green"), **multiply the separate combination counts together** — don't forget either side of the "and."
- **Union/Intersection/Complement** and the addition rule $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ are fair game for Monday's exam.
- **Conditional probability** is **not** on Monday's exam but will appear on the next one — practice 2×2 contingency tables now to be ahead of the curve.
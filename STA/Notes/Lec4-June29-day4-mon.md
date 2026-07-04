# STA 013 — Elementary Statistics
## Lecture Notes — Day 4
**Professor Max**

---

> 📌 **QUIZ TOMORROW:** 3 problems only — covers conditional probability, independence, and the material in this lecture.
> 📌 **NEXT EXAM:** Will include **one independent event question and one conditional probability question.** Both are flagged throughout these notes.

---

## 1. Probability Fundamentals — Quick Review

- If event A **always** occurs → $P(A) = 1$
- If event A **never** occurs → $P(A) = 0$
- Always: $0 \le P(A) \le 1$

> 📌 **Exam skill to build:** Practice identifying whether a word problem is asking for a **union**, **intersection**, or **complement** *without being told explicitly.* Train yourself to map the wording of the question to the correct operation before computing anything. The key phrases to internalize:

| Wording | Operation |
|---|---|
| "A or B" / "at least one of" | Union: $A \cup B$ |
| "A and B" / "both" / "A given B has occurred" | Intersection: $A \cap B$ |
| "not A" / "other than A" / "everything except A" | Complement: $A^c$ |
| "given that" / "we know that" / "if the person is a..." | Conditional: $P(A \mid B)$ |

---

## 2. Conditional Probability

> 📖 **Definition:** $P(A \mid B)$ means: **B has already occurred — it is known and observed.** Given that, what is the probability of A?

$$P(A \mid B) = \frac{P(A \cap B)}{P(B)}$$

$$P(B \mid A) = \frac{P(B \cap A)}{P(A)}$$

> ⚠️ **Wording trap (professor will use this on exam):** "If the person is a woman, the probability of being high risk is 8%" — this is stating $P(H \mid F) = 0.08$, not $P(F \mid H)$. The condition is the group you're told the person belongs to first ("is a woman"), and the event is what you're computing the probability of second ("high risk").

---

## 3. Symmetry Rules — Patterns to Internalize

These relationships are easy to mix up. Here are the ones that hold and the ones that don't:

### What IS symmetric (commutative):
$$A \cap B = B \cap A$$
$$A \cup B = B \cup A$$

Both intersection and union are **commutative** — order of A and B doesn't change the result.

### What is NOT symmetric:
$$P(A \mid B) \ne P(B \mid A) \quad \text{(in general)}$$

Conditional probability is **not commutative** — the condition and the event are in specific roles and swapping them gives a completely different quantity.

### Complement rules with conditional probability:
$$P(A^c \mid B) = 1 - P(A \mid B) \quad \checkmark \text{ (TRUE)}$$

> 💡 **Why this works:** Once B is fixed/observed, everything inside that "given B" world still has to sum to 1. So within the world where B has occurred, A and Aᶜ are still complementary.

$$P(A \mid B^c) \ne 1 - P(A \mid B) \quad \text{(NOT true in general)}$$

> 💡 **Why this fails:** Changing the condition from B to Bᶜ is changing the *world* you're working in entirely — you're no longer inside the "B occurred" world at all. The complement rule doesn't transfer across a change in condition.

### Independence relationships:
$$P(A \mid B^c) = P(A \mid B) \quad \text{only when A and B are independent}$$
$$P(B \mid A^c) = P(B \mid A) \quad \text{only when A and B are independent}$$

> 💡 **Why:** Independence means knowing B (or not knowing B, or knowing Bᶜ) gives you zero information about A. So $P(A \mid B) = P(A \mid B^c) = P(A)$ — the condition doesn't matter at all.

### The big pattern to internalize:

| Situation | Rule |
|---|---|
| Complement of event, same condition | $P(A^c \mid B) = 1 - P(A \mid B)$ ✓ |
| Same event, complement of condition | $P(A \mid B^c) \ne 1 - P(A \mid B)$ ✗ |
| Both independent | $P(A \mid B) = P(A \mid B^c) = P(A)$ |
| Swapping condition and event | $P(A \mid B) \ne P(B \mid A)$ in general |

---

## 4. Independence vs. Mutual Exclusivity

> 📌 **Exam alert:** Distinguishing these two concepts is explicitly flagged as exam material.

### Independence
> 📖 **Definition:** A and B are **independent** if knowing that one occurred gives you **zero information** about whether the other occurred.

Three equivalent ways to check independence:

$$P(A \cap B) = P(A) \cdot P(B)$$
$$P(A \mid B) = P(A)$$
$$P(B \mid A) = P(B)$$

All three are equivalent — if any one holds, all three hold.

### Mutual Exclusivity
> 📖 **Definition:** A and B are **mutually exclusive** if they **cannot both occur at the same time.**

$$P(A \cap B) = 0$$

### Why they are NOT the same thing (critical distinction):

| | Independent | Mutually Exclusive |
|---|---|---|
| Can both occur? | **Yes** — one doesn't affect the other | **No** — if one occurs, the other is impossible |
| $P(A \cap B)$ | $P(A) \cdot P(B)$ (not zero, unless one has P=0) | **= 0** always |
| $P(A \mid B)$ | $= P(A)$ (knowing B tells you nothing) | $= 0$ (if B occurred, A is impossible) |

> 💡 **The key insight:** Mutually exclusive events are actually **maximally dependent** — knowing B occurred tells you with certainty that A did NOT occur. That's the opposite of independence. If two events are mutually exclusive and both have positive probability, they **cannot** be independent.

---

## 5. Dependence and the Multiplication Rule

> 📖 **General multiplication rule (works for ANY two events, dependent or not):**
$$P(A \cap B) = P(A \mid B) \cdot P(B)$$
$$P(A \cap B) = P(B \mid A) \cdot P(A)$$

> 📖 **Special case — when A and B are independent:**
$$P(A \cap B) = P(A) \cdot P(B)$$

> 💡 **Why the general rule works:** $P(A \mid B) = \frac{P(A \cap B)}{P(B)}$ — multiply both sides by $P(B)$ and you get $P(A \cap B) = P(A \mid B) \cdot P(B)$. It's just rearranging the conditional probability formula.

---

## 6. Worked Example: High Risk Heart Attack

**Setup:** In a certain population, 10% of people can be classified as high risk for a heart attack. Three people are randomly selected.

**Question:** What is the probability that **exactly one** of the three is high risk?

**Define:**
- $H$ = high risk, $P(H) = 0.10$
- $N$ = not high risk, $P(N) = 0.90$

**Key assumption:** The three selections are **independent** (selecting one person doesn't affect the others).

**Step 1 — List all arrangements with exactly one high-risk person:**

| Arrangement | Who is high risk | Probability |
|---|---|---|
| HNN | Person 1 | $0.10 \times 0.90 \times 0.90 = 0.081$ |
| NHN | Person 2 | $0.90 \times 0.10 \times 0.90 = 0.081$ |
| NNH | Person 3 | $0.90 \times 0.90 \times 0.10 = 0.081$ |

**Step 2 — Add them up** (these three arrangements are mutually exclusive — only one can be the actual outcome):

$$P(\text{exactly 1 high risk}) = 0.081 + 0.081 + 0.081 = 0.243$$

**Shortcut:** Since all three arrangements have the same probability by symmetry:
$$P(\text{exactly 1 high risk}) = 3 \times (0.10)(0.90)^2 = 3 \times 0.081 = 0.243$$

> 💡 **Why multiply within each arrangement?** Because the three people are **independent** — so joint probabilities are computed by multiplying. This is the general multiplication rule under independence.
> 
> **Why add the three arrangements?** Because HNN, NHN, and NNH are **mutually exclusive** outcomes — only one of them can actually happen — so we add their probabilities.

---

## 7. Worked Example: High Risk Female

**Setup (continuing from above):** 49% of the population is female. Of the female patients, 8% are high risk.

**Question:** What is the probability that a randomly selected person is **both** high risk **and** female?

**Given:**
$$P(F) = 0.49$$
$$P(H \mid F) = 0.08 \quad \text{"Of the female patients, 8\% are high risk"}$$

> ⚠️ **Wording alert (professor will test this phrasing):** "If the person is a woman, the probability of high risk is 8%" = $P(H \mid F) = 0.08$. The condition is always the group named first ("is a woman"), and the event is what you're finding the probability of ("high risk").

**"High risk AND female" = $P(H \cap F)$ — use the multiplication rule:**

$$P(H \cap F) = P(H \mid F) \cdot P(F) = 0.08 \times 0.49 = 0.0392$$

> ⚠️ **Why use $P(H \mid F) \cdot P(F)$ and NOT $P(F \mid H) \cdot P(H)$?**
> Both formulas are mathematically equivalent (both give $P(H \cap F)$), but $P(F)$ is the value **given directly in the problem** (49%), while $P(F \mid H)$ is not given and would require extra work to compute. Always use the version where the values you already know plug in cleanly.

> 📌 **NOTE:** The Law of Total Probability and Bayes' Rule are **NOT covered in this course.**

---

## 8. Random Variables

> 📖 **Definition:** A **random variable (RV)** is a quantitative variable $x$ whose value is determined by the outcome of a random experiment — i.e., it takes on different values by chance.

Random variables can be **discrete** or **continuous** (same discrete/continuous distinction from Day 1).

**Examples:**
- $x$ = SAT score for a randomly selected student
- $x$ = number of people in a room at a randomly selected time of day
- $x$ = number on the upper face of a randomly tossed die
- $x$ = face observed when flipping a fair coin (coded as 0/1)

---

## 9. Worked Example: Sum of Two Dice — Probability Distribution Table

**Setup:** Roll 2 fair dice, record $x$ = sum of the two faces.

**Step 1 — Total outcomes:** Each die has 6 faces → $6 \times 6 = 36$ total equally likely outcomes.

**Step 2 — Count outcomes for each possible sum:**

The possible sums range from 2 (1+1) to 12 (6+6). For each sum, count how many of the 36 outcomes produce it:

| $x$ (Sum) | Ways to get it | Frequency | $P(X = x)$ |
|---|---|---|---|
| 2 | (1,1) | 1 | $\frac{1}{36} \approx 0.028$ |
| 3 | (1,2),(2,1) | 2 | $\frac{2}{36} = \frac{1}{18} \approx 0.056$ |
| 4 | (1,3),(2,2),(3,1) | 3 | $\frac{3}{36} = \frac{1}{12} \approx 0.083$ |
| 5 | (1,4),(2,3),(3,2),(4,1) | 4 | $\frac{4}{36} = \frac{1}{9} \approx 0.111$ |
| 6 | (1,5),(2,4),(3,3),(4,2),(5,1) | 5 | $\frac{5}{36} \approx 0.139$ |
| 7 | (1,6),(2,5),(3,4),(4,3),(5,2),(6,1) | 6 | $\frac{6}{36} = \frac{1}{6} \approx 0.167$ |
| 8 | (2,6),(3,5),(4,4),(5,3),(6,2) | 5 | $\frac{5}{36} \approx 0.139$ |
| 9 | (3,6),(4,5),(5,4),(6,3) | 4 | $\frac{4}{36} = \frac{1}{9} \approx 0.111$ |
| 10 | (4,6),(5,5),(6,4) | 3 | $\frac{3}{36} = \frac{1}{12} \approx 0.083$ |
| 11 | (5,6),(6,5) | 2 | $\frac{2}{36} = \frac{1}{18} \approx 0.056$ |
| 12 | (6,6) | 1 | $\frac{1}{36} \approx 0.028$ |
| **Total** | | **36** | **1.000** ✓ |

> 💡 **Pattern to notice:** The frequency column forms a triangle — it goes up by 1 from sum=2 to sum=7, then back down by 1 from sum=7 to sum=12. Sum = 7 is the **most likely single outcome** ($P = 1/6$), and the distribution is **symmetric** around 7. This makes the distribution **unimodal** (one peak at 7) and **symmetric** — concepts from Day 2.

> 📌 **Sanity check:** All probabilities must sum to 1 — they do ✓ (this is the "sum of relative frequencies = 1" rule from Day 1 applied to a probability distribution).

---

## Summary of Key Takeaways — Day 4

- Map question **wording → operation** before computing: "or/at least one" → union; "and/both" → intersection; "not" → complement; "given that/if" → conditional.
- $P(A^c \mid B) = 1 - P(A \mid B)$ ✓ but $P(A \mid B^c) \ne 1 - P(A \mid B)$ ✗ — complementing the **event** vs. complementing the **condition** are completely different operations.
- **Independent ≠ Mutually Exclusive** — mutually exclusive events with positive probability are actually maximally *dependent*.
- General multiplication rule: $P(A \cap B) = P(A \mid B) \cdot P(B)$ — simplifies to $P(A) \cdot P(B)$ only under independence.
- When computing $P(A \cap B)$ from a word problem, use whichever version of the formula plugs in values that are directly given.
- A **random variable** is just a quantitative variable whose value is determined by a random experiment — it can be discrete or continuous.
- The sum-of-two-dice table is a **probability distribution** — all probabilities sum to 1, the shape is symmetric and unimodal peaking at 7.
- **Law of Total Probability and Bayes' Rule are NOT in this course.**
- **Next exam:** One independence question, one conditional probability question.

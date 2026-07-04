# STA 013 — Elementary Statistics
## Lecture Notes — June 22
**Professor Max**

---

> ⚠️ **ANNOUNCEMENT:** The Final Exam has been moved to **Tuesday, July 28th** (originally July 29th). Same time as regular class meeting time.

---

## 1. Introduction — Why Statistics?

- **Statistics** and **Probability** are complementary fields.
- This course begins with **Statistics**, because Statistics exists *because of data*.
- **Statistics** = the science of data: organizing, analyzing, and summarizing data.
- The central theme underlying all of statistics is **uncertainty**.

---

## 2. Sampling: The Foundation of Statistics

**Sampling** is the process of obtaining data. It is one of the most fundamental concepts in statistics.

In any statistical problem, a set of measurements (data) — a **sample** — is drawn from a much larger body of measurements, called the **population**.

> ❓ **Exam Alert (will be on the midterm):** *What is the difference between a population and a sample?*

### Population
- The entire target group of interest.
- Can be very large or very small — it depends on the question being asked.
- **Examples:** this class, all U.S. employees (very large), a single house, a group of things, or even a single thing.

> With a single object, it's hard to do statistics — there's no uncertainty. With two objects, you start to have uncertainty.

### Sample
- We often **don't have access** to the entire population (e.g., we can't access the salary of every U.S. employee), or there isn't enough data available.
- So we collect a smaller, manageable part of the population — called a **sample** — and study that instead.
- The sample **should represent** the population.
- **Goal of statistics:** use the sample to make an **inference** about the population.

**Example:** Out of millions of U.S. employees, we might collect data on just 50 of them and study that sample.

> ❓ **Open question raised in class:** *In a population of millions, how do we know if a sample of just 50 is "enough"?* (To be addressed later in the course — concept of sample size / sampling adequacy.)

---

## 3. Key Definitions

### Variable
A **variable** is a characteristic that changes or varies over time and/or across different individuals or objects under consideration. The word "variable" literally means *change*.

- **Examples:** hair color, white blood cell count, time to failure of a computer component.
- Height is a variable because it changes from one student to another (compare: eye color also changes from person to person).

### Experimental Unit
The **experimental unit** is the individual or object on which a variable is measured.

- **Example:** If studying cat eye color at UC Davis, the experimental unit is **one cat** — specifically, a cat *at UC Davis* (because that's the population we care about).

### Measurement
A **measurement** results when a variable is actually measured on an experimental unit — it is the actual value you collected.

- **Example:** "What is your height?" → "2.5 [units]" → 2.5 is the *measurement*.

### Data
A **set of measurements** is called **data**.

- Data can be of **two types**: a sample **or** a population.
- **No population = no sample.** A sample is always a subset *of* a population.

---

## 4. Multiple Variables per Experimental Unit

How many variables can be measured on a single experimental unit? More than one.

**Example:** Measuring height and weight for students in a class:
- Experimental unit: **one student** in the class.
- Variables measured: **Height (H)** and **Weight (W)** → recorded as the pair (H, W).
- This means we are collecting **2 variables** per unit.

### Terminology by Number of Variables
| Term | Meaning |
|---|---|
| **Univariate data** | **1** variable measured on a single experimental unit |
| **Bivariate data** | **2** variables measured on a single experimental unit |
| **Multivariate data** | **More than 2** variables measured on a single experimental unit |

---

## 5. Types of Variables

### A. Qualitative Variables
Refers to a *quality* — given as a **label**, **not a number**.

- **Examples:** gender (male, female), eye color (brown, black, blue, hazel).

### B. Quantitative Variables
Has a **number**. Splits into two subtypes:

> ❓ **Exam Alert:** Discrete vs. Continuous will appear on the **next midterm**.

#### Discrete
- Used for **counting**; has a **natural gap** between possible values.
- **Examples:**
  - Number of pens in a backpack → 0, 1, 2, 3, 4, 5 (natural gap of 1)
  - Shoe size → 5, 5.5, 6, 6.5 (natural gap of 0.5)

#### Continuous
- The measurement falls **anywhere on a number line** — no natural gap; can be subdivided infinitely.
- **Example:** Weight — the difference between 2.1 and 2.11 is still meaningful, and you could keep adding decimal precision.

> 🤔 **Class discussion point:** School fees — is there a "natural gap"? There's a gap of cents, which raises the question of whether something is discrete or continuous depending on how finely it *could* be measured.

### Quick Classification Examples from Class

| Item | Classification |
|---|---|
| Amount of time to assemble a simple puzzle | Continuous |
| Number of students in a first-grade classroom | Discrete |
| Rating of a newly elected politician | **Tricky** → Qualitative (not quantitative!) |
| State in which a person lives | Qualitative |
| Number of accidents along a 50-mile stretch of the Colorado River | Discrete |
| Time to complete an exam | Continuous |
| Cost of a head of lettuce | Discrete (gap of cents) |
| Number of brothers and sisters | Discrete |
| Yield (in kg) of wheat from a 1-hectare plot | Continuous |

---

## 6. Worked Example: Presidents' Age at Death

**Scenario:** A data set consists of the ages at death for each of the 38 *past* (now deceased) presidents of the United States.

> ❓ **Question (a):** Is this set of measurements a population or a sample?
> ❓ **Question (b):** What is the variable being measured?
> ❓ **Question (c):** Is the variable in part (b) quantitative or qualitative?

**Answers & Discussion:**
- **(b)** Variable: *age at death*, for the 38 past presidents.
- **(c)** Quantitative (it's a number).
- **(a)** This is the tricky one. The wording is deliberately ambiguous — are we talking about *all* presidents who have ever died, or specifically *the most recent* 38 to pass away?
  - If it refers to **all** deceased presidents in history → this would be the **population**.
  - The class concluded: because the data set is restricted to *only the last 38* presidents who passed, and there are more than 38 deceased presidents in total, this is technically a **population** of "the last 38 deceased presidents" — but if treated as a sample of "all deceased presidents ever," it would be a **poor/non-representative sample**, since it deliberately excludes earlier presidents.

> 💡 **Takeaway:** Always clarify exactly what the *population of interest* is before deciding whether your data set is a population or a sample.

---

## 7. Graphing Data

### Data Distribution
A **data distribution** describes:
1. **What values** of the variable have been measured.
2. **How often** each value has occurred.

**Mini-example:**
Data: 1→Black, 2→Black, 3→Red, 4→Yellow, 5→Black

- Distinct values (categories): Black, Red, Yellow
- **Relative frequencies:**
  - Black = 3/5
  - Red = 1/5
  - Yellow = 1/5

> 📌 **Rule:** The sum of all relative frequencies must always equal **1**.

### Worked Example: M&M Bag (25 candies)

A bag of M&Ms contains 25 candies. Raw data was tallied by color into a statistical table:

| Color | Tally (Frequency) | Relative Frequency | Percent |
|---|---|---|---|
| Red | 3 | 3/25 = 0.12 | 12% |
| Blue | 6 | 6/25 = 0.24 | 24% |
| Green | 4 | 4/25 = 0.16 | 16% |
| Orange | 5 | 5/25 = 0.20 | 20% |
| Brown | 3 | 3/25 = 0.12 | 12% |
| Yellow | 4 | 4/25 = 0.16 | 16% |

*(Check: relative frequencies sum to 1.00 ✓ — 0.12+0.24+0.16+0.20+0.12+0.16 = 1.00)*

### Graphing Qualitative Data
- Typically displayed using a **bar graph**.
  - X-axis: the categories (e.g., color)
  - Y-axis: the frequency
  - Bars must have **gaps** between them — they cannot overlap/touch (this distinguishes a bar graph from a **histogram**, which will be covered next class).
- Can also use a **pie chart**:
  - The full perimeter represents 100%, divided into slices per category.
- To convert a bar graph to relative frequency: take each bar's frequency value and divide it by **n** (total sample size).

### Graphing Quantitative Data
A single quantitative variable measured across **different population segments/categories** can also be graphed using a **bar** or **pie chart**.

**Example:** A Big Mac hamburger costs:
- $4.90 in Switzerland
- $2.90 in the U.S.
- $1.86 in South Africa

Here, **price** is the quantitative variable, but it's being measured across different **categories** (countries). This can still be represented with a bar or pie chart, because the x-axis consists of categories (countries) — the same structural setup as qualitative bar charts, just with quantitative values as the bar heights instead of frequency counts.

> 🤔 **Clarifying question raised in class:** *"Why are bar and pie charts being used for a quantitative variable if they're supposed to be for qualitative data?"*
> **Resolution:** The chart type depends on what's on the x-axis (categories), not strictly on whether the underlying variable is qualitative or quantitative. Grouping a quantitative variable by category (country, department, etc.) still produces a categorical x-axis — hence bar/pie still applies.

### Time Series
A single **quantitative variable measured over time** is called a **time series**, and is graphed using a **line chart** or **bar chart**.

*(Example to be added later in the course.)*

---

## Summary of Key Takeaways
- Statistics is fundamentally about managing **uncertainty** using data drawn from a **sample** to infer something about a **population**.
- Always define your **experimental unit** and **variable(s)** clearly before collecting data.
- Know your variable type: **Qualitative** vs. **Quantitative (Discrete/Continuous)** — this directly determines what graph/chart is appropriate.
- **Bar/pie charts** → categorical x-axis (qualitative data, or quantitative data grouped into categories).
- **Line/time series charts** → quantitative data tracked over time.
- Relative frequencies must always **sum to 1**.
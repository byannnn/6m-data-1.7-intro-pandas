# 📚 Lesson 1.7: Introduction to Pandas

## Session Overview

| | |
|---|---|
| **Duration** | 3 hours |
| **Format** | Flipped Classroom + Guided Coding in Jupyter |
| **Tools** | Google Colab (recommended) or VS Code + `pds` conda environment |
| **Notebook** | `notebooks/pandas_lesson.ipynb` |

## Agenda

| Time | Part | Topic |
|------|------|-------|
| 0:00 – 1:00 | Part 1 | Structures & Modification — DataFrames, Series, attributes |
| 1:00 – 2:00 | Part 2 | The Art of Selection — loc, iloc, Boolean filtering |
| 2:00 – 3:00 | Part 3 | Analysis & Operations — apply, sort, rank |

## 🎯 Learning Objectives

By the end of this session, you will be able to:

1. Create and modify Pandas data structures (Series and DataFrames).
2. Apply Pandas indexing and selection using `.loc`, `.iloc`, and Boolean filters.
3. Apply functions and mapping in Pandas using `.apply()` and `.map()`.
4. Sort and rank data in Pandas.

---

## 🗣️ Plain-English Jargon Buster

Keep this table handy — every technical term in this lesson, translated.

| Term | Plain English |
|------|---------------|
| **DataFrame** | A spreadsheet in Python — rows and columns |
| **Series** | A single column with labels |
| **index** | The row labels — like row numbers in Excel, but you can rename them |
| **`.loc`** | Look up by street address / label (e.g. `data.loc['Ohio']`) |
| **`.iloc`** | Look up by GPS coordinates / position (e.g. `data.iloc[0]`) |
| **vectorization** | Do it to the whole column at once instead of row by row |

---

## 🏃 Part 1: Structures & Modification (60 min)

**Why this Part exists:** Before you can analyse any data, you need to get it into a table Python understands — the DataFrame. Everything else in the course builds on this.

### 🎯 Focus
LO1 — Create and modify Pandas data structures.

### Concept Overview

Open the notebook `notebooks/pandas_lesson.ipynb` and follow along.

**Key topics in this section:**
- Creating DataFrames from dictionaries vs. lists
- DataFrame attributes: `.shape`, `.dtypes`, `.columns`
- Accessing columns
- Adding a new column (scalar vs. array assignment)

### 🛠️ Activity: "The Inventory System"

**Scenario:** You manage a small grocery store and need to track your fruit inventory. This is the starter data (it's in the notebook as `fruit_data`):

| fruit  | quantity |
|--------|----------|
| Apple  | 100      |
| Banana | 40       |
| Cherry | 200      |
| Date   | 20       |

**Tasks:**
1. Create a DataFrame named `inventory` from the dictionary `fruit_data`.
2. Add a new column `price` with values `[3.0, 4.0, 2.0, 5.0]`.
3. Add a column `total_value` which is `quantity * price` — no loop needed, just multiply the columns.
4. Create a boolean column `low_stock` that is `True` if quantity is less than 50.

> **Discussion:** How does vectorization (operating on entire columns at once) replace the need for loops?

---

## 🏃 Part 2: The Art of Selection (60 min)

**Why this Part exists:** Real datasets have thousands of rows — you almost never want all of them. Selecting exactly the rows and columns you need is the single most-used skill in pandas.

### 🎯 Focus
LO2 — Indexing and Selection (`.loc`, `.iloc`, `[]`).

### Concept Overview

**Analogy:** Think of `.loc` as using a street address (label-based), and `.iloc` as using GPS coordinates (position-based).

**Key topics in this section:**
- Slicing rows with `.loc` and `.iloc`
- Selecting specific columns
- Boolean filtering: `df[df['Value'] > 100]`
- Common pitfall: `[]` slicing behavior

### 🛠️ Activity: "Data Detective"

You'll work with this small DataFrame (created in the notebook as `data` — four US states as row labels, columns `one` to `four` holding the numbers 0–15):

|          | one | two | three | four |
|----------|-----|-----|-------|------|
| Ohio     | 0   | 1   | 2     | 3    |
| Colorado | 4   | 5   | 6     | 7    |
| Utah     | 8   | 9   | 10    | 11   |
| New York | 12  | 13  | 14    | 15   |

**Tasks:**
1. Select the rows for `'Utah'` and `'New York'` only.
2. Select the value in the `'two'` column for `'Ohio'` (should be 1).
3. Select all rows where column `'three'` is greater than 5.
4. Update the value of `'four'` in the `'New York'` row to be 100 (use `.loc`).

> **Question:** "Which method would you use to select the last row of a DataFrame — `.loc` or `.iloc`? Why?"

---

## 🏃 Part 3: Analysis & Operations (60 min)

**Why this Part exists:** Once you can select data, the next step is to transform and order it — apply custom logic to a column, sort to find winners, rank to compare. This is where raw tables start becoming answers.

### 🎯 Focus
LO3 (Functions) & LO4 (Sort/Rank).

### Concept Overview

**Key topics in this section:**
- Introduction to `.apply()` vs. loops
- Sorting by index vs. values
- Ranking data (handling ties)
- Using `.apply()` for custom text formatting

### 🛠️ Activity: "Leaderboard Logic"

**Scenario:** You have exam scores and need to rank students and assign a Pass/Fail status. Starter data (in the notebook as `scores`):

| Student | Math | Science |
|---------|------|---------|
| Alice   | 85   | 70      |
| Bob     | 45   | 55      |
| Charlie | 92   | 88      |
| David   | 60   | 72      |

**Tasks:**
1. Run the starter code in the notebook to create the `scores` DataFrame.
2. Sort the DataFrame by `'Math'` score in descending order (highest first).
3. Create a new column `'Math_Rank'` using the `.rank()` method.
4. Define a function that returns `"Pass"` if score >= 60 and `"Fail"` otherwise.
5. Apply this function to the `'Math'` column to create a new `'Status'` column.

### 💬 Reflection

- What are the optional topics for further self-study? (Reindexing, Dropping Entries, Multi-indexing)
- What is the difference between sorting by index and sorting by values?

---

## 🎯 Wrap-Up

**Key Takeaways:**
1. DataFrames are the central data structure in Pandas — understanding how to create and modify them is foundational.
2. `.loc` (label-based) and `.iloc` (position-based) are the primary tools for row and column selection.
3. `.apply()` lets you transform DataFrame values with custom logic — cleaner and faster than writing loops.

**Next Steps:**
- Complete the [Assignment](./assignment.md) — Pandas practice covering selection, aggregation, and manipulation.
- Next lesson: Lesson 1.8 introduces EDA Basic — inspecting, cleaning, and understanding your data.

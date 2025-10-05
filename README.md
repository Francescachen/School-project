# School-project
I was responsible for the data analysis and visualization for both term projects using R.  

### PROJECT 1: Determine which model best predicts trading performance.  

### PROJECT 2: Does Exercise Improve a Person’s Activeness?

Relationship Between Exercise Level and Feelings of Activeness

---

### 📝 Project Overview

This project is a **final course assignment (CP122 Final Project)** that investigates the relationship between an individual's **exercise level** (measured by daily step count) and their **self-reported feeling of activeness**.

The motivation stems from common issues faced during the pandemic, such as **weight gain, laziness, insomnia, and anxiety attacks**.  
The core hypothesis tested is:

> 💭 Does step count significantly improve feelings of activeness?

---

### 📊 Dataset and Variables

The analysis uses the **Fitness Trends Dataset** sourced from **Kaggle**.  
The data covers the period from **2017/10/6 to 2018/1/9**.

| Variable | Type | Definition |
|-----------|------|------------|
| `date` | Date | Record date |
| `step_count` | Numeric | Step Count |
| `calories_burned` | Numeric | Calories burned |
| `mood` | Factor (3 levels) | 100 (sad), 200 (neutral), 300 (happy) |
| `hours_of_sleep` | Numeric | Hours of sleep |
| `bool_of_active` | Factor (2 levels) | Activeness: 500 (active) or 0 (inactive) |
| `weight_kg` | Numeric | Weight (kg) |

---

### 🛠️ Methodology: Hypothesis Testing

We conducted a **Wilcoxon–Mann–Whitney Rank Sum Test** to compare the  
`step_count` (numeric, Y) between the two categories of `bool_of_active` (categorical, X).

The Wilcoxon test was chosen because it is a **non-parametric test** and does not depend on the specific form of the population distribution.

> **Hypothesis:**  
> Does step count improve feelings of activeness?

---

### 🔑 Key Findings

### 1️⃣ Step Count vs. Feelings of Activeness

The Wilcoxon rank sum test was performed:

```R
wilcox.test(ft$step_count ~ ft$bool_of_active)
# Output: W = 976, p-value = 0.2447
```

---

### Test Result: The p-value obtained is 0.2447.
Conclusion: Since the p-value (0.2447) > 0.05, there is no significant difference in step counts between the “active” and “inactive” groups.
We conclude that the step count does not significantly improve the feelings of activeness.

---

### 2️⃣ Relationships Between Other Factors
Step Count vs. Calories Burned:
The analysis showed a strong and positive correlation between step_count and calories_burned.
📈 (Visualization: Scatter plot showing linear relationship)
(TODO: Replace with your actual image URL)

---

### Step Count vs. Mood:
The distribution of step_count appears to be slightly higher for individuals reporting a Neutral (200) or Happy (300) mood compared to those reporting a Sad (100) mood.
🎻 (Visualization: Violin plot comparing step_count across mood categories)
(TODO: Replace with your actual image URL)

---

### ⚠️ Limitations and Discussion
The main finding that step count does not improve activeness must be interpreted within the context of the data’s limitations:
Single Subject Data – The data was recorded from only one person instead of a large population, limiting the generalizability of the findings.
Confounding Factors – Activeness is likely influenced by numerous factors beyond physical movement, such as environment, learning barriers, and exam performance.

---

### 🧩 Conclusion
The hypothesis that step count improves activeness was not supported by the data.
However, step count and calories burned showed a strong correlation, indicating that while physical activity increases energy expenditure, it may not directly enhance perceived activeness.

## ⚙️ Tools Used
R (tidyverse, ggplot2)
R Markdown for reporting and visualization
Kaggle dataset for source data

# School-project
I was responsible for the data analysis and visualization for both term projects using R.  

### PROJECT 1: Determine which model best predicts trading performance.  

### PROJECT 2: Does Exercise Improve a Person’s Activeness?

Relationship Between Exercise Level and Feelings of Activeness

---

### 📝 Project Overview

This project is a inal course assignment that investigates the relationship between an individual's **exercise level** (measured by daily step count) and their **self-reported feeling of activeness**.

The motivation stems from common issues faced during the pandemic, such as weight gain, laziness, insomnia, and anxiety attacks.  
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

### 🔑 Key Findings

### 1️⃣ Step Count vs. Feelings of Activeness

The Wilcoxon rank sum test was performed:

```R
wilcox.test(ft$step_count ~ ft$bool_of_active)
# Output: W = 976, p-value = 0.2447
```


#### Test Result: The p-value obtained is 0.2447.
Conclusion: Since the p-value (0.2447) > 0.05, there is no significant difference in step counts between the “active” and “inactive” groups.
Therefore, based on this data, we do not find sufficient evidence that step count improves the feeling of activeness.


### 2️⃣ Relationships Between Other Factors
#### Step Count vs. Calories Burned:
The analysis showed a strong and positive correlation between step_count and calories_burned.  

<img width="548" height="350" alt="Screenshot 2025-10-07 at 11 03 09 PM" src="https://github.com/user-attachments/assets/bcc2debf-81c2-46fe-884e-cc368bde0cdf" />

The analysis reveals a strong and positive correlation between step count and calories burned.
This indicates that individuals who walk more steps generally expend more energy, confirming that step count is a reliable indicator of overall physical activity.

#### Step Count vs. Mood:
The distribution of step_count appears to be slightly higher for individuals reporting a Neutral (200) or Happy (300) mood compared to those reporting a Sad (100) mood.  

<img width="455" height="436" alt="Screenshot 2025-10-07 at 11 00 56 PM" src="https://github.com/user-attachments/assets/da33e5f0-214e-4be3-87c1-32c1780ce57f" />

The data shows that individuals reporting Neutral or Happy moods tend to have slightly higher step counts compared to those feeling Sad.
This suggests that greater physical activity may be associated with more positive emotional states, though further research is needed to confirm causality.

### ⚠️ Limitations and Discussion
The main finding that step count does not improve activeness must be interpreted within the context of the data’s limitations:
Single Subject Data – The data was recorded from only one person instead of a large population, limiting the generalizability of the findings.
Confounding Factors – Activeness is likely influenced by numerous factors beyond physical movement, such as environment, learning barriers, and exam performance.


### 🧩 Conclusion
This project explored whether exercise, measured by step count, improves a person’s feeling of activeness.
The Wilcoxon–Mann–Whitney test (p = 0.2447 > 0.05) showed no significant difference between the “active” and “inactive” groups, suggesting that step count alone may not directly enhance perceived activeness.
However, step count was strongly correlated with calories burned and slightly higher among those with neutral or happy moods.  
These findings suggest that while step count may not directly improve activeness, consistent movement supports both physical health and positive mood.

## ⚙️ Tools Used
R (tidyverse, ggplot2)
R Markdown for reporting and visualization
Kaggle dataset for source data

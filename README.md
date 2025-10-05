# School-project
I was responsible for the data analysis and visualization for both term projects using R.  

**PROJECT 1:** Determine which model best predicts trading performance.  

**PROJECT 2:** 
# 🏃‍♀️ Does Exercise Improve a Person’s Activeness?

## 🧭 Introduction
During the COVID-19 pandemic, many people experienced **weight gain, laziness, depression, and anxiety** as a result of staying home for extended periods.  
This project explores whether **exercise or working out can help improve a person’s activeness** — defined by daily step count and self-reported feelings of energy.

The analysis was conducted as part of **CP122 Final Project**, using R programming to explore the relationship between **step count** and **activeness**.

---

## 📊 Dataset
**Source:** [Fitness Data Trends – Kaggle](https://www.kaggle.com/datasets/aroojanwarkhan/fitness-data-trends)

**Description:**  
The dataset was collected using Samsung Health from *2017/10/6 to 2018/1/9*.  
It contains daily information about one individual’s activity, mood, and health habits.

| Variable | Type | Description |
|-----------|------|-------------|
| `date` | Date | Record date |
| `step_count` | Numeric | Number of steps per day |
| `calories_burned` | Numeric | Calories burned per day |
| `mood` | Factor (3 levels) | 100 = Sad, 200 = Neutral, 300 = Happy |
| `hours_of_sleep` | Numeric | Hours of sleep |
| `bool_of_active` | Factor (2 levels) | 0 = Inactive, 500 = Active |
| `weight_kg` | Numeric | Weight (kg) |

> **Note:** Mood and activeness were self-reported, while step count and calories were automatically recorded.

---

## 🧪 Methodology
We used **R** to perform statistical analysis and visualization.

**Test Used:** Wilcoxon–Mann–Whitney Rank Sum Test  
- **Reason:** It’s a non-parametric test that does not assume normality.  
- **Objective:** Compare `step_count` between the two groups of `bool_of_active`.

```R
wilcox.test(ft$step_count ~ ft$bool_of_active)
# Output: W = 976, p-value = 0.2447
```

Result:
Since the p-value (0.2447) > 0.05, we fail to reject the null hypothesis.
👉 There is no significant difference in step counts between “active” and “inactive” groups.
🔍 Additional Analysis
1. Step Count vs. Calories Burned
A strong positive correlation was found between step_count and calories_burned.
(Visualization: scatter plot – to be added)
TODO: Add scatter plot image here
2. Step Count vs. Mood
People with neutral (200) or happy (300) moods tended to have slightly higher step counts than those with sad (100) moods.
(Visualization: violin plot – to be added)
TODO: Add violin plot image here
💡 Key Findings
Step count did not significantly improve feelings of activeness (p > 0.05).
However, physical movement still correlated positively with calorie burn and mood elevation.
⚠️ Limitations
Single-Subject Data:
Data was collected from one individual, limiting generalization.
Uncontrolled Factors:
Activeness can be influenced by external variables such as environment, learning barriers, or personal motivation.
Short Time Frame:
Only covers about three months of activity data.
🧘‍♀️ Conclusion
Although no statistically significant link was found between step count and activeness,
the data still suggests that regular movement and exercise support better mood and health awareness.
Future studies could use larger, more diverse samples to better understand the link between physical activity and perceived activeness.
⚙️ How to Reproduce
Requirements
R version ≥ 4.0
Libraries: tidyverse, ggplot2, dplyr, readr, stats
Run the Analysis
# Load dataset
ft <- read.csv("fitness_data.csv")

# Run Wilcoxon test
wilcox.test(ft$step_count ~ ft$bool_of_active)

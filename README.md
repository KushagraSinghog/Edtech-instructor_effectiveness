# Instructor Effectiveness Modeling (EdTech Context)

## Overview

This project focuses on analyzing and predicting **instructor effectiveness** on an EdTech platform using data-driven methods. The dataset contains batch-level information across multiple instructors, including learner outcomes, engagement metrics, and feedback scores.

The objective is to design a structured approach to:

* Define instructor effectiveness
* Aggregate batch-level data to instructor-level insights
* Build a machine learning model to predict effectiveness tiers
* Interpret results in a business and real-world context

---

## Problem Statement

Instructors on the platform teach multiple batches across different courses. The challenge is to:

* Quantify **instructor effectiveness** using available metrics
* Identify key factors influencing teaching performance
* Predict effectiveness tiers (**Low, Medium, High**) using machine learning

There is no predefined ground truth, making this a **feature engineering and reasoning-driven problem**.

---

## Dataset Description

Each row in the dataset represents a **course batch** with the following categories:

### 1. Learner Outcome Metrics

* `completion_rate`
* `dropout_rate`
* `avg_score_improvement`
* `avg_quiz_score`

### 2. Engagement Metrics

* `avg_watch_time`
* `assignment_submission_rate`
* `forum_activity_rate`

### 3. Feedback Metrics

* `avg_feedback_score`
* `feedback_response_rate`

---

## Approach

### 1. Exploratory Data Analysis (EDA)

* Analyzed feature distributions
* Studied relationships between engagement, outcomes, and feedback
* Identified correlations and potential patterns

### 2. Defining Instructor Effectiveness

A custom **effectiveness score** was designed using three components:

* **Learning Outcomes**
* **Student Engagement**
* **Learner Feedback**

The score was then converted into **three tiers**:

* Low
* Medium
* High

---

### 3. Data Aggregation

Since instructors teach multiple batches:

* Batch-level data was aggregated to **instructor-level**
* Mean values were used for performance metrics
* Added `num_batches` to capture instructor experience

---

### 4. Machine Learning Model

* Model used: **Random Forest Classifier**
* Hyperparameter tuning performed using **GridSearchCV**
* Cross-validation applied to ensure generalization
* Target leakage was identified and resolved

---

### 5. Evaluation

* Accuracy: **~88%**
* Metrics used:

  * Precision
  * Recall
  * F1-score
  * Confusion Matrix

The model performs well overall, with minor confusion between **Low and Medium** effectiveness tiers.

---

## Key Insights

* **Learning outcomes (quiz score, score improvement)** are the strongest predictors of instructor effectiveness
* **Dropout rate** is a critical negative indicator
* Engagement metrics contribute but are less predictive than outcome-based metrics
* Instructor experience (`num_batches`) has relatively low impact

---

## Limitations

* No adjustment for **course difficulty**
* No information on **student background or prior knowledge**
* Feedback scores may contain **bias**
* Dataset size is relatively small (120 instructors)

---

## Ethical Considerations

This model should **not be used as the sole basis for evaluating instructors**.

Instead, it should serve as a **decision-support tool** to:

* Identify trends
* Highlight improvement areas
* Support instructor development

---

## Potential Applications

* Identifying high-performing instructors
* Improving course quality through targeted interventions
* Supporting instructor training programs
* Enhancing learner experience through better course delivery

---

## Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn

---

## How to Run

1. Open the Jupyter Notebook (`main.ipynb`)
2. Ensure required libraries are installed
3. Run all cells sequentially
4. Review outputs and visualizations

---

## Conclusion

This project demonstrates how instructor effectiveness can be modeled using data-driven techniques. By combining learning outcomes, engagement, and feedback metrics, we can derive meaningful insights into teaching performance and support better decision-making in EdTech platforms.

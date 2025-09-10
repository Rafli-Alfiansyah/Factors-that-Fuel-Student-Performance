# Analysis of Student Exam Performance

![Exam_sheet](https://github.com/user-attachments/assets/0f04f3a9-6267-48a1-b54c-dbdcaeb56a71)

## An Investigation into Factors Influencing Student Success

In today's competitive educational environment, understanding the factors that influence student success is crucial. This project analyzes a dataset containing details about various aspects of student life, such as hours studied, sleep patterns, and attendance, to uncover what truly impacts exam performance.

### Data and Key Questions

The analysis uses a table named `student_performance` containing student data across six key columns: `attendance`, `extracurricular_activities`, `sleep_hours`, `tutoring_sessions`, `teacher_quality`, and `exam_score`.

Using SQL queries, this investigation aims to answer the following questions:

1.  How do study hours affect the average exam scores for students involved in extracurricular activities?
2.  What is the relationship between different ranges of study hours and the average exam scores?
3.  What are the characteristics of the top-performing students?

### Analysis and Results

#### 1\. Exam Scores for Active Students Studying Over 10 Hours

The first analysis focuses on students who participate in extracurricular activities and study for more than 10 hours. The query calculates the average exam score for each level of `hours_studied` and sorts the results in descending order.

The results show a clear positive correlation, among students engaged in extracurriculars, those who studied for 43 hours achieved the highest average score of 78. As the number of study hours decreases, the average exam score also tends to decline, down to an average of 65.15 for those studying 11 hours.

| hours\_studied | avg\_exam\_score |
| :--- | :--- |
| 43 | 78.00 |
| 39 | 75.00 |
| 38 | 73.50 |
| ... | ... |
| 12 | 64.97 |
| 11 | 65.15 |

#### 2\. Average Exam Scores by Study Hour Ranges

To simplify the relationship between study time and performance, students were grouped into four distinct ranges based on their `hours_studied`. The average `exam_score` was then calculated for each group.

The data confirms that increased study time is associated with higher average exam scores. Students studying **16+ hours** have the highest average score, while those studying **1-5 hours** have the lowest.

| hours\_studied\_range | avg\_exam\_score |
| :--- | :--- |
| 16+ hours | 67.92 |
| 11-15 hours | 65.20 |
| 6-10 hours | 64.23 |
| 1-5 hours | 62.63 |

#### 3\. Profile of Top-Performing Students

Finally, an analysis was performed to rank students by their exam scores and identify the characteristics of the top 30 performers. The `DENSE_RANK()` function was used to assign a rank based on `exam_score`.

The results for the top-ranked students show a wide variation in study habits and other factors. For instance, the top-ranked student achieved their score with 98% attendance, 27 hours of study, 6 hours of sleep, and 5 tutoring sessions. However, another student with the 4th rank studied 28 hours but had no tutoring sessions. This suggests that while there are general trends, individual success is influenced by a diverse combination of factors.

### Conclusion

This analysis reveals clear patterns between student habits and academic outcomes. The most straightforward conclusion is that **more hours spent studying generally leads to higher exam scores**. Furthermore, even students who participate in extracurricular activities benefit from dedicating more time to their studies. While factors like attendance, sleep, and tutoring also play a role, the amount of time invested in studying appears to be a primary driver of success in this dataset.

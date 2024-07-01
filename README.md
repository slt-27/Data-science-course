# Data-science-course
Python Projects 
import pandas as pd
from scipy.stats import f_oneway

# Load the data
file_path = '/mnt/data/students.csv'
data = pd.read_csv(file_path)

# Extract the scores into separate variables
reading_scores = data['reading_score']
writing_scores = data['writing_score']
maths_scores = data['maths_score']

# Perform the ANOVA test
f_statistic, p_value = f_oneway(reading_scores, writing_scores, maths_scores)

# Print the F-statistic and p-value
print("F-statistic:", f_statistic)
print("P-value:", p_value)

# Conclusion based on p-value
if p_value < 0.05:
    conclusion = "As the p-value is less than 0.05, you do have enough evidence to say that there is a difference in means of student performance in reading, writing, and maths."
else:
    conclusion = "As the p-value is greater than 0.05, you do not have enough evidence to say that there is any difference in means of student performance in reading, writing, and maths."

print(conclusion)


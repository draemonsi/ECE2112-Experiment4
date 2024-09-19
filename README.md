# Experiment 4: Data Wrangling and Data Visualization

## Course: ECE 2112 - Advanced Computer Programming and Algorithms <br/>
**Institution**: University of Santo Tomas, Faculty of Engineering, Electronics Engineering Department

## Project Overview
- In this experiment, we use Python's Pandas library to perform data wrangling and create meaningful data visualizations from a given dataset. We analyze the dataset by applying various techniques such as filtering, conditional indexing, and visualization methods to extract insights about student performance in specific tracks. Finally, we use visualizations like box plots, bar graphs, pie charts, and scatter plots to present our findings.
---
## Table of Contents
1. [Intended Learning Outcomes](#intended-learning-outcomes)
2. [Problem Descriptions](#problem-descriptions)
3. [Installation Instructions](#installation-instructions)
4. [Usage](#usage)
5. [Files Included](#files-included)
6. [Technologies Used](#technologies-used)
7. [Data Interpretation](#data-interpretation)
8. [Conclusion](conclusion)
9. [License](#license)
10. [Author](#author)
---
## Intended Learning Outcomes
1. Identify the functions and methods required for cleaning and visualizing data in Python using Pandas. <br/>
2. Use conditional indexing to filter and subset DataFrames based on multiple conditions.<br/>
3. Generate meaningful visualizations using Matplotlib and Seaborn to analyze data patterns.
---
## Problem Descriptions
### Problem 1: Create a DataFrame using a subset of the columns and specific filtering conditions
- **Objective:**  Filter students from Visayas whose Math score is less than 70.<br/>
  - Code sample:
```
board_results[['Name', 'Gender', 'Track', 'Math']][(board_results['Hometown'] == 'Visayas') & (board_results['Math'] < 70)]
```
- **Objective:**  Create a DataFrame showing students from Luzon in the Instrumentation track who scored more than 70 in Electronics.<br/>
  - Code sample:
```
board_results[['Name', 'GEAS', 'Electronics']][(board_results['Electronics'] > 70) & (board_results['Track'] == 'Instrumentation') & (board_results['Hometown'] == 'Luzon')]
```
- **Objective:**  Create a DataFrame showing students from Mindanao, who are female and have an average score greater than or equal to 55.<br/>
  - Code sample:
```
board_results['Average'] = (board_results['Math'] + board_results['Electronics'] + board_results['GEAS'] + board_results['Communication']) / 4
board_results[['Name', 'Track', 'Electronics', 'Average']][(board_results['Average'] >= 55) & (board_results['Hometown'] == 'Mindanao') & (board_results['Gender'] == 'Female')]
```
### Problem 2: Visualizing Data
- **Objective:**  Create visualizations (boxplots, bar charts, pie charts, scatter plots) to analyze student performance across different tracks, subjects, and gender distributions.<br/>
  - Code sample (Boxplot):
```
board_results.boxplot(column=subject, by='Track', ax=axes[idx])

```

---
## Installation Instructions

To run the provided Python code, ensure you have the following installed:<br/>
1. Python (Version 3.6 or higher) <br/>
2. Jupyter Notebook or any Python IDE (VS Code, PyCharm) <br/>
3. Pandas, Matplotlib, Seaborn, and NumPy library <br/>

### Installation steps:<br/>
1. Clone the repository:<br/>
```git clone https://github.com/draemonsi/ECE2112-Experiment4.git``` <br/>
2. Install dependencies (if Pandas is not installed):<br/>
```pip install pandas matplotlib seaborn numpy```<br/>
---
## Usage
1. Open Jupyter Notebook or any Python environment. <br/>
2. Load the provided dataset (board2.csv) into a Pandas DataFrame.<br/>
3. Run the code snippets to solve each problem and create visualizations.<br/>
4. The results will be displayed directly in your environment.
---
## Files included
- PA4.ipynb: Python file containing the code to perform data wrangling and visualization. <br/>
- board2.csv: CSV file containing the dataset with students’ scores and other details.
---
## Technologies Used
- Python (version 3.x)
- Pandas (Python Data Analysis Library)
- Matplotlib and Seaborn (Data visualization)
- Jupyter Notebook for code execution and analysis
---
## Data Interpretation
The data from the ECE board exam reveals a multifaceted view of performance variations based on academic tracks, regional demographics, and gender distribution. In the Microelectronics track, which is predominantly female [Figure 1.0](#figure-1.0) (around 70% female students), the students demonstrate strong proficiency in Math, with many scoring above 87, and a tighter distribution of scores indicating consistent performance. However, this same group tends to underperform in the Electronics section, where their median score falls below 70, highlighting a disconnect between their theoretical math skills and practical application in electronics. In contrast, the Instrumentation track, mainly composed of male students (over 80% male), displays robust performance across exam sections, with no scores below 55 in the General Engineering and Applied Sciences (GEAS). However, this track struggles in Communication, where no students scored above 80.

The Communication track, with an equal gender distribution, shows a broader range of Math scores, with many students scoring below 70, and a slightly higher but still variable range of scores in Electronics, where the median hovers around 70. This indicates challenges in both technical and mathematical areas.

Regionally, students from the Visayas region (green points in the scatterplots) perform well in Math, often scoring above 80, but face significant struggles in the Electronics section, with most scoring below 60. This points to a regional disparity in performance, potentially driven by differences in educational resources or focus. Students from Mindanao and Luzon display a more balanced but variable performance across both Math and Electronics, with scores spanning a wide range in both subjects.

The scatterplots reveal that there is no strong correlation between high performance in one section and another, especially in Math and Electronics, underscoring the idea that students tend to specialize in specific areas rather than achieving uniform excellence across the board. For example, several students who scored above 80 in Math did not surpass 60 in Electronics, particularly in the Microelectronics track.

In summary, the data underscores significant performance trends and disparities across tracks, regions, and gender groups. The math-strong but electronics-weak Microelectronics students, and the consistent but communication-challenged Instrumentation students, suggest the need for more nuanced, possibly track-specific, educational strategies. The inclusion of gender demographics—such as the predominantly male Instrumentation track and the more balanced Communication track—adds another layer to these findings, offering a pathway for more tailored interventions to address specific weaknesses and improve overall performance in the ECE board exam.<br/>
 
## Figure 1.0 
<img width="1105" alt="image" src="https://github.com/user-attachments/assets/7e3fafcf-8e49-4dee-bbed-95f525c6e335">

## Figure 1.1 
<img width="996" alt="image" src="https://github.com/user-attachments/assets/b44c1c78-453c-498f-b400-eb2c6bb5af82">

## Figure 1.2 
<img width="852" alt="image" src="https://github.com/user-attachments/assets/288c4492-034f-4cf7-b9ad-808260d39752">

## Figure 1.3 
<img width="848" alt="image" src="https://github.com/user-attachments/assets/804d1100-8b54-42f6-bfe5-513415b92892">

## Figure 1.4 
<img width="841" alt="image" src="https://github.com/user-attachments/assets/faeb8c23-e4de-42a5-b95c-612addc5cbc6">

---
## Conclusion 
- This experiment demonstrates the power of data wrangling and visualization techniques in uncovering insights from a dataset. By using Pandas, we were able to filter data based on specific conditions and manipulate the DataFrame to focus on relevant information. Additionally, the visualizations helped identify patterns in student performance across tracks, subjects, and gender distributions. The ability to interpret these patterns is crucial in making data-driven decisions and conclusions.
---
## License<br/>
- This project is licensed under The Unlicense. Please see [LICENSE](https://github.com/draemonsi/ECE2112-Experiment4/blob/main/LICENSE.txt) file for more details.
---
## Author<br/>
- Andrei Jorelle C. Simon<br/>
  [GitHub Profile](https://github.com/draemonsi)



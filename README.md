# Experiment 4: Data Wrangling and Data Visualization

## Course: ECE 2112 - Advanced Computer Programming and Algorithms <br/>
**Institution**: University of Santo Tomas, Faculty of Engineering, Electronics Engineering Department

## Project Overview

In this experiment, we use Python's Pandas library to perform data wrangling and create meaningful data visualizations from a given dataset. We analyze the dataset by applying various techniques such as filtering, conditional indexing, and visualization methods to extract insights about student performance in specific tracks. Finally, we use visualizations like box plots, bar graphs, pie charts, and scatter plots to present our findings.
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
The data from the ECE board exam reveals distinct differences in student performance across various tracks and regions, shaped by both academic focus and demographics. In the Microelectronics track, predominantly composed of female students, there's a strong performance in Math, with a high percentage of scores above 87 and a tight score spread indicating consistency. However, these students often struggle in the Electronics section, suggesting a gap between their mathematical proficiency and their ability to apply these skills practically. Conversely, the Instrumentation track, which is predominantly male, shows consistent performances across all sections, with no scores below 55 in GEAS but notable struggles in Communication. The Communication track, which boasts an equal distribution of male and female students, shows a broader range of scores and lower overall performance in Math, but slightly higher mean scores in Electronics.

Regionally, Visayas students excel in Math but are significantly challenged in Electronics, while Mindanao and Luzon students display more balanced but still varied performance across these subjects. Scatter plots further highlight these trends, showing that excelling in Math does not guarantee similar success in Electronics or other sections, as evidenced by the performance disparities between tracks and regions. Additionally, there's no clear correlation between performance in GEAS and Communication, emphasizing variability and specialization in student skill sets.

In summary, the data underscores the need for targeted educational strategies that address the specific weaknesses and demographic compositions of each track to enhance overall performance in the ECE board exam. The distinct trends across tracks—like the math-strong but electronics-weak Microelectronics track, and the balanced but struggling Instrumentation and Communication tracks—suggest that more nuanced, possibly track-specific, educational interventions are necessary to bridge the gaps in knowledge and application skills, particularly in regions like Visayas where additional support in Electronics could prove beneficial.

The data from the ECE board exam reveals a multifaceted view of performance variations based on academic tracks, regional demographics, and gender distribution. In the Microelectronics track, which is predominantly female (around 70% female students), the students demonstrate strong proficiency in Math, with many scoring above 87, and a tighter distribution of scores indicating consistent performance. However, this same group tends to underperform in the Electronics section, where their median score falls below 70, highlighting a disconnect between their theoretical math skills and practical application in electronics. In contrast, the Instrumentation track, mainly composed of male students (over 80% male), displays robust performance across exam sections, with no scores below 55 in the General Engineering and Applied Sciences (GEAS). However, this track struggles in Communication, where no students scored above 80.

The Communication track, with an equal gender distribution, shows a broader range of Math scores, with many students scoring below 70, and a slightly higher but still variable range of scores in Electronics, where the median hovers around 70. This indicates challenges in both technical and mathematical areas.

Regionally, students from the Visayas region (green points in the scatterplots) perform well in Math, often scoring above 80, but face significant struggles in the Electronics section, with most scoring below 60. This points to a regional disparity in performance, potentially driven by differences in educational resources or focus. Students from Mindanao and Luzon display a more balanced but variable performance across both Math and Electronics, with scores spanning a wide range in both subjects.

The scatterplots reveal that there is no strong correlation between high performance in one section and another, especially in Math and Electronics, underscoring the idea that students tend to specialize in specific areas rather than achieving uniform excellence across the board. For example, several students who scored above 80 in Math did not surpass 60 in Electronics, particularly in the Microelectronics track.

In summary, the data underscores significant performance trends and disparities across tracks, regions, and gender groups. The math-strong but electronics-weak Microelectronics students, and the consistent but communication-challenged Instrumentation students, suggest the need for more nuanced, possibly track-specific, educational strategies. The inclusion of gender demographics—such as the predominantly male Instrumentation track and the more balanced Communication track—adds another layer to these findings, offering a pathway for more tailored interventions to address specific weaknesses and improve overall performance in the ECE board exam.
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



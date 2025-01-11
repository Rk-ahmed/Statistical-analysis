# Descriptive Statistics in Python
Documented by: Rakib Ahmed
This repository demonstrates how to perform descriptive statistical analysis using Python with a sample dataset. The project explores key statistical measures and visualizations using commonly used Python libraries.

# 📊 Overview
Statistics is a branch of mathematics focused on collecting, analyzing, interpreting, presenting, and organizing data. This project covers descriptive statistics, which summarize and describe features of a dataset.

We explore various statistical measures such as:

Mean, Median, Mode
Range, Variance, Standard Deviation
Trimmed Mean
Quantiles and Interquartile Range (IQR)
Skewness and Kurtosis
Correlation and Covariance
Additionally, we demonstrate data visualization techniques using boxplots, histograms, scatter plots, and pie charts to better understand the dataset.

🛠 Libraries Used
The following Python libraries are used in this project:

pandas – Data manipulation and analysis (loading datasets, transformations).
numpy – Numerical computing (arrays, mathematical operations).
scipy.stats – Used for statistical functions like trim_mean.
matplotlib.pyplot – Plotting graphs and charts.
seaborn – High-level statistical data visualization.
📁 Dataset
The dataset used in this analysis contains information on U.S. states, their populations, murder rates, and abbreviations. Here's a snapshot of the dataset:

State	Population	Murder Rate	Abbreviation
Alabama	4,779,736	5.7	AL
Alaska	710,231	5.6	AK
Arizona	6,392,017	4.7	AZ
Arkansas	2,915,918	5.6	AR
California	37,253,956	4.4	CA
Colorado	5,029,196	2.8	CO
Connecticut	3,574,097	2.4	CT
Delaware	897,934	5.8	DE

📈 Results and Insights
Mean and median of the population indicate that while the average population is around 7.7 million, half of the states have populations below 4.1 million.
The skewness of 2.68 suggests that the population distribution is positively skewed, with a long right tail indicating a few states with very high populations.
The kurtosis value of 7.37 indicates a leptokurtic distribution, meaning the dataset has more extreme values (outliers) than a normal distribution.
A weak correlation of -0.13 between population and murder rate suggests no strong linear relationship between the two variables.
Visualizations like boxplots and histograms reveal the spread and distribution of population data across states.

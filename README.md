# MALARIA INCIDENCE REDUCTION IN NIGERIA

The aim is to analayse global malaria case and death estimates with the goal of informimg strategies to reducing the impact of malaria in Nigeria.

The dataset, sourced from the World Health Organization (WHO),and retrieved from Kaggle provides insights into malaria incidence, mortality, and regional disparities. 

The analysis includes exploratory data analysis (EDA), data visualization, statistical analysis, and a simple ETL (Extract, Transform, Load) process.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## The Dataset
The dataset was sourced from Kaggle 
* The dataset comprises of 3 .csv files -

[Download Reported Numbers](./jupyter_notebooks/raw/reported_numbers.csv)

[Download incidence](./jupyter_notebooks/raw/incidence.csv)

[Download estimated_numbers](./jupyter_notebooks/raw/estimated_numbers.csv)

* Description:

•Dimensions;

estimated_numbers: 855 rows and 11 columns

incidence: 2033 rows and 4 columns

reported_numbers: 1944 rows and 5 columns

•Variables:

Country: Country name

Year: Year of the data (2016 or 2017)

No. of cases: Number of reported malaria cases

No. of deaths: Number of reported malaria deaths

No. of cases_median: Median estimate of malaria cases

No. of cases_min: Minimum estimate of malaria cases

No. of cases_max: Maximum estimate of malaria cases

No. of deaths_median: Median estimate of malaria deaths

No. of deaths_min: Minimum estimate of malaria deaths

No. of deaths_max: Maximum estimate of malaria deaths

WHO Region: WHO region to which the country belongs


## Business Requirements

* By focusing on effective resource allocation, targeted interventions, and improved monitoring and evaluation, it is hoped that data driven strategies will help to reduce malaria incidence and death rates overall. 
The main objective is to reduce incidence by 20% and to improve the reporting of cases by implementing real time malaria surveillance in healthcare systems. This will hav a significant impact on decreasing underreporting of cases.


## Hypothesis and validation

# **Hypothesis 1**:  Using Chi-Square Test

To test if underreporting has a significant effect on the mortality in Nigeria

• NULL HYPOTHESIS(H<sub>0</sub>): Underreporting does not have a significant impact on malaria deaths in Nigeria

•  ALTERNATIVE HYPOTHESIS|(H<sub>1</sub>): Malaria deaths are significantly higher in areas of high underreporting of malaria cases.

•  VALIDATION: The Chi_Test was computed using python code and corresponding value was output alongside the p-value. A heatmap was used to visually interprete the CHI-Square Test.
The Chi-Test compared the frequencies of observed estimated and reported cases.

•  OUTPUT: 

**Chi-Square Statistic**: 562.6588785046729  
**P-value**: 2.219350768431402e-124  
**Reject H₀**: Underreporting significantly affects malaria deaths in Nigeria.

•  CONCLUSION: The Null hypothesis is rejected showing underreporting impacts deaths ion Nigeria significantly.


# **Hypothesis 2**: Using Mann-Kendall Trend Test

To check the decrease of malaria incidence over time in Nigeria

• NULL HYPOTHESIS(H<sub>0</sub>): No significant trend in malaria incidence decrease

•  ALTERNATIVE HYPOTHESIS|(H<sub>1</sub>): malaria incidence has decreased due to interventions over time

•  VALIDATION: THe Mann-Kendall test is used to find out if there is a trend in the decrease of incidence over the years. This will help give better understanding into cause for decrease either climate,weather or better surveillance method.

•  OUTPUT: 
Trend: no trend

P-value: 0.15961031455633856

Fail to reject H₀: No significant decreasing trend in malaria incidence.

• CONCLUSION: 

The Null hypothesis is found true,there is no significant decreas in Malaria incidence. This means the incidence has been fluctuating over the years.


# **Hypothesis 3**:  Using ARIMA(AutoRegressive Integrated Moving Average)
Time series forecasting checks if future malaria incidence can be predicted in Nigeria

• NULL HYPOTHESIS(H<sub>0</sub>): The malaria incidence follows an unpredictable pattern

•  ALTERNATIVE HYPOTHESIS|(H<sub>1</sub>): The incidence pattern is predictable and able to forecast

•  OUTPUT:

Forecasted Malaria Incidence for the next 5 years: 856    95.426729
857    91.061710
858    91.364738
859    91.343701
860    91.345162
Name: predicted_mean, dtype: float64

• CONCLUSION:
From the plot we can see the forecast as red dotted lines which is flat and hints that the model isn't capturing the trend.


## Project outline
The project was based on:
* Setting up a work tracker: Use of the Kanban board
* Objectives: this was set after researching dataset
* Data sourcing: from Kaggle dataset
* Data Preparation: ETL 
* EDA
* Visualisations
* Statistical Analysis
* Dashboard and Visualisation:Tableau for story telling of the data
* Documentation: documenting project processes
* Conclusion: form the analysis
* Evaluation: Lessons learnt from the project and implications

* The methodology used suited the purpose of finding the necessarty trends and was carried in the order stated above to fit in with results needed. The data was maintained by uploading and viewing each time required for use on a new notebook.

## The rationale to map the business requirements to the Data Visualisations
* The tarrget was tomcreate visuals to show the relation between different variables that have effect on the malaria incidence in Nigeria.
The trend lines and Regression plots helped to convey this. 
 •The trend line conveyed a fluctuation in the decrease of incidence.
 •While the regression line was inaccurate giving a forecast due to probably the model unable to capture the dat properly or migh be some underreporting of the cases.

## Analysis techniques used

 The following analyis were carried in order they are listed here. 

## ETL: Extract,Transform and Load

* Extract:

Extraction of needed data from the 3 datasets uploaded unto Jupyter notebook.

* Transform: 

The csv files were loaded onto the Dataframe

Converted columns to appropriate data types (numeric, string).

Checked and handled missing values (if any) using appropriate methods.

Filtering data needed to carry out basic data insights

Merged datasets to carry out further analysis

* Load

The merged dataset(transformed) was used in the EDA, visualisations and statistical analysis.

## Exploratory Data Analysis (EDA)

To understand the data, the following exploratory analysis was done:

* DESCRIPTIVE ANALYSIS:

To check for the data structiure of the merged data, if there are any discrepancies needed to fix.

* HANDLING MISSING/NEGATIVE VALUES

Check for outliers,negative values and missing values.Box plots used to identify outliers

* DATA DISTRIBUTION:

* Histogram of yearly malaria cases. 

* Malaria trend by WHO REGION
Aggregated data by WHO region to understand the regional burden of malaria with the use of a bar chart to visualise

* Top countries with high malaria burden
Identified countries with the highest and lowest malaria cases

* Malaria trend in Nigeria

* Correlation analysis;to understand the relationships between variables

Correlation Between Reported Cases, Incidence, and Estimated Cases:

                   Reported Cases  Malaria Incidence  Estimated Cases
Reported Cases           1.000000           0.485402        -0.009833
Malaria Incidence        0.485402           1.000000         0.648249
Estimated Cases         -0.009833           0.648249         1.000000

## Visualisations

These visualisations were generated to provide insights into the data:

Pie Chart: to show the proportion of malaria burden by WHO region

Scatter Plot:to show if there is a visual relationship between the estimated cases and incidence

Correlation Heatmap: checks the relation between Reported,Incidence and No of cases_median

Box Plot:using the WHO Region to check for outliers(underreporting)

Regression Plot:to see if there is a linear relationship between the two variables Reported and Estimated.

## Statistical Analysis
Hypothesis Testing: the 3 hypothesis stated above was tested and visual output included.

* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
The dashboard was created on Tableau. Idea of the layout was from Balsamiq.
It is made up of 6 worksheets created from the merged dataset loaded onto Tableau
The visualisations are:
Bar Chart: showing the top most countries affected in the Africa Region
Pie Chart: showing the Region with the highest malara burden
Trend line: showing the effect of estimsted case vs estimated death over time
Trend line: for  malaria incidence in Nigeria.
Regression line: for forecasting

The dashboardvwas designed withnthe layman in mind so anyone coukld easily understyand the visuals especial;ly those who will aid decision making in government.

* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* Had initial hurdle of loading the merged datyaset onto the EDA notebook. I found out i was using the wrong path name, i assumed it was required but it wasn't because it had alraedy been saved in jupyter so coukld load directly.
* Had to change the data type for the Estimated death and Estmated Cases when initially loaded on Tableau to integer because it was still in object.




## Main Data Analysis Libraries
The project consists of the following Python scripts:

etl.ipynb: for extracting, transforming, and loading the data.

eda.ipynb: for performing exploratory data analysis and generating summary statistics.

visualizations.ipynb: Script for creating visualizations such as bar charts, time series plots, and heatmaps.

statistical_analysis.ipynb: for performing statistical tests and computing probabilities.

 Dependencies
The following tools were required to run this

Software requirements
Python 3.12

Python Libraries
For Data Handling & Manipulation
pandas – For data cleaning, manipulation, and merging datasets.
numpy – For numerical operations and handling large arrays.

For Data Visualisation
matplotlib – For basic plotting and data visualization.
seaborn – For creating more advanced and aesthetically appealing statistical plots.
plotly – For interactive visualizations (e.g., interactive maps, trend graphs).

Statistical Analysi
scipy – For statistical testing and probability distributions.
statsmodels – For regression analysis and time series forecasting.
scikit-learn – For predictive modeling (e.g., linear regression, clustering).

Time Series Analysis
statsmodels.tsa – For time series forecasting (e.g., ARIMA models).


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people who provided support through this project.


[def]: data/incidence.csv
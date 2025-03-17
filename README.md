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






## Project Plan
* Outline the high-level steps taken for the analysis.
* How was the data managed throughout the collection, processing, analysis and interpretation steps?
* Why did you choose the research methodologies you used?

## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

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

* Data Distribution:

Histogram of yearly malaria cases. 

* Malaria trend by WHO REGION
Aggregated data by WHO region to understand the regional burden of malaria with the use of a bar chart to visualise

* Top countries with high malaria burden
Identified countries with the highest and lowest malaria cases

* Malaria trend in Nigeria
Correlation Analysis:

* Correlation analysis 

To understand the relationships between variables 
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
Hypothesis Testing: the 3 hypothesis stated above was tested and visual output included


7. Key Findings
Regional Disparities: Africa bears the highest malaria burden globally, with countries like Nigeria, the Democratic Republic of Congo, and Uganda reporting the highest numbers of cases and deaths.

Zero-Case Countries: Several countries (e.g., China, Morocco) report zero cases, indicating potential elimination or very low transmission.

Variability in Estimates: Estimated cases show greater variability across regions compared to reported cases, highlighting potential uncertainties in modeling methods.

Underreporting: Differences between reported and estimated cases suggest underreporting in regions with limited surveillance infrastructure.

High Correlation: Strong positive correlation between reported cases and deaths, indicating a direct relationship between disease incidence and mortality.

8. Code Structure
The project consists of the following Python scripts:

etl.py: Script for extracting, transforming, and loading the data.

eda.py: Script for performing exploratory data analysis and generating summary statistics.

visualizations.py: Script for creating visualizations such as bar charts, time series plots, and heatmaps.

statistical_analysis.py: Script for performing statistical tests and computing probabilities.

9. Dependencies
The following tools are required to run this analysis

9.1 Software requirements
Python (>=3.6)

9.2 Python Libraries
pandas

matplotlib

seaborn

scipy

statsmodels

To install these dependencies, run:

bash
pip install pandas matplotlib seaborn scipy statsmodels
10. Usage
To reproduce the analysis, follow these steps:

bash
# Clone the repository
git clone [repository URL]

# Navigate to the project directory
cd [project directory]

# Run the ETL script
python etl.py

# Run the EDA script
python eda.py

# Run the visualizations script
python visualizations.py

# Run the statistical analysis script
python statistical_analysis.py
11. Potential Limitations
Data Quality: The accuracy of this project is based on the quality of the underlying data.

Causality: Correlation does not equal causation.

External Factors: The model may not account for policy changes or changes to the health landscape.

12. Future Work
Analyze Intervention Effectiveness: Evaluate the impact of malaria interventions (e.g., insecticide-treated bed nets, indoor residual spraying) on case and death rates.

Develop Predictive Models: Build time series models to forecast future malaria trends.

Geospatial Analysis: Incorporate spatial data to understand geographic patterns of malaria transmission and mortality.


* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 

## Deployment
### Heroku

* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. From the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.


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
# ANALYSIS OF INDIAN START-UP FUNDING ECOSYSTEM

My team is trying to venture into the Indian start-up ecosystem. This project aims to provide insights into the Indian startup ecosystem through data analysis. The analysis includes cleaning and processing raw data, exploring various aspects of the startup landscape, and deriving meaningful conclusions.

This project required that we look into the Indian start-up funding ecosystem from 2018 to 2021.
In order to conduct this analysis, data was sourced from DAP Database, OneDrive, and a github repo.
After collecting the dataset, we had to use the Cross-Industry Standard for Data Mining (CRISP-DM) framework approach to data analysis. It involved the five-fold stages of Business Understanding, Data Understanding, Data Preparation, Analysis, and Deployment. Let’s highlight each stage in the order listed.

### TEAM LEADER

Ntuk, Etebom

## COLLABORATORS

Mohammed Idris
Etebom Ntuk
Elvis Obeng Yeboah
Prince Acquah Rockson
Celestine Jerop Kaplelach
Andy Konney

## BUSINESS UNDERSTANDING

In the business understanding phase, we had to state out clearly what we intended to achieve.
Per the title of the project, we’re to investigate the Indian start-up funding ecosystem to uncover as much trends that the data reveals for the start-ups and the investors alike. This meant understanding the trends funding amounts, the sectors/industries that received a greater part of the funds, and to uncover the major investors that contributed the most to start-up funding.
Below are our business questions:
(1)How has the funding trend changed over the years?
(2)What is the distribution of funding received by industry?
(3)What cities have attracted the most funding for start-ups?
(4)Which cities have attracted the most start-ups?
(5)Who are the major investors in this ecosystem?
(6)Who are the top investors in the ecosystem, and which industries do they favor?
(7)Are there any emerging sectors gaining traction by investors?
(8)Which emerging main sector/industry is gaining traction by investors?
(9)What are the top three (3) industries to receive funding?
(10)What are the top three (3) main sectors within the top three (3) industries in terms of frequency?
(11)Can we identify any correlation between the amount of funding they received and the sector to which they belong?

## DATA UNDERSTANDING

The datasets collected held details of the start-up names, what they do, how much they received in funds, the year they received funding, the stage of their operations when they received funding, the year the start-up commenced business, the industry/sector in which they operate, their official business location, and the investors that granted these start-ups the much needed funds.
For the 2018 dataset, some requisite columns such as sector and headquarter were incorporated into industry and location columns respectively. We had to pick out the specific details needed and thus created the headquarter and sector columns in order for the dataset to be consistent with the datasets for 2019 - 2021. Some columns such as stage and amount had their values wrongly inputed. This was noted ahead of the data cleaning exercise. Also noticed was that the amount column held values of both numerical and categorical types. There were multiple currency symbols found in the amount column. The columns for the datasets covering 2019 to 2021 were in order and so we were ready for data cleaning.
(a)DATA CLEANING: While the 2019 dataset was downloaded from OneDrive, the 2018 dataset was soucred via a github url link in Pandas. The 2020 and 2021 datasets were first queried from the DAP database using our environment variables and then saved locally. For the data cleaning proper, we had to first take on each dataset one after the other because we realised that concatenating the datasets before cleaning a singular dataframe proved counter productive.
(i)2018 DATASET:
The bulk of work was on the Amount column. Amounts stated in rupees were converted to dollar values using a function, Currency symbols, white spaces, and commas were removed wherever found in the amount column.
(ii)2019 DATASET:
The column was renamed to make it consistent with other datasets, amounts stated in rupees were also converted to dollar values in this dataset, characters such as white spaces, commas and currency symbols were all removed from the amount column. The amount values were converted to float data type from object data type.
(iii)2020 DATASET:
The “column10” which was found to contain null values only was dropped.
(iv)2021 DATASET
No cleaning exercise was conducted on the 2021 dataset.

## DATA PREPARATION

Given the improved state of all four (4) datasets, they were all merged into one dataframe.
Column names were changed from their previous states to “Company_Brand”. “Stage”, “Sector”, “What it does”, and “HeadQuarter”.
Rows with words such as “Undisclosed”, “Upsparks” and others were cleaned out of the concatenated dataframe. Rows with mixed values for amount and stage columns were swapped back to their correct places. The Company_Brand column was cleaned to reflect better case types. The Sector column was mapped in order to reduce its number of unique categories.
Other columns were cleaned in order to have them standardized, mostly by changing their case types, changing of data type from float to integer, and reducing the number of categories that they hold.
We realised that this was an investigation into start-ups and so had to ensure that the companies did reflect that status by removing companies that had been in existence for longer than 5years.
After all the cleaning exercise was satisfactorily completed, we proceeded to conduct an Exploratory Data Analysis of what was left of the dataframe (which had about 2,144 rows from the initial 2,878 rows).

## DATA CLEANING

The data used in this analysis was sourced from three different sources, github, sql server and onedrive, a connection was created with a connection string defined in the '.env' file

1. Data Collection: Gathering raw data from online database.

2. Data Integration: Consolidating data from different sources into a unified dataset.

3. Missing Value Handling: Identifying and dealing with missing values through imputation or removal.

4. Outlier Detection: Detecting and handling outliers that could skew the analysis results.

5. Normalization and Standardization: Ensuring consistency and comparability of data by normalizing or standardizing where necessary.

6. Data Validation: Verifying the integrity of the cleaned dataset to ensure accuracy in subsequent analyses.

## DATA ANALYSIS

### (i) UNIVARIATE DATA ANALYSIS

The univariate data analysis for numerical variables can be seen below.

![Univariate Data Analysis](project/univariate.jpg?raw=true "Univariate Data Analysis")

As can be seen from the image above, the Amount variable had a mean value of $101,098,600, with minimum and maximum values of $876 and $150,000,000,000 respectively, as well as a standard deviation of approximately $3,239,380.

The Year variable had a mean of 2020, a minimum and maximum of 2018(the start year) and 2021(the end year), and a standard deviation of 1.

The Years of existence variable had a mean of 3years, a minimum and maximum of 0years and 5years respectively, and a standard deviation of 1.

The distribution of numerical variables is presented in the image below.

![Numerical Variables Distribution](project/numerical_dist.jpg?raw=true "Numerical Variables Distribution")

The Univariate distribution of Main Sector, Industry, Stage, and HeadQuarter variables are presented below

![Main Sector](project/main_sector.jpg?raw=true "Main Sector")

![Distribution of Industry](project/industry.jpg?raw=true "Industry Distribution")

![Distribution of Stage](project/stage_freq.jpg?raw=true "Distribution of Stage")

![Distribution of HeadQuarter](project/hqtr.jpg?raw=true "Distribution of HeadQuarter")

### (ii) BIVARIATE ANALYSIS

We looked into the relationships that exists between some select categorical and numerical variables and present our findings below

![Main Sector vs Amount](project/top_sector_with_highest_funding.jpg?raw=true "Top Sectors by Amount")

From the image above, Fintech is the Main Sector with the most fundings.

![Main Sector vs Years of Existence](project/successful_start_up_sectors.jpg?raw=true "Main Sector vs Years of Existence")

From the image above, we can see that the top 10 Main Sectors by Years of Existence. They include Transport & Logistics, Fintech, Food & Beverages, Healthtech, Business, E-commerce, Healthcare & Wellness, Technology, Edtech, and Finance in no particular order.

## DATA REPRESENTAION

The cleaned data was represented in structured formats suitable for analysis. This included organizing data into tables and saving the unified dataset as a single '.csv' file. Visualization techniques such as charts, graphs, and maps were also employed to present key findings effectively.

## ANALYSIS METHODS

Various analytical methods and techniques were utilized to extract insights from the data:

1. Descriptive Statistics: Summarizing key metrics such as mean, median, mode, and standard deviation to describe the central tendency and dispersion of variables.
2. Time-Series Analysis: Examining trends and patterns over time to understand the evolution of the startup ecosystem.
3. Correlation Analysis: Investigating relationships between different variables, such as funding amount and startup success rate.
4. Segmentation Analysis: Grouping startups based on common characteristics (e.g., sector, funding stage) and analyzing each segment separately.
5. Predictive Modeling: Building predictive models to forecast future trends or identify factors influencing startup performance.

# CONTRIBUTORS

This is an LP1 project completed by

- [Prince Acquah Rockson](https://github.com/parockson)
- [Etebom Ntuk](https://github.com/netebom)
- [Elvis Obeng](https://github.com/mabrony)
- Mohammed Idris
- [Celestine Jerop Kaplelach](https://github.com/cjerop)
- [Andy Konney](https://github.com/drewmacony)

## Usage

To replicate or extend the analysis conducted in this project, follow these steps:

1. Clone the Repository: Clone this repository to your local machine using git clone https://github.com/parockson/analysis-into-indian-startup-ecosystem.git.

2. Install Dependencies: Ensure all necessary dependencies are installed as per the requirements specified in requirements.txt.
   pip install python-dotenv
   pip install pyodbc
   pip install numpy
   pip install pandas
   pip install seaborn
   pip install scipy
   pip install jupyterlab

## activate by using the script below

.\venv\Scripts\activate

3. Run Analysis Scripts: Execute the analysis scripts provided in the repository, following any instructions or guidelines provided in the README or code comments.

4. Explore Results: Explore the generated results, visualizations, and findings to gain insights into the Indian startup ecosystem.
   .\venv\Scripts\activate

## CONTRIBUTIONS

Contributions to this project are welcome! If you have suggestions for improvement, new analyses to conduct, or additional data sources to incorporate, please open an issue or submit a pull request.

## LICENSE

This project is licensed under the MIT License, which means you are free to use, modify, and distribute the code for any purpose, provided you include the appropriate license information. See the LICENSE file for more details.

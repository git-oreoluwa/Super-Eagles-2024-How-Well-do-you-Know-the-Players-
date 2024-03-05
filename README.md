# Uncovering the Super Eagles 2024: What Surprises Await in Their Player Profiles?

## Introduction
This project aims to uncover the Super Eagles 2024 player profiles. Leveraging Python's BeautifulSoup and requests libraries for web scraping, followed by Pandas and Mathplotlib for Exploratory Data Analysis(EDA) and Visualization respectively, this project offers a comprehensive dive into the players' attributes and statistics.

### The Analysis
The purpose of this analysis was to gain deeper insights into the players. Specifically, I aimed to identify the players with the highest goal scorers, significant market values, most international caps, their respective positions, aggregate data on their age, height, and caps by position, as well as to provide a brief profile of each player. This analysis was done between the 14th of February 2024 to the 22nd of February 2024.
### The Analysis Process
To understand my data and get my desired insights from my analysis, I needed to follow certain steps. These steps are important because each one is necessary to make sure the data is processed correctly and provide me with helpful information. Here are the steps I followed:
1.	Data Gathering
2.	Data Cleaning and Preparation
3.	Data Preprocessing
4.	Exploratory Data Analysis (EDA)
5.	Data Visualization
   
## Data Gathering

<p>First, I utilized Python libraries BeautifulSoup and requests to scrape player details from the web. Then, I identified the table containing player information by extracting headers ("th") and individual row data ("td"). Subsequently, I gathered the players' jersey numbers, names, positions, dates of birth/ages, clubs, heights, preferred foot, international matches, goals, debut information, and market values from the designated website. </p>
<p>However, the data obtained initially was disorganized, as depicted in the image below.<p/>
<img src="https://github.com/git-oreoluwa/Google_Data_Analytics_Capstone_Cyclistic_Case_Study/assets/110780775/7845b4be-89e4-4394-ba98-a5255066e9c0"/>
  
## Data Cleaning and Preparation
It's well known that a significant portion of time in any analytical process is dedicated to data cleaning, and my experience was no exception.
After thoroughly examining my dataset for missing data, irrelevant features, and duplicate values, I identified duplicate rows and promptly removed them. Additionally, I discovered that the club titles were not visible in the dataset and had to be extracted from the "title" attribute of the <a> tag. I replaced the item at index 4 with the extracted club title before appending the row to the correct header columns in the dataframe, "df".
Furthermore, I encountered inconsistencies in some values within the dataset. For instance, the "International matches" and "Goals" columns contained "-" values, which I replaced with "0". Additionally, I standardized the format of the "Height" column by replacing 'm' with a space and ',' with '.'. To enhance clarity, I renamed certain columns, such as changing "Market value" to "Market value (EURO €)" and "Height" to "Height (m)".
<p> Lastly, to ensure the data remained current, I updated some values that were last recorded in December 2023.</p>
<img src = "https://github.com/git-oreoluwa/Google_Data_Analytics_Capstone_Cyclistic_Case_Study/assets/110780775/974b18c1-29d9-4ce9-9f1c-3f991185ab78"/>

## Data Preprocessing
Before delving into any meaningful analysis of my dataset, I needed to reorganize and transform it. Here are the steps I took:
1.	I converted the "Debut" column to datetime format, then created a new column called "Years Played" by calculating the difference between the present date and the debut date.
2.	Utilizing the regex function in Python, the "Date of birth/Age" column was split into two separate columns to extract the age.
3.	I removed the Euro symbol from the 'Market value(EURO €)' column and converted the decimal strings representing values in thousands ('k') or millions ('m') to their corresponding numerical values in thousands, thus standardizing the format of the data for analysis.
4.	I converted specific columns in the DataFrame 'df' to different data types. Specifically, I converted the 'Player', 'Position', 'Club', and 'Foot' columns to string data types, the 'Height (m)' column to float data type, the 'Age' and 'Goals' columns to integer data types, and the 'Date of Birth' column to datetime data type using Pandas functions such as astype() and pd.to_datetime().
<p></p>
<img src = "https://github.com/git-oreoluwa/Google_Data_Analytics_Capstone_Cyclistic_Case_Study/assets/110780775/4b84bfca-199a-4516-ab54-0f9fb4152725"/>

## Exploratory Data Analysis (EDA)
In the exploratory data analysis (EDA) process, I began by gaining an overview of my DataFrame's structure using the df.info() function, which provided valuable insights into the data types and the presence of any missing values. Next, to further understand the numerical aspects of the dataset, I utilized the df.describe() function to generate summary statistics for numerical columns. These statistics offered key insights into the distribution of the data, allowing for a better understanding of its characteristics.

<p>Thereafter, I focused on exploring the relationships between specific columns of interest, including 'Age', 'International matches', 'Height (m)', 'Goals', 'Market value (EURO €)', and 'Years Played'. I constructed a correlation matrix to identify any potential relationships or patterns among these variables. Then I visualized the correlation matrix using a heatmap, which provided a clear visual representation of the correlation coefficients between the selected columns. </p>

<img src = "https://github.com/git-oreoluwa/Google_Data_Analytics_Capstone_Cyclistic_Case_Study/assets/110780775/ec9f861f-94c5-47e6-8982-c803fec65d71" width="400" height="320"/>

This comprehensive approach to exploratory data analysis helped unveil insights and patterns within the dataset, laying the groundwork for further analysis and interpretation.

## Data Visualization
For visualisation, I exported my final csv file to <a href = "https://public.tableau.com/app/profile/oreoluwa.folorunsho./viz/Super-Eagles-2024-How-Well-do-you-Know-the-Players-/Dashboard1#1">Tableau</a> and I created a dashboard to better display my findings and communicate the analysis.

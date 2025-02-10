# GenZ Dating App Data Analysis

## Overview
This project analyzes the **GenZ Dating App** dataset to explore user demographics, app preferences, and usage patterns. The analysis involves data preprocessing, feature engineering, and visualization to gain insights into user behavior on dating apps.

## Dataset Overview
This dataset contains information about users' app usage, demographics, preferences, and challenges in using dating applications. It includes details on primary and secondary app choices, usage frequency, satisfaction levels, and desired features.

| Column Name                   | Data Type | Description |
|--------------------------------|----------|-------------|
| User_ID                        | int      | Unique identifier for each user |
| Age                            | int      | Age of the user |
| Gender                         | category   | Gender identity of the user |
| Location                       | category   | City where the user is based |
| Education                      | category   | Highest level of education completed |
| Occupation                     | category   | Employment status or job role of the user |
| Primary_App                    | category   | The main dating app the user prefers |
| Secondary_Apps                 | category   | Other dating apps the user uses |
| Usage_Frequency                | category   | How often the user engages with dating apps (e.g., daily, weekly, monthly) |
| Daily_Usage_Time               | category   | Time spent on the apps in hours/minutes format |
| Reason_for_Using               | category   | The user's motivation for using dating apps (e.g., finding a partner, casual dating) |
| Satisfaction                   | category      | Satisfaction rating on a scale (e.g., 1-5) |
| Challenges                     | category   | Issues faced while using dating apps (e.g., safety concerns, time-wasting) |
| Desired_Features               | category   | Features users wish to have in dating apps |
| Preferred_Communication        | category   | The most preferred mode of communication (e.g., text, voice notes, video calls) |
| Partner_Priorities             | category   | The order of priority for selecting a partner (e.g., values > personality > appearance) |
| Daily_Usage_Time_in_Minutes    | int      | Numeric representation of daily usage time in minutes |


## Data Preprocessing
### Handling Missing Values
- Used **backfill** and **forward fill** methods to handle missing values in categorical columns like `Primary_App`, `Secondary_Apps`, and `Challenges`.
- Replaced remaining missing values in `Primary_App` with the **mode** of the column.
- Verified that no missing values remained after processing.

### Data Cleaning
- Converted all categorical string values to **lowercase** for consistency.
- Converted categorical variables to the **category** data type to optimize memory usage.
- Ensured `Satisfaction` was properly categorized.
- Converted `Daily_Usage_Time` into numerical minutes and stored in `Daily_Usage_Time_in_Minutes`.
- Missing values in `Primary_App`, `Secondary_App` and `Challenges` were found in the dataset and filled them using backfill and forward fill because the value counts of the entries in each column didn't have any significant difference so I didn't think it'll be good to fill  it with the mode.
- Ensured that object columns were converted to category data types and `Satisfaction` was also converted to category data type.
- Checked for duplicates but there were none available.
- Standardized categorical labels to avoid inconsistencies.

### Data Type Transformation
- Converted `Daily_Usage_Time` from a text format (e.g., "2 hours 30 minutes") into an integer representing **total minutes**.
- Changed `Daily_Usage_Time_in_Minutes` to an integer data type.

## Exploratory Data Analysis (EDA)
### Summary Statistics & Data Integrity
- Verified there were **no duplicate rows** in the dataset.
- Generated summary statistics using `df.info()` and `df.describe()`.

### Correlation Analysis
- Computed and visualized a **correlation matrix** using a heatmap to identify relationships between numerical variables.

### Aggregation & Grouping
- Analyzed **satisfaction levels** and average usage time based on `Gender`, `Age`, `Location`, and `Primary_App`.
- Created **pivot tables** to compare app usage statistics.

### Visualizations
1. **User Demographics**
   - Distribution of `Age`, `Gender`, and `Location` using bar charts and count plots.
   - Verified that no demographic group was overrepresented.
2. **Usage Patterns**
   - **Boxplots** to analyze `Age` and `Daily_Usage_Time_in_Minutes`.
   - **Histograms & KDE plots** to visualize usage time distributions.
3. **App Preferences**
   - **Stacked bar charts** to analyze `Primary_App` preferences across genders.
   - **Line plots** to track app preferences across different age groups.
4. **Geographical Analysis**
   - Mapped city-wise app usage using **Plotly scatter geo-plots**.

## Feature Engineering
- Created a new feature, **`Active_App_Count`**, representing the total number of dating apps used per user.
- One-Hot Encoded categorical variables for machine learning compatibility.
- Applied **MinMax Scaling** to normalize `Age` and `Daily_Usage_Time_in_Minutes`.

## Final Processed Dataset
- Exported the cleaned dataset as `version_1.csv` for further modeling.



---

## Task 8 Answers
1. **Insights for Expanding into Rural India**  
- **App Usage Patterns** – Understanding how frequently users engage with dating apps and their daily screen time can help determine if rural users would be willing to adopt similar behaviors.
- **Primary & Secondary App Preferences** – If the dataset contains insights on why users choose certain apps, it can help shape an app that aligns with rural preferences.  
- **Challenges Faced by Users** – If challenges like **privacy concerns**, **network issues**, or **social stigma** appear in urban areas, they could be more pronounced in rural areas. Addressing these proactively would be crucial.  
- **Demographics & Satisfaction Levels** – Understanding age groups, gender distribution, and **what makes users satisfied or dissatisfied** will help in tailoring the app’s features.  
- **Geographical Insights** – If certain locations show more engagement, the same strategy can be adapted to rural settings with cultural modifications.

2. **Two Features for a New Dating App Based on This Data**  
- **AI-Based Matchmaking with Local Cultural Filters**  
   - A feature that **matches users based on cultural preferences, traditions, and local languages**. The dataset likely shows how preferences vary by location, so a **region-based matching algorithm** could enhance engagement.  

- **Offline Mode & Low-Bandwidth Compatibility**  
   - Rural areas often struggle with **internet connectivity**. Implementing an **offline mode** that allows users to browse profiles and send messages when they regain internet access (similar to WhatsApp's offline messaging) would improve accessibility.
 

3.  **Biggest Data Cleaning Challenges**  
- **Handling Missing Values**  
   - Many key columns (`Primary_App`, `Secondary_Apps`, `Challenges`) had missing values that required careful **backfill, forward fill, and mode-based imputation** to ensure data integrity.  

- **Inconsistent Data Formats**  
   - `Daily_Usage_Time` was stored in a **non-standard format** ("2 hours 30 minutes"), requiring conversion into total minutes for proper analysis.  

- **Categorical Data Standardization**  
   - Strings had inconsistent **capitalization and spacing**, which needed standardization (`lowercasing` and trimming spaces).  


 

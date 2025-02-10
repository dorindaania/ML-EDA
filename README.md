# Dataset Overview
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

# Data Cleaning Steps

1. **Standardized Time Format:** Converted `Daily_Usage_Time` into numerical minutes and stored in `Daily_Usage_Time_in_Minutes`.
2. **Checked for Missing Values:** Missing values in `Primary_App`, `Secondary_App` and `Challenges` were found in the dataset and filled them using backfill and forward fill because the value counts of the entries in each column didn't have any significant difference so I didn't think it'll be good to fill  it with the mode.
3. **Data Type Consistency:** Ensured that object columns were converted to category data types and `Satisfaction` was also converted to category data type.
4. **Removed Duplicates:** Checked for duplicates but there were none available.
5. **Ensured Gender Categorization:** Standardized gender labels to avoid inconsistencies.




# TikTok Claims Classification EDA & Data Visualization Project

![](tiktok.png)

## Project Overview

In this project, our team is working on a data analysis task for TikTok, focusing on Exploratory Data Analysis (EDA) and data visualization. We have completed the initial project proposal and have organized the TikTok dataset using Python.

## Scope of the Analysis

We received a request from Orion Rainier, a Data Scientist at TikTok, to perform EDA and create visualizations. The management team expects a comprehensive report with structured and cleaned data, along with various matplotlib/seaborn visualizations. Key visualizations include comparing claim counts to opinion counts, boxplots for important variables, and a breakdown of "author ban status" counts.

## Visualization Tools

We will be using Python for creating matplotlib/seaborn visualizations in the form of a Jupyter notebook. Additionally, the management team has requested Tableau visualizations. We will create a Tableau dashboard that provides a simple comparison of claims versus opinions counts and stacked bar charts for variables such as video view counts, video like counts, video share counts, and video download counts.

## Inclusive Design

We understand that accessibility is essential, and one of the stakeholders, the assistant director, has visual impairments. We will ensure that our Tableau dashboard is designed in a way that is easy to comprehend for non-data-savvy individuals and is accessible to those with visual impairments.

## Deliverables

0. Course 3 PACE Strategy Document: It outlines project details, questions, and action items for each stage.
1. Jupyter notebook containing the EDA process, data cleaning, and matplotlib/seaborn visualizations.
2. Tableau dashboard presenting a simple comparison of claims versus opinions counts and stacked bar charts for relevant variables.
3. Executive summary to provide a concise overview of our analysis.

## Data Dictionary

The dataset contains 19,383 rows, where each row represents a different published TikTok video in which a claim/opinion has been made. There are 12 columns in the dataset, each with a specific type and description.

| Column Name            | Type  | Description                                                                                             |
|------------------------|-------|---------------------------------------------------------------------------------------------------------|
| #                      | int   | TikTok assigned number for video with claim/opinion.                                                   |
| claim_status           | obj   | Whether the published video has been identified as an "opinion" or a "claim."                          |
| video_id               | int   | Random identifying number assigned to the video upon publication on TikTok.                           |
| video_duration_sec     | int   | How long the published video is measured in seconds.                                                   |
| video_transcription_text | obj  | Transcribed text of the words spoken in the published video.                                           |
| verified_status        | obj   | Indicates the status of the TikTok user who published the video in terms of their verification.       |
| author_ban_status      | obj   | Indicates the status of the TikTok user who published the video in terms of their permissions.        |
| video_view_count       | float | The total number of times the published video has been viewed.                                         |
| video_like_count       | float | The total number of times the published video has been liked by other users.                          |
| video_share_count      | float | The total number of times the published video has been shared by other users.                         |
| video_download_count   | float | The total number of times the published video has been downloaded by other users.                     |
| video_comment_count    | float | The total number of comments on the published video.                                                   |

Note: "obj" represents the object data type, while "int" and "float" represent integer and floating-point data types, respectively.

## PACE Strategy

The PACE strategy is a structured problem-solving approach that guides us through the key stages of data analysis and decision-making. PACE stands for Plan, Act, Check, and Evolve. In the Plan stage, we focus on understanding the problem, defining objectives, and devising a clear plan to approach the data analysis process systematically. This involves identifying the relevant data columns and variables, understanding the units of the variables, making initial presumptions about the data, checking for missing or incomplete data, and ensuring data format consistency. The Plan stage sets the foundation for the subsequent stages by guiding us in gathering the right data and establishing a roadmap for analysis. As we progress through the Act, Check, and Evolve stages, we execute the plan, assess outcomes, and continuously refine our approach based on new insights. The PACE strategy empowers us to make data-driven decisions, ensuring that our analysis is thorough, reliable, and adaptable to the evolving needs of the project.

### Plan Stage - Explaining Initial Steps for the Project

The first stage of the PACE strategy for problem-solving is "Plan." During this stage, the primary focus is on understanding the problem at hand, defining the objectives, and devising a plan to approach the problem systematically.

To identify outliers, various methods can be employed depending on the nature of the data. Some common techniques include:

1. **Visualizations:** Plotting the data using scatter plots, box plots, or histograms can reveal potential outliers that fall far outside the majority of the data points.

2. **Statistical Methods:** Utilizing statistical measures such as Z-scores, standard deviations, or the interquartile range (IQR) can help identify observations that deviate significantly from the mean or median.

3. **Domain Knowledge:** Sometimes, domain experts can recognize outliers based on their understanding of the context and the expected range of values.

Once potential outliers have been identified, the decision to keep or exclude them from future models depends on the specific situation and the impact of outliers on the analysis or model. Consider the following factors:

1. **Data Quality:** Evaluate whether the outliers are genuine data points or errors in data collection. If they are genuine and represent valid but rare occurrences, they might carry essential information and should be kept.

2. **Data Distribution:** Assess the impact of outliers on the overall data distribution. If the data is heavily skewed, removing extreme outliers might help create a more normal distribution and improve model performance.

3. **Model Sensitivity:** Some models, like linear regression, are sensitive to outliers and may produce biased results. In such cases, it might be appropriate to exclude outliers to achieve more accurate predictions.

4. **Sample Size:** If the dataset is small, removing even a few outliers can significantly reduce the data available for analysis, potentially leading to biased results.

5. **Business Objectives:** Consider the business context and whether outliers have a direct impact on the objectives of the analysis or model. If outliers are crucial in decision-making, keeping them might be necessary.

Ultimately, the decision to keep or exclude outliers should be made thoughtfully, with a clear understanding of their impact on the analysis or model's validity and the overall goals of the problem-solving process.

### Data Columns and Relevant Variables
In this project, we are working with a dataset that contains 19,383 rows and 12 columns. Each row represents a different published TikTok video in which a claim/opinion has been made. The columns in the dataset are:

1. `#` (int)
2. `claim_status` (obj)
3. `video_id` (int)
4. `video_duration_sec` (int)
5. `video_transcription_text` (obj)
6. `verified_status` (obj)
7. `author_ban_status` (obj)
8. `video_view_count` (float)
9. `video_like_count` (float)
10. `video_share_count` (float)
11. `video_download_count` (float)
12. `video_comment_count` (float)

For our deliverable, the most relevant variables will likely be:
- `claim_status`: To understand the distribution between "opinion" and "claim" videos.
- `video_duration_sec`: To examine the length of videos and its relation to claims or opinions.
- `video_transcription_text`: To analyze the content of videos and explore any patterns in claims or opinions.
- `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`: To gain insights into the popularity and engagement of videos containing claims or opinions.

### Units of Variables
The units for most of the variables are clearly specified:
- `#`, `video_id`: Integer values.
- `video_duration_sec`: Time duration in seconds.
- `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`: Numeric counts.

### Initial Presumptions about the Data
Before starting the Exploratory Data Analysis (EDA), we might presume the following about the data:
- We may expect to see a mix of "opinion" and "claim" videos in the dataset.
- Longer video durations might be associated with more in-depth content or claims.
- Videos with a higher view, like, share, and download counts may indicate more popular content.
- "Verified" users might have a higher proportion of claims compared to "not verified" users.
- "Banned" users could potentially have a higher number of claims due to their contentious nature.

### Missing or Incomplete Data
As part of the initial data examination, we need to check for any missing or incomplete data in the dataset. Addressing missing data is crucial to ensure the accuracy and reliability of our analysis.

### Data Format Consistency
We must verify if all pieces of the dataset are in the same format. Inconsistent data formats might lead to errors during analysis and visualizations. Ensuring data format consistency will be an essential step in preparing the data for EDA.

### Required EDA Practices
To begin this project, we will employ several EDA practices:
- Summary statistics to understand the distribution and central tendencies of numerical variables.
- Visualizations, such as scatter plots, box plots, and histograms, to identify potential outliers and patterns in the data.
- Categorical visualizations, like bar charts, to explore the distribution of "claim_status," "verified_status," and "author_ban_status."
- Text analysis or word cloud to gain insights from the "video_transcription_text" variable.

By conducting these initial EDA practices, we will be well-equipped to derive meaningful insights from the dataset and proceed with the subsequent stages of the project.

## Analyse Stage

Based on the provided `.head()` of the dataset, here is an initial analysis of the data:

1. **Data Columns and Variables**: The dataset contains several columns, including `#`, `claim_status`, `video_id`, `video_duration_sec`, `video_transcription_text`, `verified_status`, `author_ban_status`, `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`.

2. **Data Size and Structure**: The dataset has at least 5 rows and 12 columns. Each row represents a different published TikTok video in which a claim/opinion has been made. The columns contain information related to the video content, verification status, view counts, like counts, share counts, download counts, comment counts, and more.

3. **Data Types**: The data types for each column appear to be appropriate. For example, numerical columns like `video_duration_sec`, `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count` have float or integer data types, while textual data like `claim_status`, `video_transcription_text`, `verified_status`, and `author_ban_status` have object (string) data types.

4. **Missing Data**: From the provided sample, we cannot ascertain whether there is missing data. We would need to use the `.info()` function to check for non-null counts and see if there are any columns with missing values.

5. **Outliers**: We can identify potential outliers by using the `.describe()` function, which will provide summary statistics for the numerical columns. We can also visualize the data using box plots or scatter plots to detect extreme values that might be outliers.

As requested, we will now proceed to use the `.info()` function to check for missing data, and the `.describe()` function to explore the distribution of numerical variables and identify potential outliers.

Based on the provided information, here is a further analysis of the data:

1. **Data Size and Shape**: The data contains 19,382 rows and 12 columns, making it a moderately large dataset with 19,382 data points and 12 different attributes.

2. **Data Types and Missing Data**: The data types for each column are as follows:
   - Integer columns: `#`, `video_id`, and `video_duration_sec`.
   - Float columns: `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`.
   - Object (string) columns: `claim_status`, `video_transcription_text`, `verified_status`, and `author_ban_status`.
   
   The `.info()` function shows that some columns have missing data. Notably, `claim_status`, `video_transcription_text`, `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count` have 19084 non-null entries out of 19382, indicating that there are missing values in these columns.

3. **Handling Missing Data**: To deal with the missing data, we will need to decide on an appropriate approach. Depending on the importance and amount of missing data, we might consider imputation techniques, such as filling missing values with mean, median, or mode, or we may opt to remove the rows with missing values. The choice will depend on the specific context of the analysis and the impact of missing data on the objectives of the project.

4. **Outliers**: To identify outliers, we will use the `.describe()` function to generate summary statistics for the numerical columns: `video_duration_sec`, `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`. This will help us detect extreme values that could potentially be outliers. Additionally, visualizations like box plots can be helpful to visually assess the presence of outliers in the data.

Before proceeding with the analysis and visualization, addressing missing data is a critical step to ensure the accuracy and reliability of the results.

Based on the provided .describe() command, here is an analysis of the numerical columns:

`# and video_id`: The columns # and video_id represent identification numbers for each video. The mean and median values are close, indicating that these columns likely contain sequential or unique identifiers for each video.

`video_duration_sec`: The video_duration_sec column represents the duration of the published videos measured in seconds. The mean video duration is approximately 32.42 seconds, with a minimum duration of 5 seconds and a maximum duration of 60 seconds.

`video_view_count`: The video_view_count column represents the total number of times the published videos have been viewed. The mean view count is approximately 254,708.56, with a minimum of 20 views and a maximum of 999,817 views.

`video_like_count`: The video_like_count column represents the total number of times the published videos have been liked by other users. The mean like count is approximately 84,304.64, with a minimum of 0 likes and a maximum of 657,830 likes.

`video_share_count`: The video_share_count column represents the total number of times the published videos have been shared by other users. The mean share count is approximately 16,735.25, with a minimum of 0 shares and a maximum of 256,130 shares.

`video_download_count`: The video_download_count column represents the total number of times the published videos have been downloaded by other users. The mean download count is approximately 1,049.43, with a minimum of 0 downloads and a maximum of 14,994 downloads.

`video_comment_count`: The video_comment_count column represents the total number of comments on the published videos. The mean comment count is approximately 349.31, with a minimum of 0 comments and a maximum of 9,599 comments.

### Select data vosualization types

For the Exploratory Data Analysis (EDA) of the TikTok dataset, several data visualization types can help us understand and explain the data. Considering the distribution of the data and the specific data columns we'll be using, the following visualization types would be most helpful:

1. **Bar Chart**: A bar chart would be useful for visualizing categorical data, such as the distribution of `claim_status`, `verified_status`, and `author_ban_status`. It will help us see the frequency of each category and understand the proportion of claims and opinions, as well as the distribution of verified and banned users.

2. **Box Plot**: Box plots are effective for visualizing the distribution of numerical data, such as `video_view_count`, `video_like_count`, `video_share_count`, `video_download_count`, and `video_comment_count`. Box plots will help us identify potential outliers and understand the spread and central tendency of these variables.

3. **Histogram**: Histograms are suitable for visualizing the distribution of continuous numerical data, such as `video_duration_sec`. They will allow us to observe the frequency of different video durations and identify patterns in the data.

4. **Scatter Plot**: Scatter plots can be useful for exploring relationships between two numerical variables, such as `video_view_count` and `video_like_count`, or `video_view_count` and `video_share_count`. Scatter plots will help us identify any correlations or trends between these variables.

Notes: All the continuous variables can be also broked down by categorical variables specially the variable of most interest `clain_status`.

## PACE: Construct

In the Construct stage of the data analysis process, we leverage the insights gained from the previous stages to build meaningful visualizations that bring clarity and understanding to the TikTok dataset. Having assessed our data and understood its characteristics, it is time to embark on the task of plotting visualizations.

### Build Visualizations

The primary objective in this stage is to use appropriate data visualization techniques to effectively communicate patterns, trends, and relationships within the dataset. By selecting the most suitable visualization types, such as bar charts, box plots, histograms, and scatter plots, we aim to gain deeper insights into the distribution of variables, identify potential outliers, and explore connections between different data attributes.

Through well-crafted visualizations, we can unravel valuable information, enabling us to make data-driven decisions and present compelling findings to stakeholders and team members. This Construct stage lays the foundation for further analysis and helps us move forward with confidence, armed with a comprehensive understanding of the TikTok dataset.

## Execute: Jupyter Notebook

In the Execute step of the PACE strategy, we utilized a Jupyter Notebook to carry out an extensive data analysis on the TikTok dataset. The notebook incorporated Python libraries such as Pandas, Matplotlib, and Seaborn to perform data exploration, visualization, and cleaning. We began by understanding the dataset's size and structure, which comprised 19,382 rows and 12 columns. Leveraging the head() and info() functions, we gained a glimpse of the data's content and data types, identifying some missing values in certain columns.

To better understand the data distributions, we used various visualization types such as histograms, bar charts, and pie charts. The histogram of video duration in seconds revealed distinct patterns, suggesting the influence of popular dance songs repeatedly shared on the platform. The view count histogram indicated a right-skewed distribution, with the majority of videos having relatively low viewership, while a few videos had exceptionally high view counts.

Furthermore, we visualized the like, comment, share, and download counts, which exhibited similar right-skewed patterns with long tails. The pie chart comparing claim and opinion videos' view proportions provided valuable insights into the data's distribution.

During the data cleaning process, we handled missing values and outliers. By calculating the Interquartile Range (IQR) and identifying videos with counts exceeding 15 times the IQR, we identified and dealt with outliers. The notebook was instrumental in systematically exploring the data and extracting valuable information for further analysis and decision-making.

The Jupyter Notebook served as a powerful tool in documenting and presenting our data analysis steps, results, and visualizations in an organized and interactive manner. As we move forward with the project, the insights gained from this execution phase will guide subsequent steps and help achieve the project's objectives effectively.

## Tableau Visualization

[Dahsboard](https://public.tableau.com/authoring/TikTokVideos/LikesvsCommentsOpinions#1)

## Executive Summary

1. Video Duration in Seconds:
   - The distribution of video durations shows multiple modes, possibly indicating recurring posts of popular dance songs.
   - The majority of videos have durations between 5 and 6 seconds, with each bin representing around 1 second.

2. Video View Counts:
   - The distribution of video view counts is right or positively skewed, with a long tail.
   - Over 50% of the videos have less than 10,000 views, while the minimum view count is recorded at 20 views.
   - The 75th percentile of the data indicates that 75% of videos have 500,000 or fewer views.
   - The mean view count is significantly higher than the median, suggesting the presence of a few videos with exceptionally high view counts.
   - The video with the highest number of views received over 1 million views.

3. Video Like Count:
   - The distribution of video like counts exhibits a right or positive skew, with a long tail in the data.
   - Over 12,000 videos have less than 3,500 likes, and some videos received zero likes.
   - The 75th percentile of the data shows that 75% of videos have 125,000 or fewer likes.
   - The mean like count is notably higher than the median, indicating videos with a large number of likes.
   - The video with the most likes obtained more than 650,000 likes.

4. Video Comment Count:
   - The distribution of video comment counts displays a right or positive skew, with a long tail.
   - Over 50% of the videos have fewer than 10 comments, with some videos receiving zero comments.
   - The 75th percentile of the data reveals that 75% of the videos have fewer than 300 comments.
   - The mean comment count is substantially higher than the median, with the maximum reaching 9,599 comments.

5. Video Share Count:
   - The distribution of video share counts is right or positively skewed, with a long tail.
   - Over 50% of the videos have less than 720 shares, and some videos received zero shares.
   - The 75th percentile of the data shows that 75% of the videos have fewer than 18,300 shares.
   - The mean share count exceeds the median, with the maximum reaching 256,130 shares.

6. Video Download Count:
   - The distribution of video download counts is right or positively skewed, with a long tail.
   - Over 50% of the videos have less than 46 downloads, and some videos have zero downloads.
   - The 75th percentile of the data reveals that 75% of the videos have fewer than 1,200 downloads.
   - The video with the most downloads reached 15,000 downloads.

Additionally, we present the counts of videos by claim status and verify the median view count for each claim status. The data indicates that claim videos tend to have a higher median view count compared to opinion videos.

Finally, we explore the presence of outliers in each column using a threshold of 15 times the interquartile range (IQR). The results show that there are no outliers in the view count, like count, share count, and download count columns. However, there are 212 outliers in the comment count column.

These findings offer valuable insights into the TikTok dataset, facilitating the identification of patterns, trends, and outliers. As we continue with this project, these insights will guide data-driven decision-making and contribute to a deeper understanding of the TikTok platform.
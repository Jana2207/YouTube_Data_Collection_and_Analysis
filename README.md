# <center>✨ <u><b>YOUTUBE DATA COLLECTION AND ANALYSIS</b></u> ✨</center>

## 📋 Introduction
This project focuses on analyzing various aspects of YouTube channels and video content, including likes, dislikes, views, and comments. We also examine the effect of various factors, such as video length, publishing day, and video category on the performance metrics.

---

## 📝 Data Fields Explanation

### 1. `video_id`
- **Description**: Unique identifier for each YouTube video.
- **Example**: `dQw4w9WgXcQ`

### 2. `title`
- **Description**: The title of the YouTube video.
- **Example**: `How to Learn Python in 10 Minutes`

### 3. `description`
- **Description**: A detailed text description of the video content.
- **Example**: `In this video, we will go through the basics of Python programming...`

### 4. `published_at`
- **Description**: Date and time when the video was published on YouTube (ISO 8601 format).
- **Example**: `2023-08-24T14:00:00Z`

### 5. `channel_id`
- **Description**: Unique identifier for the YouTube channel that uploaded the video.
- **Example**: `UC_x5XG1OV2P6uZZ5FSM9Ttw`

### 6. `channel_title`
- **Description**: The name of the YouTube channel that uploaded the video.
- **Example**: `Google Developers`

### 7. `category_id`
- **Description**: Numeric ID representing the video category.
- **Example**: `10` (Music)

### 8. `category_name`
- **Description**: Human-readable name corresponding to the `category_id`. Defaults to `Unknown` if not found.
- **Example**: `Music`

### 9. `tags`
- **Description**: List of keywords associated with the video to help with discoverability.
- **Example**: `["python", "programming", "tutorial"]`

### 10. `duration`
- **Description**: Length of the video in ISO 8601 format (`PT` stands for "period of time").
- **Example**: `PT10M30S` (10 minutes and 30 seconds)

### 11. `definition`
- **Description**: Indicates the video quality, either `"hd"` (high definition) or `"sd"` (standard definition).
- **Example**: `hd`

### 12. `caption`
- **Description**: Specifies whether the video has captions available, either `"true"` or `"false"`.
- **Example**: `true`

### 13. `view_count`
- **Description**: Total number of views for the video.
- **Example**: `450000`

### 14. `like_count`
- **Description**: Number of likes the video has received.
- **Example**: `35000`

### 15. `dislike_count`
- **Description**: Number of dislikes the video has received.
- **Example**: `500`

### 16. `favorite_count`
- **Description**: Number of times the video has been added to users' favorites (deprecated, usually set to 0).
- **Example**: `0`

### 17. `comment_count`
- **Description**: Total number of comments on the video.
- **Example**: `1200`

---

## 🛠️ Procedure Followed in YouTube Data Collection and Analysis

### 1. 📊 Data Collection
The data for this project was collected using the YouTube Data API. API requests were made to retrieve metadata such as video IDs, titles, descriptions, view counts, likes, dislikes, comments, and other relevant details. The API also provided information about the channel, video category, duration, and publishing date.

### 2. 🧹 Data Cleaning and Preprocessing
After collecting the data, it was cleaned and preprocessed:
- **Handling Missing Data**: Missing values for fields like `tags` and `caption` were handled by filling them with default values or ignoring them during analysis.
- **Outlier Removal**: Outliers in fields such as `view_count` and `like_count` were detected and removed.
- **Duration Conversion**: Video durations were transformed from ISO 8601 format to a more readable format.
- **Feature Extraction**: New features like `posted_hour` were extracted from the `published_at` field to analyze trends over time.

### 3. 🔍 Exploratory Data Analysis (EDA)
EDA was conducted to uncover trends and relationships between the variables:
- **Viewership Trends**: Examined how views and engagement varied based on video category, length, and publishing time.
- **Correlation Analysis**: Explored relationships between metrics such as views, likes, dislikes, and comments.
- **Category Performance**: Analyzed which categories (e.g., Music, Education) performed best in terms of views and engagement.

### 4. 📈 Data Visualization
Visualizations were created to present the findings clearly:
- **📊 Histograms**: To show distributions of views, likes, and comments.
- **📊 Bar Charts**: For analyzing performance by video category and publishing day.
- **📊 Heatmaps**: To visualize correlations between variables such as likes, views, and comments.

---

## 🔍 Insights and Conclusions

### 1. Distribution Skewness

![Distribution Skewness](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/1.distribution.png)
The analysis reveals a **right-skewed distribution** across views, likes, and comments. This indicates that a limited number of videos have high engagement metrics, while the majority of the videos have lower counts.

---

### 2. Correlation Insights

![Correlation Insights](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/2.correlation.png)
The analysis shows strong positive correlations between the following:
- **View Count and Like Count**: Videos with higher views tend to accumulate more likes.
- **Like Count and Comment Count**: An increase in likes is often accompanied by an increase in comments.

---

### 3. Category Distribution

![Category Distribution](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/3.count_category.png)
- **Entertainment**: Approximately 75% of trending videos are categorized under Entertainment.
- **Professional Growth**: About 9% of the videos pertain to Professional Growth, including themes such as Education and Politics.

---

### 4. Engagement Trends

![Engagement Trends](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/4.average_category.png)
- **Entertainment**: Demonstrates consistent growth in both likes and comments as view counts increase.
- **Lifestyle**: Exhibits a higher average comment count relative to likes.
- **Music**: Attracts substantial views but tends to receive fewer average likes and comments.
- **People & Blogs**: Shows lower average views, yet their likes and comments are significantly higher.
- **Science & Technology**: Consistently garners both likes and comments as views rise.

---

### 5. Video Duration

![Video Duration](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/5.length_bins.png)
- **1-5 Minutes**: Videos in this range achieve optimal engagement in terms of views, likes, and comments.
- **0-1 Minute**: Short videos generally receive fewer comments in relation to their views and likes.
- **20-60 Minutes**: These longer videos generate higher view and like counts but receive comparatively fewer comments.

---

### 6. Tags and Views

![Tags and Views](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/6.tags.png)
- The analysis shows no strong relationship between the number of tags and views.
- **Recommendation**: Using 10-25 tags is recommended for enhanced visibility.
- A significant number of videos utilize approximately 20-30 tags.

---

### 7. Optimal Posting Times

![Optimal Posting Times](https://github.com/Jana2207/YouTube_Data_Collection_and_Analysis/blob/main/results/7.posted_hour.png)
- **Consistent Posting**: Most videos are posted between 8 AM and 4 PM.
- **Higher View Counts**: Videos posted between 7 AM to 9 AM and 3 PM to 5 PM tend to achieve higher initial view counts.
- **Slower View Growth**: Posting during 6 PM to 8 PM is associated with slower view growth.
- **Optimal Time to Post**: Between 7 AM to 5 PM, while the least effective time is 6 PM to 8 PM.

---

# 📱 Social Media Engagement Analytics

End-to-end data analysis of social media engagement metrics using **Python**: data cleaning, exploration, wrangling, statistical analysis, visualization, and business insights.

> **Python for Data Analysis Project | Data Analytics (DA), Module-End 5**

---

## 📌 Problem Statement

Social media platforms generate massive volumes of engagement data such as likes, comments, shares, impressions, and watch time. Analysing this data helps companies understand user behaviour, identify trends, and improve content performance.

This project works with a dataset of **5,000 social media posts** and covers data cleaning, transformation, NumPy/Pandas operations, exploratory data analysis, visualizations, and insight generation.

---

## 📂 Dataset

**File:** `social_media_engagement_5000.csv` (5,000 rows, 19 original columns)

| Column | Description |
|--------|-------------|
| `user_id` | Unique user identifier |
| `age`, `gender`, `country` | User demographics |
| `post_id` | Unique post identifier |
| `post_type` | image, reel, text, video |
| `post_category` | Content category (e.g., food) |
| `likes`, `comments`, `shares` | Engagement counts |
| `watch_time_sec` | Watch time in seconds |
| `impression_count` | Number of impressions |
| `posted_at` | Post date/time |
| `follower_count` | Followers of the user |
| `is_verified` | Verified account flag |
| `device_type` | Device used |
| `sentiment` | Post sentiment label |
| `hashtags` | Hashtags used in the post |
| `engagement_rate` | Engagement rate of the post |

**Engineered features:** `hashtag_count`, `engagement_score` (likes + comments + shares)

---

## 🗂️ Project Structure

```text
social-media-engagement-analytics/
│
├── social_media_engagement_5000.csv     # Dataset
├── social_media_analytics.ipynb         # Main notebook
└── README.md                            # Project documentation
```

---

## 🧰 Tech Stack

- Python 3.x
- NumPy, Pandas
- Matplotlib, Seaborn
- Plotly (interactive charts)
- Google Colab / Jupyter Notebook

```bash
pip install numpy pandas matplotlib seaborn plotly
```

---

## 🚀 How to Run

**Option 1: Google Colab**
1. Upload the notebook to Google Colab
2. Run the import cell and upload `social_media_engagement_5000.csv` when prompted

**Option 2: Local Jupyter**
```bash
git clone https://github.com/<your-username>/social-media-engagement-analytics.git
cd social-media-engagement-analytics
jupyter notebook social_media_analytics.ipynb
```
> Note: the `google.colab` upload cell only works in Colab. Locally, load the file with `pd.read_csv("social_media_engagement_5000.csv")`.

---

## 📋 Tasks Covered

### Task 1: Data Import & Setup
- Imported the CSV with Pandas
- Checked data types
- Converted `posted_at` to datetime (`dayfirst=True`)

### Task 2: Data Cleaning
| Area | Approach |
|------|----------|
| Missing values | Detected with `isnull().sum()`: 150 missing each in `age`, `gender`, `likes`, `comments`, `shares`, `sentiment` |
| Numeric imputation | Filled `age`, `likes`, `comments`, `shares` with the **median** |
| Categorical imputation | Filled `gender`, `sentiment` with the **mode** |
| Duplicates | Checked with `duplicated().sum()` (0 found) |
| Formatting | Reviewed category labels and min/max of likes, comments, shares |
| Feature cleaning | Extracted `hashtag_count`; reviewed sentiment labels |

### Task 3: Data Exploration (Pandas)
- `head()`, `tail()`, `shape`, `columns`, `info()`, `dtypes`
- `describe()` summary statistics
- `value_counts()`, `unique()`, `nunique()` for categorical fields
- Correlation matrix of numeric fields
- `groupby()` summaries (avg likes by post type, avg impressions by country)

### Task 4: Data Wrangling
- Split the DataFrame in two and recombined with `pd.concat()` (5,000 rows retained)
- Created `engagement_score` and `hashtag_count`
- Group summaries by `post_type`, `country`, and `sentiment`

### Task 5: Statistical Analysis
Columns: `likes`, `comments`, `shares`, `watch_time_sec`, `engagement_rate`, `follower_count`

- Mean, median, mode
- Standard deviation, variance
- Percentiles (25th, 50th, 75th)
- Skewness and kurtosis

### Task 6: Data Visualization

| Library | Plots |
|---------|-------|
| **Matplotlib** | Scatter (likes vs impressions), line (daily engagement trend), bar (posts by category), pie (gender distribution), histogram (age), box (engagement rate) |
| **Seaborn** | Count plot (post type), violin (followers by sentiment), pair plot (likes, comments, shares, engagement rate) |
| **Plotly** | Interactive scatter (impressions vs likes, colored by post type) |

---

## 🔍 Key Insights

### Content Performance
- **Best post type:** `video` (highest average engagement rate)
- **Best content category:** `food`
- **Top country by average engagement rate:** `Brazil`

### User Trends
- **Verified accounts** perform better, with an average engagement rate of about **1.05** vs **0.95** for non-verified accounts
- Age-wise engagement was analysed with `groupby("age")`

### Behavioral Insights
- Average **watch time by device type** compared using `groupby("device_type")`

### Sentiment Analysis
- Average engagement rate and engagement score compared across sentiment labels

*(Add your own observations after viewing the outputs, especially for age, device type, and sentiment.)*

---

## 💡 Concepts Demonstrated

- Data import, type conversion, and datetime handling
- Missing value imputation (median / mode)
- Feature engineering (`hashtag_count`, `engagement_score`)
- Aggregation with `groupby()`, and combining data with `concat()`
- Descriptive statistics and distribution shape (skewness, kurtosis)
- Static and interactive visualization

---

## 🔮 Possible Improvements

- Add the remaining required plots: Seaborn bar plot (avg likes by category), heatmap (correlation matrix), swarm plot (engagement vs device)
- Add a "best time of day for impressions" analysis using the hour from `posted_at`
- Add log-transformed metrics and outlier handling for likes, comments, shares
- Add Plotly line, bar, and bubble charts

---

## 👤 Author

**Revathi**
-

---

## 📄 License

This project is created for educational purposes as part of a Data Analytics course assignment.

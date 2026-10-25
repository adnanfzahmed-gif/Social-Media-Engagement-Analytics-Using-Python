# 📱 Social Media Engagement Analytics Using Python

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adnanfzahmed-gif/Social-Media-Engagement-Analytics-Using-Python/blob/main/%E2%80%9CSocial_Media_Engagement_Analytics%E2%80%9D.ipynb)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4c72b0)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-3F4F75?logo=plotly&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> Cleaning, exploring and visualising **5,000 social media posts** with Pandas, Matplotlib, Seaborn and Plotly to find out which content, audiences and countries drive the most engagement.

---

## 📌 Project Overview

Social platforms produce huge volumes of engagement data: likes, comments, shares, impressions, watch time and follower counts. This project turns a 5,000-post dataset into insights about **content performance, user behaviour, posting patterns and audience preferences**.

**What it covers**
- 🧹 Data cleaning: missing values, duplicates, data types and standardised text
- 🛠️ Feature engineering: hashtag count, age groups, posting hour
- 📐 Descriptive statistics and correlation analysis
- 🔎 `groupby` analysis and `merge` of summary tables
- 📊 17 static charts plus 2 interactive Plotly charts
- 💡 Business-oriented findings

---

## 📂 Repository Contents

| File | Description |
|---|---|
| `“Social_Media_Engagement_Analytics”.ipynb` | Full analysis notebook (opens in Google Colab via the badge above) |
| `Social_Media_Engagement_Analytics_Using_Python.pdf` | Project document: problem statement, objectives, dataset description and walkthrough |

---

## 🗂️ Dataset

`social_media_engagement_5000.csv`: **5,000 rows × 19 columns**, loaded directly from a public dataset repository inside the notebook.

| Group | Columns |
|---|---|
| User | `user_id`, `age`, `gender`, `country`, `follower_count`, `is_verified`, `device_type` |
| Post | `post_id`, `post_type`, `post_category`, `hashtags`, `posted_at`, `sentiment` |
| Engagement | `likes`, `comments`, `shares`, `watch_time_sec`, `impression_count`, `engagement_rate` |

**Composition:** 10 countries (about 500 posts each), 4 post types, 8 categories, 3 device types, 3 genders and 3 sentiment classes. Only 9.7% of posts (483) come from verified accounts.

---

## 🔧 Methodology

| Step | What was done |
|---|---|
| **1. Import and inspect** | Loaded the CSV; checked shape, types and statistics |
| **2. Missing values** | 150 missing values in each of `age`, `gender`, `likes`, `comments`, `shares` and `sentiment`. Numeric columns filled with the **median**; gender and sentiment with the **mode** |
| **3. Duplicates** | 0 duplicate rows |
| **4. Types and text** | Counts converted to integers; `posted_at` converted to datetime; sentiment trimmed and lower-cased |
| **5. Feature engineering** | `hashtag_count`, `age_group` (7 bands) and `post_hour` |
| **6. Exploration** | Value counts, correlation matrix, `groupby` summaries |
| **7. Merge** | Combined average likes and average engagement by post type into one summary table |
| **8. Statistics** | Mean, median, mode, standard deviation, variance, percentiles, skewness, kurtosis |
| **9. Visualisation** | Matplotlib, Seaborn and interactive Plotly charts |

---

## 📊 Key Findings

> ⚠️ **Read the averages with care.** `engagement_rate` is extremely skewed: mean 0.96, median 0.25, maximum 191.5 (skewness 18.8, kurtosis 483). A few extreme posts pull every group average upward, so the rankings below show *average* engagement and may differ from the typical post.

### Content
| Post category | Avg engagement rate |
|---|---|
| 🥇 Food | 1.359 |
| Tech | 1.160 |
| Lifestyle | 1.091 |
| Music | 0.889 |
| Fitness | 0.866 |
| Education | 0.844 |
| Fashion | 0.807 |
| Travel | 0.702 |

| Post type | Avg likes | Avg engagement rate |
|---|---|---|
| Video | 10,189 | **1.122** |
| Text | 10,100 | 1.065 |
| Image | 10,105 | 0.896 |
| Reel | 10,038 | 0.783 |

Likes are almost identical across post types (about 10,000), so the differences in engagement come from the other side of the ratio.

### Audience and geography
| Country | Avg engagement rate |
|---|---|
| 🥇 Brazil | 1.541 |
| Australia | 1.324 |
| France | 1.146 |
| UAE | 1.112 |
| Canada | 0.917 |
| UK | 0.851 |
| Japan | 0.770 |
| Germany | 0.759 |
| India | 0.655 |
| USA | 0.577 |

India has the most posts (535) but ranks second to last on engagement.

| Age group | Avg engagement rate |
|---|---|
| 🥇 46-55 | 1.414 |
| 18-25 | 1.060 |
| <18 | 0.867 |
| 26-35 | 0.865 |
| 36-45 | 0.861 |
| 56-65 | 0.709 |

### Account, device and sentiment
| Factor | Finding |
|---|---|
| **Verification** | Verified accounts average 1.054 vs 0.955 for others |
| **Device** | Mobile users watch longest (4,088 s) vs tablet (3,980 s) and desktop (3,975 s), a small gap |
| **Sentiment** | Positive posts are the most common (2,513) yet have the **lowest** average engagement (0.920); negative posts score highest (1.038) |

### Correlations
- **Impressions and engagement rate: −0.23.** This is the only notable relationship: engagement rate is a ratio, so posts with very large reach have lower rates.
- Likes and engagement rate: +0.09 (weak).
- Every other pair, including hashtag count, follower count, watch time and age, is close to zero.

### 🎯 Takeaways
1. **Food and tech content, and video posts, deliver the highest average engagement.**
2. **Brazil and Australia are the most engaged markets;** India and the USA are the least, despite high post volume.
3. **More reach does not mean a higher rate:** engagement rate falls as impressions rise.
4. **Hashtag count and follower count show no relationship with engagement** in this data.
5. **Positive sentiment does not guarantee engagement;** negative and neutral posts perform at least as well.

---

## 🚀 How to Run

**Option 1: Google Colab.** Click the *Open in Colab* badge at the top.

**Option 2: Locally**

```bash
# 1. Clone the repository
git clone https://github.com/adnanfzahmed-gif/Social-Media-Engagement-Analytics-Using-Python.git
cd Social-Media-Engagement-Analytics-Using-Python

# 2. Install the dependencies
pip install pandas numpy matplotlib seaborn plotly jupyter

# 3. Open the notebook (an internet connection is needed to load the dataset)
jupyter notebook
```

---

## ⚠️ Known Limitations

- **Cell order.** The age-group bar chart (cell 2) sits before the cells that import `matplotlib` and `seaborn` and create `age_group`, so running the notebook from the top fails there. Move that cell after the age-group step, or run *Restart and Run All* after reordering.
- **Posting hour carries no information.** `posted_at` holds dates only, so every `post_hour` is 0 and "the best hour for impressions" cannot be answered from this data. Remove that analysis or note it as not available.
- **Date format.** `posted_at` is day-first (`17-12-2022`); the notebook parses it without `dayfirst=True`, which triggers a warning and could misread dates such as 03-04-2023. Use `pd.to_datetime(df["posted_at"], dayfirst=True)`.
- **Averages of a skewed rate.** Using medians (or a log scale) would give a more reliable ranking than means.
- **Imputed values.** About 3% of rows in six columns were filled with the median or mode.
- **Duplicate cells.** Two cells repeat the same category ranking, and the notebook has an empty cell.
- **File name.** The notebook name contains curly quote characters, which can cause problems in some tools. Consider renaming it to `Social_Media_Engagement_Analytics.ipynb` (and updating the Colab link).

---

## 🔮 Future Improvements

- Add posting time of day to the data so that timing analysis is possible
- Use medians and statistical tests to confirm differences between groups
- Build a predictive model for engagement rate
- Analyse hashtags individually (for example, which hashtags appear in top-performing posts)

---

## 👤 Author

**Adnan Ahmed**
GitHub: [@adnanfzahmed-gif](https://github.com/adnanfzahmed-gif)

---

⭐ If you found this useful, consider starring the repo.

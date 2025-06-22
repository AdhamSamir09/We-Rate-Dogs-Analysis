
# 🐶 WeRateDogs Twitter Data Wrangling and Analysis

## 📌 Project Overview

This impressive project, created by a **16-year-old data enthusiast**, wrangles, cleans, and analyzes data from the **WeRateDogs** Twitter account to uncover insights about dog ratings, engagement, and breed popularity.

Using **Python** and **Jupyter Notebooks**, the project focuses on original tweets with images, extracting meaningful patterns from **three datasets**. Great work for a young coder tackling real-world data!

---

## 📂 Data Sources

- **Twitter Archive** (`twitter_archive_enhanced.csv`):  
  Contains tweet details like `tweet_id`, `text`, `rating_numerator`, `rating_denominator`, and dog stages (`doggo`, `floofer`, `pupper`, `puppo`).

- **Image Predictions** (`image_predictions.tsv`):  
  Provides breed predictions for tweet images, including `tweet_id`, `jpg_url`, `p1` (top prediction), `p1_conf` (confidence), and `p1_dog` (whether prediction is a dog).

- **Tweet JSON** (`tweet_json.txt`):  
  Includes metrics like `retweet_count` and `favorite_count`, downloaded as a fallback due to Twitter API access limitations.

---

## 🔍 Methodology

### 🗃️ Data Gathering
- **Twitter Archive**: Loaded into a pandas DataFrame.
- **Image Predictions**: Downloaded using the `requests` library.
- **Tweet JSON**: Retrieved via a URL, with selective column retention (`retweet_count`, `favorite_count`).

### 🧪 Data Assessment
Identified **8 quality issues** and **2 tidiness issues** using both visual inspection and programmatic checks:

#### 🧹 Quality Issues
1. Retweets and replies in the archive  
2. Missing images for some tweets  
3. Incorrect data types (e.g., `tweet_id` as integer)  
4. Invalid dog names (e.g., "None", "a")  
5. Non-dog predictions in image data  
6. Inconsistent rating denominators  
7. Missing dog stage classifications  
8. Inconsistent breed name capitalization  

#### 🪢 Tidiness Issues
1. Multiple dog stage columns (`doggo`, `floofer`, `pupper`, `puppo`)  
2. Separated datasets requiring merging  

### 🧼 Data Cleaning
(*Inferred from context*)
- Removed retweets and replies  
- Filtered tweets with images  
- Standardized data types and dog names  
- Combined dog stages into one `category` column  
- Merged datasets into a `master_dataset` using `tweet_id`  

---

## 📊 Analysis & Visualization

**📄 Insights Report:** [`Insights_report.html`](./Insights_report.html)

### 🐾 Insight #1
Analyzed monthly averages of `favorite_count` and `retweet_count` using bar plots.  
**Result:** **June** is the top month for engagement.

### 🐾 Insight #2
Compared dog stages using pie charts.  
**Result:** **"Puppo"** (puppies) had the highest engagement.

### 🐾 Insight #3
Calculated `rating_percentage` (`numerator / denominator * 100`) and plotted the top 10 breeds (excluding non-dogs and "puppo") using a horizontal bar chart.  
**Result:** **Clumber** breed has the highest average rating.

---

## 🛠️ Tools & Libraries
- `pandas`, `numpy`, `requests`, `matplotlib`, `tweepy`, `json`, `bs4`
- `nbconvert` for generating HTML report

---

## 🔑 Key Findings

| Metric                     | Result                             |
|---------------------------|-------------------------------------|
| **Best Month for Engagement** | June (~15,981 favorites & ~4,972 retweets) |
| **Most Popular Category**     | Puppo (~22,716 favorites & ~7,125 retweets) |
| **Top-Rated Breed**          | Clumber (270% average rating)     |

---

## 🌟 Strengths
- Creative and clear visualizations  
- Smart workaround for Twitter API limitations  
- Logical structure and great problem-solving  
- Fun, engaging use of a real-world dataset  

---

## ⚠️ Limitations
- Cleaning steps not fully documented  
- Small sample size for rare breeds (e.g., Clumber)  
- No error bars or sample sizes in plots  
- Minimal error handling during data fetching  

---

## ✅ Recommendations
- **Document Cleaning**: Add comments/markdown for steps like retweet removal  
- **Validate Insights**: Show sample sizes and monthly tweet counts  
- **Improve Visualizations**: Add error bars and more chart types  
- **Enhance Robustness**: Use retry logic and handle edge cases  

---

## 📄 License

This project is for educational purposes using data provided by **Udacity**.  
Refer to the original data sources for licensing details.

---

## 🙌 Acknowledgments

Kudos to the 16-year-old creator for tackling this complex dataset with enthusiasm and skill! This project showcases a promising start in data science.


# 🐶 WeRateDogs Twitter Data Wrangling and Analysis

## 📌 Project Overview

This project was developed as part of the **Level 3 Data Science & AI** course in the **Digital Egypt Cubs Initiative (DECI)**, organized by the **Ministry of Communication and Telecommunications**.

In this analysis, I gathered, wrangled, and examined data from three sources related to the Twitter account [**@dog_rates**](https://twitter.com/dog_rates) — a popular page known for rating dogs in funny posts.

Using **Python** and **Jupyter Notebooks**, I focused on original tweets that included images to extract valuable insights about **dog ratings**, **user engagement**, and **breed popularity**.

---

## 📦 Files in This Repository

- **`wrangle_act.ipynb`** – The main notebook where data gathering, cleaning, and wrangling are performed  
- **`Insights_report.html`** – Exported HTML version of the final insights for easy viewing without running code  
- **`twitter_archive_enhanced.csv`** – Dataset containing basic tweet data from @dog_rates  
- **`image_predictions.tsv`** – File containing image classification results for each tweet image  
- **`tweet_json.txt`** – Extracted tweet metadata including retweet and favorite counts
- **`master_dataset.csv`** – File containing merged data of the 3 cleaned datasets
- **`wrangle_report.html`** – Exported HTML version of the wrangling process for easy viewing without running code
  
---

## 📂 Data Sources

- **Twitter Archive** (`twitter_archive_enhanced.csv`):  
  Contains tweet details

- **Image Predictions** (`image_predictions.tsv`):  
  Provides breed predictions for tweet images

- **Tweet JSON** (`tweet_json.txt`):  
  Includes metrics
  
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
- Removed retweets and replies  
- Filtered tweets with images  
- Standardized data types and dog names  
- Combined dog stages into one `category` column  
- Merged datasets into a `master_dataset` using `tweet_id`  

---

## 📊 Analysis & Visualization

### 🐾 Insight #1
Analyzed monthly averages of `favorite_count` and `retweet_count` using bar plots.  
**Result:** **June** is the top month for engagement.

### 🐾 Insight #2
Compared dog stages using pie charts.  
**Result:** **"Puppo"** (puppies) had the highest engagement.

### 🐾 Insight #3
Calculated average rating for every dog breed and plotted the top 10 breeds (excluding non-dogs and "puppo") using a horizontal bar chart.  
**Result:** **Clumber** breed has the highest average rating.

---

## 🔑 Key Findings

| Metric                     | Result                             |
|---------------------------|-------------------------------------|
| **Best Month for Engagement** | June (~15,981 favorites & ~4,972 retweets) |
| **Most Popular Category**     | Puppo (~22,716 favorites & ~7,125 retweets) |
| **Top-Rated Breed**          | Clumber (270% average rating)     |

---
## 🛠️ Tools & Libraries
- `pandas`, `numpy`, `requests`, `matplotlib`, `tweepy`, `json`, `bs4`
- `nbconvert` for generating HTML report




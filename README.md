# 📊 Amazon Fashion – 1-Star Review Sentiment Analysis (SQL + Python + Power BI)

## 🔍 Project Overview

This project analyses **1-star reviews** from Amazon Fashion to identify key customer complaints and dissatisfaction trends. The project combines SQL for data filtering, Python for sentiment labelling, and Power BI for dashboard visualization.

## 🎯 Objective

To uncover root causes of negative customer feedback on Amazon Fashion through data cleaning, feature engineering, and insightful visualization.

## 📁 Dataset

- Source: Kaggle – Amazon Fashion Review Dataset  
- Focus: Only 1-star rated reviews  
- Important columns: `rating`, `reviewText`, `reviewDate`, `verified_purchase`, `sentiment`

---

## 🔧 Tools Used

- **SQL Workbench** – for filtering 1-star reviews, extracting date parts, categorising verified purchases  
- **Python** – for keyword-based sentiment labelling  
- **Excel** – for minor cleaning and export  
- **Power BI** – to create interactive dashboards

---

## 🧮 SQL Operations

- Filtered reviews where `rating = 1`  
- Extracted `YEAR(reviewDate)` and `MONTH(reviewDate)`  
- Categorised `verified_purchase` as ‘Yes’ or ‘No’  

---

## 🐍 Python Sentiment Labelling

- Added a `sentiment` column based on keywords:  
```python
def label_sentiment(review):
    negative_keywords = ['bad', 'fake', 'broken', 'cheap', 'not original', 'small', 'poor']
    if any(word in review.lower() for word in negative_keywords):
        return 'Negative'
    elif review.strip() == '' or review is None:
        return 'Neutral'
    else:
        return 'Neutral'

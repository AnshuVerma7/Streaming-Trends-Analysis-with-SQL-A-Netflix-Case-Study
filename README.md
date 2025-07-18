# 🎬 Netflix Movies and TV Shows Data Analysis using SQL

## 📊 Overview

This project focuses on performing end-to-end SQL analysis of Netflix's movies and TV shows dataset. It explores key business questions to uncover insights into content distribution, audience targeting, regional availability, and content categorization.

---

## 🎯 Objectives

- Compare the number of movies and TV shows on Netflix.
- Identify the most common ratings and genres.
- Analyze content distribution by country, year, and duration.
- Explore keyword-based content classification (e.g., violence).
- Extract insights about directors, actors, and release trends.

---

## 📁 Dataset

- **Source**: [Kaggle - Netflix Movies and TV Shows Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows?resource=download)

### Database Schema (PostgreSQL)

```sql
CREATE TABLE netflix (
    show_id      VARCHAR(5),
    type         VARCHAR(10),
    title        VARCHAR(250),
    director     VARCHAR(550),
    casts        VARCHAR(1050),
    country      VARCHAR(550),
    date_added   VARCHAR(55),
    release_year INT,
    rating       VARCHAR(15),
    duration     VARCHAR(15),
    listed_in    VARCHAR(250),
    description  VARCHAR(550)
);
````

---

## 🔍 Key Analysis Queries

### 1. Distribution of Movies vs. TV Shows

```sql
SELECT type, COUNT(*) FROM netflix GROUP BY 1;
```

### 2. Most Frequent Rating per Content Type

```sql
-- Uses window functions to rank ratings by frequency
```

### 3. Movies Released in 2020

```sql
SELECT * FROM netflix WHERE release_year = 2020;
```

### 4. Top 5 Countries by Total Content

```sql
-- Unnest and count country-wise content
```

### 5. Longest Movie by Duration

```sql
-- Order by duration field after conversion
```

### 6. Content Added in Last 5 Years

```sql
-- Use TO_DATE and INTERVAL logic
```

### 7. Content by Specific Director (e.g., 'Rajiv Chilaka')

```sql
-- Use UNNEST for multi-director rows
```

### 8. TV Shows with More Than 5 Seasons

```sql
-- Filter using SPLIT_PART on duration
```

### 9. Content Count by Genre

```sql
-- Use UNNEST and group by genre
```

### 10. India's Top Years for Content Release

```sql
-- Calculate average release percentage per year
```

### 11. Documentaries Only

```sql
SELECT * FROM netflix WHERE listed_in LIKE '%Documentaries%';
```

### 12. Content Without a Director

```sql
SELECT * FROM netflix WHERE director IS NULL;
```

### 13. Movies Featuring 'Salman Khan' in Last 10 Years

```sql
-- Filter cast and release year
```

### 14. Top 10 Actors in Indian Productions

```sql
-- Use UNNEST on cast field for 'India' country
```

### 15. Categorize Content by Keywords ('kill' or 'violence')

```sql
-- Classify as 'Bad' or 'Good' based on description
```

---

## 📈 Key Insights

* Netflix offers more movies than TV shows, with varied genres and content ratings.
* U.S. leads in total content, while India has strong yearly contributions.
* Some actors and directors appear consistently across top-performing content.
* Descriptive keyword analysis highlights content tone and theme categorization.

---

## ✅ Conclusion

This project demonstrates the application of **advanced SQL** techniques—including subqueries, window functions, string operations, and conditional logic—to solve real-world data analysis problems and generate actionable insights from entertainment data.

It is ideal for showcasing SQL proficiency in data analytics portfolios and job interviews.

---

## 📌 Tags

`#SQL` `#NetflixDataAnalysis` `#PortfolioProject` `#DataAnalytics` `#PostgreSQL`

# Netflix Movies and TV Shows Data Analysis using SQL

![Netflix Logo](https://github.com/BiswaRanjan8596/netflix_sql_project/blob/main/logo.png)


# 🎬 Netflix SQL Data Analysis Project

Welcome to my first hands-on SQL project! In this project, I used **PostgreSQL** to analyze the Netflix dataset and uncover key trends across genres, countries, content types, and release years.

---

## 📌 Project Overview

The goal of this project was to use raw SQL queries to explore and analyze the Netflix catalog data, including:

- Movies vs TV Shows by year
- Country-wise content breakdown
- Genre trends using `UNNEST` and `STRING_TO_ARRAY`
- Year-wise content release patterns (focused on India)
- Rating and duration distributions

---

## 🧠 Key Skills Practiced

- SQL (PostgreSQL)
- Data Cleaning & Transformation
- Aggregation & Grouping
- Date Parsing with `TO_DATE`, `EXTRACT`
- String Operations with `STRING_TO_ARRAY`, `TRIM`, `UNNEST`
- Subqueries and Nested Logic

---

## 🛠️ Tools & Technologies

- **PostgreSQL**
- **pgAdmin / VS Code**
- **Excel** (for initial data formatting)
- Dataset Source: [Kaggle - Netflix Titles](https://www.kaggle.com/datasets/shivamb/netflix-shows)

---

## 📊 Sample Queries

### 🎭 Top Genres (using UNNEST)
```sql
SELECT 
  TRIM(UNNEST(STRING_TO_ARRAY(listed_in, ','))) AS genre,
  COUNT(show_id) AS total
FROM netflix
GROUP BY genre
ORDER BY total DESC
LIMIT 10;
🇮🇳 Content Released in India by Year
sql
Copy
Edit
SELECT 
  EXTRACT(YEAR FROM TO_DATE(date_added, 'Month DD, YYYY')) AS year,
  COUNT(*) AS content_count
FROM netflix
WHERE country = 'India'
  AND date_added IS NOT NULL
GROUP BY year
ORDER BY content_count DESC;
📈 Key Insights
📅 Netflix content has grown significantly since 2016.

🎭 Most popular genres include Dramas, Documentaries, and International Movies.

🌏 India is among the top countries with consistent yearly releases.

🕒 Most content has an average duration of 84–143 minutes.

📁 Project Structure
File	Description
netflix_queries.sql	Main SQL queries used for analysis
notebook.md	Notes, observations, and insights
README.md	Project summary and documentation
logo.png	Custom logo for project branding (optional)
📸 Project Screenshots
Coming soon — Tableau dashboard visualizations! (Optional: insert image links here)

🧩 Challenges Faced
Inconsistent date formats in date_added

Parsing multiple genres stored in a single string field

Handling NULL values for missing data

📌 What's Next?
Visualizing these results in Tableau

Building an interactive dashboard with filters

Applying this analysis to other datasets like IMDb or Spotify


## 👨‍💻 Author

**Biswa Ranjan Swain**  
👋 I'm **Biswa Ranjan Swain**, a passionate data analyst with hands-on experience in SQL, Power BI, Tableau, and Python.
📫 [Connect on LinkedIn](https://www.linkedin.com/in/biswa-ranjan-swain-1b72a7158)
🎓 [Deloitte Data Analytics Certification (Forage)](https://forage-uploads-prod.s3.amazonaws.com/completion-certificates/9PBTqmSxAf6zZTseP/io9DzWKe3PTsiS6GG_9PBTqmSxAf6zZTseP_KDoEgTn4rvPhWTM5F_1744043250362_completion_certificate.pdf)



## Findings and Conclusion

- **Content Distribution:** The dataset contains a diverse range of movies and TV shows with varying ratings and genres.
- **Common Ratings:** Insights into the most common ratings provide an understanding of the content's target audience.
- **Geographical Insights:** The top countries and the average content releases by India highlight regional content distribution.
- **Content Categorization:** Categorizing content based on specific keywords helps in understanding the nature of content available on Netflix.


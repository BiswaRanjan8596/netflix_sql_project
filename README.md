# Netflix Movies and TV Shows Data Analysis using SQL

![Netflix Logo](https://github.com/BiswaRanjan8596/netflix_sql_project/blob/main/logo.png)


# 🎬 Netflix SQL Data Analysis Project

This project is a SQL-based analysis of the Netflix catalog dataset. The goal is to extract meaningful insights about content trends, genres, countries, and release patterns using PostgreSQL.

---

## 📌 Project Overview

Using SQL, I explored Netflix's content library to uncover:

- 📈 Year-wise trends in Movies vs TV Shows
- 🌍 Country-specific content releases (with a focus on India)
- 🎭 Genre breakdown using `UNNEST` and `STRING_TO_ARRAY`
- 🕒 Duration and rating analysis
- 🧠 Data cleaning with string and date functions

---

## 🛠️ Tools & Technologies

- **PostgreSQL** (SQL)
- **VS Code / pgAdmin** (for running queries)
- **Excel** (for initial data formatting)
- Dataset: Cleaned version of Netflix titles from [Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)

---

## 📂 Files

| File | Description |
|------|-------------|
| `netflix.sql` | All SQL queries used for the project |
| `notebook.md` | Notes and insights from the exploration |
| `README.md` | Project summary and documentation |

---

## 📊 Sample Queries

```sql
-- Top 5 genres by content volume
SELECT 
  TRIM(UNNEST(STRING_TO_ARRAY(listed_in, ','))) AS genre,
  COUNT(show_id) AS total
FROM netflix
GROUP BY genre
ORDER BY total DESC
LIMIT 5;
sql
Copy
Edit
-- Year-wise content release in India
SELECT 
  EXTRACT(YEAR FROM TO_DATE(date_added, 'Month DD, YYYY')) AS year,
  COUNT(*) AS content_count
FROM netflix
WHERE country = 'India'
GROUP BY year
ORDER BY content_count DESC;
📈 Key Insights
India has seen a surge in Netflix content releases since 2017

TV Shows make up ~30% of total content, with steady growth year over year

Top genres include Documentaries, International Movies, and Dramas

🎯 What's Next?
📊 Visualizing these insights using Tableau

Adding more complex logic using window functions

Automating data pipelines using SQL scripts + Python

🔗 Connect with Me
👤 Biswa Ranjan Swain
📫 [Linkedin](https://www.linkedin.com/in/biswa-ranjan-swain-1b72a7158?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BOCxA6IVcQuWopca46qyK%2Bw%3D%3D)
📁 Project on LinkedIn Post (link after you post it)


## Findings and Conclusion

- **Content Distribution:** The dataset contains a diverse range of movies and TV shows with varying ratings and genres.
- **Common Ratings:** Insights into the most common ratings provide an understanding of the content's target audience.
- **Geographical Insights:** The top countries and the average content releases by India highlight regional content distribution.
- **Content Categorization:** Categorizing content based on specific keywords helps in understanding the nature of content available on Netflix.


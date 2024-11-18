# MySql --Movies report analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset Information](#dataset-information)
- [Objectives](#objectives)
- [SQL Queries and Analysis](#sql-queries-and-analysis)
  - [1. Top 10 Movies with a High Budget](#1-top-10-movies-with-a-high-budget)
  - [2. Top 10 Highest-Grossing Movies](#2-top-10-highest-grossing-movies)
  - [3. Total Number of Movies in the Dataset](#3-total-number-of-movies-in-the-dataset)
  - [4. Average Runtime of Movies](#4-average-runtime-of-movies)
  - [5. Movies Released Before 2016](#5-movies-released-before-2016)
  - [6. Movies with High Ratings](#6-movies-with-high-ratings)
  - [7. Count of English Language Movies](#7-count-of-english-language-movies)
  - [8. Top 5 Most Popular Movies](#8-top-5-most-popular-movies)
  - [9. Movies by 'Walt Disney Pictures'](#9-movies-by-walt-disney-pictures)
  - [10. Movies with Runtime Over 150 Minutes](#10-movies-with-runtime-over-150-minutes)
  - [11. Total Revenue from All Movies](#11-total-revenue-from-all-movies)
  - [12. Adventure Genre Movies](#12-adventure-genre-movies)
  - [13. Movie with the Highest Vote Count](#13-movie-with-the-highest-vote-count)
  - [14. Movies with No Revenue](#14-movies-with-no-revenue)
  

## Project Overview
This project involves analyzing a dataset of movies using **MySQL** to extract meaningful insights about film performance, financial metrics, and various other attributes. The focus is on leveraging **SQL** to manipulate and query the dataset, uncovering trends related to budget, revenue, popularity, and more.

## Dataset Information
- The dataset used in this project is **tmdb_5000_movies**, which includes information on movies such as titles, budgets, revenues, runtimes, ratings, and genres.
- The analysis was performed using **MySQL**, utilizing various SQL queries to derive insights from the data.

## Objectives
- To identify top-performing movies based on budget, revenue, and ratings.
- To analyze movie trends such as popularity, genre distribution, and runtime.
- To provide data-driven insights for stakeholders in the film industry.

## SQL Queries and Analysis

### 1. Top 10 Movies with a High Budget
sql
SELECT title, budget 
FROM tmdb_5000_movies 
WHERE budget > 100000000 
ORDER BY budget DESC 
LIMIT 10;
## 2. Top 10 Highest-Grossing Movies
sql
Copy code
SELECT title, revenue 
FROM tmdb_5000_movies 
ORDER BY revenue DESC 
LIMIT 10;
## 3. Total Number of Movies in the Dataset
sql
Copy code
SELECT COUNT(*) 
FROM tmdb_5000_movies;
## 4. Average Runtime of Movies
sql
Copy code
SELECT AVG(runtime) AS avg_runtime 
FROM tmdb_5000_movies;
## 5. Movies Released Before 2016
sql
Copy code
SELECT title, release_date 
FROM tmdb_5000_movies 
WHERE release_date < '2016-01-01' 
LIMIT 10;
## 6. Movies with High Ratings
sql
Copy code
SELECT title, vote_average 
FROM tmdb_5000_movies 
WHERE vote_average > 8;
## 7. Count of English Language Movies
sql
Copy code
SELECT COUNT(*) 
FROM tmdb_5000_movies 
WHERE original_language = 'en';
## 8. Top 5 Most Popular Movies
sql
Copy code
SELECT title, popularity 
FROM tmdb_5000_movies 
ORDER BY popularity DESC 
LIMIT 5;
## 9. Movies by 'Walt Disney Pictures'
sql
Copy code
SELECT title 
FROM tmdb_5000_movies 
WHERE production_companies LIKE '%Walt Disney Pictures%';
## 10. Movies with Runtime Over 150 Minutes
sql
Copy code
SELECT title, runtime 
FROM tmdb_5000_movies 
WHERE runtime > 150;
## 11. Total Revenue from All Movies
sql
Copy code
SELECT SUM(revenue) AS total_revenue 
FROM tmdb_5000_movies;
## 12. Adventure Genre Movies
sql
Copy code
SELECT title 
FROM tmdb_5000_movies 
WHERE genres LIKE '%Adventure%' 
LIMIT 10;
## 13. Movie with the Highest Vote Count
sql
Copy code
SELECT title, vote_count 
FROM tmdb_5000_movies 
ORDER BY vote_count DESC 
LIMIT 1;
## 14. Movies with No Revenue
sql
Copy code
SELECT title 
FROM tmdb_5000_movies 
WHERE revenue = 0;

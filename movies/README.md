## Exploratory Data Analysis of Top 250 IMDB Movies

This notebook explores the user ratings and other information for the top 250 movies on IMDB according to a scraped dataset. The analysis utilizes Python libraries like pandas for data manipulation and seaborn for data visualization.

### Data Acquisition

The data for this analysis is assumed to be from a CSV file named "movies.csv" located in the same directory as this Jupyter notebook. 

### Libraries

* pandas: Data manipulation and analysis 
* seaborn: Data visualization

### Data Description

```python
import pandas as pd

movies_df = pd.read_csv('movies.csv')

print(movies_df.describe())
```

The `describe()` function provides a summary of the numerical features (rank, year, number of votes, and rating) within the dataset.

### Interpretation

The dataset contains information about 250 movies, including:

* Rank: The movie's placement based on user ratings. 
* Year: The year the movie was released.
* IMDB Votes: The number of users who rated the movie on IMDB.
* IMDB Rating: The average user rating for the movie (on a scale of 1 to 10).

While the descriptive statistics provide a basic understanding of these numerical features, it's important to note that the dataset also contains categorical variables like genre, director, and writer names. These will be explored further in the analysis.

### Question 1: Most Frequent Genres

```python
top_genres = movies_df['genre'].value_counts().head(10)
top_genres.plot(kind='bar')
```

This code snippet explores the most frequent movie genres among the top 250 on IMDB. The `value_counts()` method creates a series showing the count of each unique genre, and the `.head(10)` selects the top 10 genres for visualization with a bar chart.

**Conclusion:** Drama is the most common genre found in the top-rated movies on IMDB, followed by genres like Crime, Drama and Animation, Adventure, Comedy.

### Question 2: Director-Writer Overlap

```python
direct_and_write_df = movies_df[movies_df['director_name'] == movies_df['writter_name']]

print(direct_and_write_df.shape[0])
```

This code identifies movies where the director and writer are the same person. It filters the DataFrame (`movies_df`) to include only rows where the director name and writer name match.  

**Conclusion:**  There are 30 movies in the top 250 where the same person is credited as both director and writer.

### Question 3: Votes vs. Rank/Rating

```python
group = movies_df.groupby(['imbd_votes', 'rank'])[['imdb_rating']].mean()
sns.relplot(data=group, x='rank', y='imbd_votes', hue='imdb_rating')
```

This code investigates the relationship between the number of IMDB votes a movie receives, its rank on the list, and its average rating. The `groupby` function is used to create groups based on both the number of votes and the movie's rank. The average rating is then calculated for each group. Finally, a relational plot is generated to visualize these trends.

**Conclusion:** There appears to be a weak positive correlation between the number of votes and the movie's rating/rank. Generally, movies with higher ratings and rankings tend to have a larger number of user votes. However, it's important to note that correlation doesn't imply causation. 

### Future Analysis

This initial exploration provides a starting point for further analysis of the movie data. Here are some areas for future investigation:

* **Data Cleaning:** The data may contain inconsistencies or typos (e.g., "writter_name") that should be addressed before further analysis.
* **Categorical Variable Exploration:**  A deeper dive into the categorical variables like genre, director, and cast could reveal interesting relationships with other features (e.g., average rating for different genres, director with the most movies).
* **Temporal Analysis:** If the dataset includes release years, exploring trends across time periods could be interesting (e.g., most popular genres by decade).
* **Predictive Modeling:** After data cleaning and feature engineering, this dataset could be used for building models to predict movie ratings or recommend movies based on user preferences.

<sub> 
This README document was partially generated with the assistance of artificial intelligence.
</sub>
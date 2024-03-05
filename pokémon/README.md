# Fun-EDA

## Exploratory Data Analysis of Pokemon Stats (Gen I-VI)

This document outlines the initial exploration of a dataset containing information on the base stats of various Pokemon across the first six generations of the video game series. 

### Data Acquisition

The dataset, ["Complete Pokemon Dataset (Gen I-VI)"](./Pokedex_Cleaned.csv), was retrieved from [https://www.kaggle.com/rounakbanik/pokemon/activity](https://www.kaggle.com/rounakbanik/pokemon/activity).

### Libraries

This analysis utilizes the following Python libraries:

* pandas: Data manipulation and analysis 
* seaborn: Data visualization

### Data Description

```python
import pandas as pd

pokemon_df = pd.read_csv('Pokedex_Cleaned.csv')

print(pokemon_df.describe())
```

The `describe()` function provides a statistical summary of the numerical features within the dataset. This includes the mean, standard deviation, minimum, and maximum values for each stat.

### Interpretation

The dataset contains 1173 rows (Pokemon) and 12 columns of data. Here's a breakdown of some key observations from the descriptive statistics:

* **Total** (sum of base stats): The average Pokemon has a total stat value of approximately 440, with a significant spread between the weakest (175) and strongest (1125) Pokemon.
* **HP** (health points): HP ranges from a minimum of 1 to a maximum of 255, with an average of around 71.
* **Attack, Defense, Sp. Atk, Sp. Def, Speed**: These stats all follow a similar pattern, with average values in the low-to-mid 70s and a standard deviation in the 30s.

It's important to note that this initial exploration focuses on numerical data. Future analysis should incorporate the categorical variables, such as "Primary Type" and "Secondary Type", for a more comprehensive understanding.

### Question 1: Most Popular Primary Type

```python
pokemon_df['Primary Type'].value_counts().plot(kind='bar')
```

The code snippet above generates a bar chart to visualize the frequency of each primary type.

**Conclusion:** Water is the most frequent primary type, with nearly 150 Pokemon categorized as such.

### Question 2: Most Frequent Type Combinations

```python
pd.crosstab(pokemon_df['Primary Type'], pokemon_df['Secondary Type'])
```

A crosstabulation table is created to explore how often each combination of primary and secondary types appears within the dataset.

**Conclusion:** The most frequent combination is Normal/Flying, followed by Ground/Flying and Poison/Flying.

### Question 3: Primary Type vs. Speed/HP

```python
pokemon_df.groupby('Primary Type')[['Speed', 'HP']].describe()
```

This code examines how HP and Speed are distributed across the different primary types. Descriptive statistics are generated for each type grouping.

**Conclusion:** There isn't a clear relationship between a Pokemon's primary type and its HP or Speed. It's unlikely to predict a Pokemon's HP or Speed based solely on its primary type. 

### Future Analysis

While this initial exploration provided a basic understanding of the data, there's room for further analysis:

* **Data Cleaning:** Inconsistencies within the data, such as incorrect primary types (rows 803-804, 918-919), should be addressed.
* **Visualization:** Additional visualizations can be created to explore relationships between different features. 
* **Categorical Variables:** A deeper dive into the categorical variables, such as type combinations and their impact on other stats, is recommended.

This refined data can then be used for more advanced statistical modeling and data mining techniques.

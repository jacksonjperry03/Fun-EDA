## [Fake News Classification and Text Similarity](./fake_news.ipynb)

This Jupyter notebook explores a dataset of news articles labeled as real or fake. It aims to answer two questions:

**1. Is the text or title of an article more predictive of whether it's real or fake news?**
**2. Are titles of real or fake news articles more similar to one another?**

The dataset, ["fake_or_real_news"](./fake_or_real_news.csv), was retrieved from [https://github.com/lutzhamel/fake-news/blob/master/data/fake_or_real_news.csv](https://github.com/lutzhamel/fake-news/blob/master/data/fake_or_real_news.csv).

### Methodology

The notebook follows these steps for each question:

1. **Import necessary libraries:** Pandas for data manipulation, scikit-learn libraries for classification and text analysis.
2. **Load the data:** Load the CSV file containing the news articles with labels.
3. **Preprocess the data:** Separate the data into features (text or title) and target variable (label). Convert text data into numerical features using CountVectorizer.
4. **Train a classification model:** Train a Multinomial Naive Bayes model to classify news based on text or title.
5. **Evaluate the model:** Calculate the accuracy score on test data to determine which feature (text or title) leads to better classification.
6. **(For question 2 only) Calculate text similarity:** Separate the data into real and fake news DataFrames. Calculate the mean Euclidean distance between titles within each DataFrame. Compare the distances to see which category has more similar titles.

### Results

**Question 1:** The text classifier achieved a higher accuracy score compared to the title classifier. This suggests that **the text of a news article is more predictive than the title in determining whether it's real or fake.**

**Question 2:** The mean Euclidean distance between titles in the real news DataFrame was lower compared to the fake news DataFrame. This indicates that **titles from real news articles are more similar to one another** compared to titles from fake news articles.

### Conclusion

This exploratory analysis suggests that the content of a news article is more informative for identifying real or fake news compared to the title. Additionally, titles from real news articles tend to share more similarities than titles from fake news articles. 

This is a basic analysis, and further exploration might involve more sophisticated techniques and a larger dataset.

<sub> 
This README document was partially generated with the assistance of artificial intelligence.
</sub>


### Features in the Dataset

Here are the features that were present in the original dataset:

1. **Book ID:** A unique identifier for each book.
2. **Title:** Title of the book
3. **Description:** A brief description of the article's content.
4. **publishedDate:** The date/year/month when the book was published.
5. **Authors:** The authors of the book
6. **Publisher:** The publisher of the book
7. **Impact:** Target Variable Impact Score for the book

### Shortlisting Features Process

We selected a set of features from the given dataset to create Input Space for our Model

1. **Book ID:** This feature is a unique identifier and does not provide any valuable information for classification, so it was excluded from the feature selection process.

2. **Title and Description:** While these text features contain valuable information, they can be challenging to work with directly. To make them usable, you decided to convert them into vectors that the model could understand

3. **Published Date:** Published Data is an important feature but needs some processing due to inconsistency

4. **Authors and Categories:** Authors and categories are crucial for classifying articles as they give information about the themes of the book and who wrote them which could be a strong signal to find the book's impact score

5. **Publisher:** The publisher information is crucial so we decided to keep the feature.

### Feature Engineering

Now, let's discuss how we engineered these features:

1. **Preprocessing Published Dates:** We converted the 'publishedDate'  to another feature 'published_year' since there were inconsistent in this feature as we did not have dates and month information for all articles so we decided to keep it at a year level

2. **Vectorization of Authors and Categories:** Authors and Categories were a string of type list so we first converted them to list. We decided to convert them to one hot vector but the  vectors would have become very huge and sparse so we decided to restrict ourselves to the top 100 authors and categories

3. **Transformation of Publisher:** To work with the categorical 'publisher' feature, you performed ordinal encoding. Each publisher was assigned a unique numeric value.

4. **TF-IDF Transformation for Title and Description:** We applied TF-IDF (Term Frequency-Inverse Document Frequency) vectorization to the 'Title' and 'description' features as we could not use text features in our model directly. We performed some basic text processing like tokenization and stop word removal then  TF-IDF transformed these text data into numerical vectors, where each word's importance was considered with the entire dataset. We decided to use hashing and limit the vectors to 200 dim sizes each.

By implementing these feature engineering techniques, we prepared the dataset for building our model.

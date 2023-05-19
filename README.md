# Problem: Which anime should I watch? 



## Best Model
Decision Tree (sklearn) with Cross-Validated Depth (5 iterations)



## Conclusion
### For new anime (<5 years), Manga score is a good predictor of a good anime (Score >7.5)
- 0.6690 classification accuracy in a cross-validated decision tree with depth 5

### For older anime (>5 years), Favorites is an excellent predictor of a good anime (Score >7.5)
- 0.8106 classification accuracy in a cross-validated decision tree with depth 1
- Older anime are likely to have more Favorites, and any anime with Favorites >25000 has Score >7.5



## What We Learnt
### Data Cleaning
- Transforming the numerical variable Score into classification variables to produce more accurate decision trees
- Transforming one variable two different ways can produce very different results, e.g Season and Age, which are both based on Aired 
- How to use SequenceMatcher from difflib to match animes to their manga sources
- Encoding string data into integers for easier use

### EDA
- Some variables which are difficult to use for prediction cannot be filtered out purely through EDA, e.g. Genres

### Analysis
- Linear and Polynomial Regression could not be used due to low correlation values
- Logistic Regression also failed because both the classification variables for Score had a numerical bias toward a certain class, which led to the model always predicting an anime as that class
- Using Cross Validation to find the best depth for decision trees is a good method, but a regular decision tree may occasionally produce slightly better accuracy as it is more randomized



## Future Considerations
- Ratings from reputable critics and reviewers might produce more accurate predictions
- Expand analysis to include anime based on other sources such as novels and games



## Datasets & References
MAL Top 10000 Anime Details: Main dataset containing a few predictors such as Genre and Source, as well as the initial response variable Score
- https://www.kaggle.com/datasets/stoicstatic/mal-top-10k-anime-details?select=MAL+Anime+Top+10000+Details.csv

manga: Secondary dataset which we used to add the score of source manga
- https://www.kaggle.com/datasets/joshjms/kawaii?select=manga.csv

TV_data: Initial cleaned dataset
- Dropped irrelevant columns
- Combined similar types
- Set reference numbers for convenient classification

TV_data_manga: Final dataset
- Dropped all anime which did not have manga as their source material
- Added a new column to indicate the rating of the source manga for the corresponding anime



## Team Members & Contributions
### Pey Ruo-Yang @PRYtheSheep 
-  Data Cleaning
-  EDA
-  Decision Tree
-  Analysis

### Tiffany Grace Sajoto @itmorgan
- Data Cleaning 
- Data Visualisation
- Presentation Slides
- Video Editing

### Ezra Koh @OSA7JIMI 
- Data Cleaning 
- Polynomial Regression
- Decision Tree
- Repository Organisation

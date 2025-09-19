# Movie Recommendation System

## Introduction
In this project, I built a simple anime recommendation system using user ratings. The idea was to find similar anime based on how users rated them, using collaborative filtering. I worked with a dataset of anime titles and ratings, cleaned it up, created a user-item matrix, and calculated similarity scores. Then, I built a function to suggest similar anime and used visuals like heat maps and bar charts to show the results.  

It’s a basic system, but a good start for understanding how recommendations work.

## Objective
The main goal of this project was to build a basic anime recommendation system using collaborative filtering. The system suggests anime titles to users based on their rating patterns and those of other users.

## Tools & Libraries Used
- **Python** – Main programming language used for the project  
- **Pandas** – Data cleaning, filtering, merging, and reshaping datasets  
- **NumPy** – Handling numerical data and matrix operations  
- **Scikit-learn (sklearn)** – Calculating cosine similarity between anime based on user ratings  
- **SciPy (scipy.sparse)** – Converting user-anime matrix into sparse format for memory and performance efficiency  
- **Seaborn** – Visualizations like heat maps and bar charts for similarity and rating comparisons  
- **Matplotlib** – Plotting graphs and customizing visual elements  
- **Pickle** – Saving the item similarity matrix for future use  

## Process

### 1. Loading the Data
- Loaded two datasets:
  - User ratings (`user_id`, `anime_id`, `rating`)  
  - Anime info (title and overall rating)  

### 2. Exploring the Data (EDA)
- Viewed dataset shape and columns  
- Checked for missing values  
- Looked at unique user and anime IDs  
- Plotted a histogram of ratings (most ratings were high)  
- Removed rows with `rating = -1` (not actual ratings)  
- Identified most-rated anime  
- Sorted and grouped data to explore how many ratings each anime and user had  

### 3. Cleaning the Text (Pre-processing)
- **Filtering Duplicate Ratings**:
  - Sorted dataset by rating to prioritize higher ratings  
  - Removed duplicate user-anime pairs to keep the highest rating per user-anime combination  

### 4. Creating the User-Anime Matrix
- Transformed data into a matrix where:
  - Rows = Users  
  - Columns = Anime titles  
  - Values = Ratings  
- Filled missing values with `0` to represent unwatched/unrated anime  

### 5. Sparse Matrix Conversion
- Converted the matrix into a sparse format for memory and computation efficiency  

### 6. Calculating Similarity
- Calculated cosine similarity between anime titles  
- Generated a similarity matrix to quantify how similar each anime is to others  

### 7. Saving Similarity Matrix
- Stored the similarity matrix for future use without re-computation  

### 8. Anime Recommendation Function
- Created a function to retrieve the top `n` similar anime based on similarity scores  
- Merged results with anime metadata (title and rating) for interpretation  

### 9. Visualizations
- **Heat Map of Top Anime Similarities**: Showed similarities between top-rated anime  
- **Histogram of Ratings**: Displayed distribution of ratings across all anime titles  
- **Bar Chart for Similar Anime**: Showed top 5 most similar anime to a selected anime  

## Conclusion
In this project, I built a basic anime recommendation system using user ratings and cosine similarity. By processing a large dataset, I identified patterns in user preferences and suggested similar anime based on rating behavior.  

Key insights:
- Relied on **item-item collaborative filtering**, not anime content  
- Cleaning the data, such as removing `-1` ratings and handling sparse entries, was crucial  
- **Visual Insights**:
  - **Bar Chart**: For *“Kimi no Na wa”*, top 5 similar anime were shown. *“Shigatsu wa Kimi no Uso”* ranked closest  
  - **Heatmap**: Displayed similarity between top-rated anime (brighter colors = stronger similarity)  
  - **Histogram**: Most users rated anime between 7–10, indicating generous scoring  

This approach gave useful, understandable results and can be further improved with content-based or hybrid recommendation methods.

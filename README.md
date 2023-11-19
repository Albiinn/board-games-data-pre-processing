# board-games-data-pre-processing

## Overview

This Python script performs data preprocessing and feature engineering on a dataset of board games. The dataset is loaded from a CSV file, and various steps are taken to clean and enhance the data for analysis.

## Requirements

- Python 3.x
- pandas library (pip install pandas)
- jupyter library (pip install jupyter)

## Code Structure
- `main.ipynb`: Main Jupyter Notebook for data processing.
- `data/board_games.csv`: Input dataset in CSV format.

## Steps Performed
1. Data Loading:
  - Load the dataset from the CSV file using pandas.

2. Initial Data Exploration:
  - Display the top rows and data types of the dataset.

3. Handling Missing Values:
  - Identify and handle null values in specific columns.
  - Remove unnecessary columns.

4. Feature Engineering:
  - Create a new column 'average_playtime' based on the mean of 'min_playtime' and 'max_playtime'.
  - Remove 'max_playtime' and 'min_playtime' columns.

5. Filtering and Imputing Values:
  - Filter and drop rows where 'average_playtime' is 0.
  - Impute null values in 'image' and 'category' columns.

6. Handling Player Information:
  - Identify and drop rows where both 'min_players' and 'max_players' are 0.
  - Set 'min_players' to 1 where 'min_players' is 0.

7. Discretization:
  - Discretize the 'average_rating' and 'users_rated' columns into categories.

8. Percentage Calculation:
  - Calculate the percentage of total ratings achieved by each game with their respective number of minimum players.

9. Binarization:
  - Binarize the 'average_playtime' column.

## Output
Display information about the processed dataset.

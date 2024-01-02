# board-games-data-pre-processing

## Overview

This Python script performs data preprocessing and feature engineering on a dataset of board games. The dataset is loaded from a CSV file, and various steps are taken to clean and enhance the data for analysis.

## Requirements

- Python 3.x
- pandas library (pip install pandas)
- jupyter library (pip install jupyter)
- sklearn library (pip install scikit-learn)

## Code Structure
- `main.ipynb`: Main Jupyter Notebook for data processing.
- `data/board_games.csv`: Input dataset in CSV format.

## Steps Performed
1. Data Loading:
  - Load the dataset from the CSV file using pandas.

2. Initial Data Exploration:
  - Display the top rows and data types of the dataset.
    
     <img width="1006" alt="Screenshot 2024-01-02 at 10 56 54 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/659d15a2-a61d-4828-95dd-2e6d047efc16">
     <img width="1007" alt="Screenshot 2024-01-02 at 11 08 25 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/39e205b4-c81e-4deb-8e33-cf2a4db86d99">

3. Handling Missing Values:
  - Identify and handle null values in specific columns.
    
    <img width="1006" alt="Screenshot 2024-01-02 at 11 00 50 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/baa6f486-7b0a-421c-805e-a69a368821dd">

  - Remove unnecessary columns.
    
    <img width="1007" alt="Screenshot 2024-01-02 at 11 02 24 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/bac0f2b5-00dd-46b9-931f-6b0e0f6e5fd3">


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

    <img width="1008" alt="Screenshot 2024-01-02 at 11 04 14 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/3ead0287-34a7-4795-a3f6-42c2edca51fe">

8. Percentage Calculation:
  - Calculate the percentage of total ratings achieved by each game with their respective number of minimum players.

    <img width="1008" alt="Screenshot 2024-01-02 at 11 10 14 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/adc47682-9ada-4cab-920c-45796fcdd652">


9. Binarization:
  - Binarize the 'min_age' column. For each game check the recommended minimum age that is required. If the age is less than 18 it is mapping to 1, otherwise to 0.

    <img width="1007" alt="Screenshot 2024-01-02 at 11 10 52 PM" src="https://github.com/Albiinn/board-games-data-pre-processing/assets/56487491/5f794004-74ed-41d2-92f0-8a10959875fa">


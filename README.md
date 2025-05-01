# Real Estate Price Prediction

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Exploratory Data Analysis](#exploratory-data-analysis)
4. [Data Preprocessing](#data-preprocessing)
5. [Modeling](#modeling)
6. [Results](#results)
7. [Technologies Used](#technologies-used)
8. [How to Run](#how-to-run)
9. [Visualizations](#visualizations)
10. [Challenges and Solutions](#challenges-and-solutions)
11. [Future Work](#future-work)

## Introduction
This project analyzes a real estate dataset from [seloger.com](https://www.seloger.com/) to predict property prices using machine learning techniques. The goal is to identify key factors influencing property prices, such as surface area and location, and build accurate predictive models.

## Dataset
The dataset contains 8,899 property listings with 24 features, including:
- `prix`: Property price (target variable)
- `surface`: Surface area in square meters
- `nb_chambres`: Number of bedrooms
- `nb_pieces`: Number of rooms
- `ville`: City or location
- `typedebien`: Property type

## Exploratory Data Analysis
Exploratory data analysis (EDA) revealed:
- A strong positive correlation between `surface` and `prix`.
- Properties in Paris are generally more expensive than those in the banlieue.
- Variables like kitchen type and property type also influence prices.

Visualizations, including scatter plots and box plots, were used to explore these relationships.

## Data Preprocessing
Key preprocessing steps included:
- **Encoding Correction**: Fixed special characters in text fields (e.g., `idtypecuisine`) using mapping dictionaries.
- **Outlier Removal**: Eliminated entries with unrealistic values, such as zero surface area or 22 bedrooms.
- **Feature Engineering**: Grouped high-cardinality variables (e.g., `ville` into "Paris" and "Banlieue") and created a `freq_annonce` feature to capture advertisement frequency.

These steps ensured the data was clean and suitable for modeling.

## Modeling
The project implemented:
- **Ordinary Least Squares (OLS) Regression**: Identified significant predictors like `surface` and specific Paris districts.
- **Random Forest Regression**: Highlighted `surface` and `typedebien` as key features.
- **Linear Regression**: Trained on an 80/20 train-test split to predict prices.

## Results
Key findings:
- **OLS Regression**: Achieved an R-squared of 0.820, with `surface` and location as top predictors.
- **Random Forest Regression**: Confirmed `surface` and `typedebien` as the most important features.
- **Linear Regression**: Obtained an R-squared of 0.822 on the test set, with an RMSE of 164,653 and a correlation of 0.899 between predicted and actual prices.

These results indicate strong predictive performance, with `surface` being the primary driver of property prices.

## Technologies Used
- Python 3.x
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Statsmodels

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/yassirbelarche/Real-Estate-Price-Prediction.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebook:
   ```bash
   jupyter notebook main.ipynb
   ```

## Visualizations
The project includes:
- **Scatter Plot**: Surface area vs. price, showing a strong positive correlation.
![Prices based on different quantity variabes](images/Prices%20based%20on%20different%20quantity%20variabes.png)
- **Box Plot**: Price distribution by location, highlighting higher prices in Paris.
![Price distribution by location](images/Price%20distribution%20by%20location.png)
- **Feature Importance Chart**: From Random Forest, emphasizing key predictors.
![Feature Importance Bar Plot](images/Feature%20Importance%20Bar%20Plot.png)
- **Error Histogram**: Distribution of prediction errors for model evaluation.
![Histogram of Actual vs. Predicted Prices](images/Histogram%20of%20Actual%20vs.%20Predicted%20Prices.png)

## Challenges and Solutions
- **High-Cardinality Variables**: Simplified `ville` by grouping into "Paris" and "Banlieue" to reduce dimensionality.
- **Outliers**: Removed entries with erroneous data to improve model accuracy.
- **Encoding Issues**: Corrected special characters in text data for accurate categorization.

## Future Work
- Incorporate additional features, such as proximity to amenities or market trends.
- Experiment with advanced models like gradient boosting or neural networks.
- Perform hyperparameter tuning to optimize model performance.
- Develop a web application for real-time price predictions.

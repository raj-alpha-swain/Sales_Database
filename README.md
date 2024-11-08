
# Sales Prediction Model

This project is a machine learning model for predicting sales of various products in different types of outlets. The model uses regression techniques to predict sales values based on various product and outlet features.

## Table of Contents

1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Installation](#installation)
4. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
5. [Data Preprocessing](#data-preprocessing)
6. [Model Training](#model-training)
7. [Evaluation](#evaluation)
8. [Results](#results)
9. [Contributing](#contributing)
10. [License](#license)

## Introduction

The objective of this project is to build a model that accurately predicts product sales based on historical data. This model can be useful for understanding factors that influence sales and for making informed business decisions regarding inventory management, pricing, and promotional activities.

## Dataset

The dataset used in this project is sourced from `Train.csv`. It contains information about product attributes, outlet characteristics, and historical sales data.

### Columns in the Dataset

- `Item_Identifier`: Unique product ID
- `Item_Weight`: Weight of the product
- `Item_Fat_Content`: Indicates whether the product is low fat or regular
- `Item_Visibility`: Percentage of the total display area of all products in a store allocated to this particular product
- `Item_Type`: Category to which the product belongs
- `Item_MRP`: Maximum Retail Price (price at which the product is sold)
- `Outlet_Identifier`: Unique identifier for the outlet
- `Outlet_Size`: The size of the outlet (e.g., Small, Medium, Large)
- `Outlet_Location_Type`: The type of city where the outlet is located
- `Outlet_Type`: The category of the outlet (e.g., Grocery Store, Supermarket Type1)
- `Item_Outlet_Sales`: Sales of the product in a particular outlet (target variable)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sales-prediction-model.git
   cd sales-prediction-model
   ```

2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook or Python file:
   - Open `Sales Database.ipynb` in Jupyter Notebook/Google Colab to view and execute the code.

## Exploratory Data Analysis (EDA)

The initial analysis included visualizing different product and outlet features to understand the data distribution and potential correlations with sales. Key visualizations were:

1. **Distribution of Product Weights**  
2. **Visibility, MRP, and Outlet Sales Distributions**
3. **Counts of Outlet Establishment Years, Item Fat Content, and Outlet Sizes**

These visualizations helped identify any data inconsistencies and missing values, leading to a more refined data cleaning and preprocessing phase.

## Data Preprocessing

Steps involved:

1. **Handling Missing Values**
   - Replaced missing values in `Item_Weight` with the mean.
   - Filled missing values in `Outlet_Size` with the mode of `Outlet_Size` for each `Outlet_Type`.

2. **Label Encoding**  
   - Converted categorical variables like `Item_Fat_Content`, `Item_Type`, and `Outlet_Size` into numerical form.

3. **Feature Engineering**  
   - Split data into training and testing sets.

## Model Training

We used the `XGBRegressor` model to train our data. Key steps include:

1. **Splitting the Data**  
   - Used an 80-20 train-test split.

2. **Training the Model**  
   - Trained `XGBRegressor` on the training dataset.

3. **Hyperparameter Tuning**  
   - Default parameters were used; you can improve performance by tuning parameters for `XGBRegressor`.

## Evaluation

The model was evaluated using the **R-Squared (R²)** metric, which measures the proportion of variance in the target variable explained by the features.

- **Training R² Score**: 0.876
- **Testing R² Score**: 0.502

These scores indicate that the model performs well on training data but shows some overfitting, as the performance drops on the test set.

## Results

The model provides a reasonable approximation for predicting sales, with potential for improvement by tuning hyperparameters or using more advanced feature engineering techniques. Future steps may include testing additional models or using ensemble techniques to improve performance on the test set.

## Contributing

Feel free to contribute to this project by:
- Reporting issues
- Making pull requests
- Suggesting new features

## License

This project is licensed under the MIT License.

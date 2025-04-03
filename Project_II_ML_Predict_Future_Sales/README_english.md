
# Predict Future Sales – Machine Learning Project

This project aims to predict the number of products sold per store and product for the upcoming month, using historical sales data from an e-commerce platform.

## Project Description

This project addresses a real-world demand forecasting problem in an e-commerce environment. Using historical monthly sales data, the goal is to build a model that can anticipate how many units of each product will be sold in each store in the next month.

I chose this project because it directly connects to real-world applications in logistics, inventory planning, and resource optimization. It is based on a well-documented and complete dataset available on Kaggle, which allows the application of advanced Machine Learning techniques with business impact.

## Model Objective

The main objective is to build a Machine Learning model capable of predicting the number of products sold (`item_cnt_month`) per store and product in the next month (month 34), based on historical monthly sales data.

This model aims to answer key business questions such as:
- How many units of a product will be sold in a specific store next month?
- Which stores have the highest sales volume by category?
- Which products show an increasing or decreasing trend?
- What historical factors (month, store, category, product) influence demand?

Accurate demand prediction enables better logistics, inventory control, and strategic decision-making in e-commerce.

## Data Source

The data comes from the Kaggle competition [Predict Future Sales](https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales). The dataset simulates a monthly sales environment in a Russian e-commerce store.

Files used in this project:

- `sales_train.csv`: Historical sales data from January 2013 to October 2015 (daily records).
- `test.csv`: Store-product combinations for which sales in November 2015 (month 34) must be predicted.
- `items.csv`: Information about products.
- `item_categories.csv`: Product categories.
- `shops.csv`: List of stores.

### Data Summary

- `sales_train.csv`: 2,935,849 records and 6 columns (`date`, `date_block_num`, `shop_id`, `item_id`, `item_price`, `item_cnt_day`)
- `items.csv`: 22,170 products
- `item_categories.csv`: 84 categories
- `shops.csv`: 60 stores

The goal is to predict the value `item_cnt_month` for each row in `test.csv`, i.e., how many units will be sold per product and store in month 34.

## Repository Structure


Project_II_ML_Predict_Future_Sales/
│
├── presentation/                 # Final presentation
├── src/
│   ├── data/                     # Original and processed files (.csv)
│   ├── final_notebook/          # Clean notebook for delivery
│   ├── models/                  # Trained model (.joblib)
│   ├── notebooks/               # Step-by-step development notebooks (EDA, cleaning, modeling, etc.)
│   └── utils/                   # Helper functions (if any)
│
├── README.md                    # Project description
└── requirements.txt             # Libraries used in the project environment

## Model Results

The final model was trained using XGBoostRegressor and evaluated using RMSE (Root Mean Squared Error) on the validation set (month 33).

- Model used: XGBoost
- Metric: RMSE
- Validation RMSE: 0.8958

This result shows that the model performs well when predicting monthly sales by store and product. A clipping strategy was applied to restrict predictions to the range [0, 20], as specified in the Kaggle competition.

A `submission.csv` file was also generated with final predictions for month 34, ready for submission to the platform.

## Author

Project developed by Toni Santacruz as part of the Data Science Bootcamp.

- LinkedIn: https://www.linkedin.com/in/toni-santacruz
- Email: tonisantacruzadam@gmail.com

## Credits

This project is based on data provided by the Kaggle competition:  
Predict Future Sales – https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales

# :bar_chart: Advertising Sales Prediction using Multivariate Linear Regression

This repository contains a machine learning practice project implementing **Multivariate Linear Regression** to predict product sales based on advertising budgets across multiple media channels (TV, Radio, and Newspaper).

---

## :dart: Project Purpose & Overview

The goal of this project is to practice and demonstrate multivariate linear regression modeling:
- Modeling a continuous target variable (`Sales`) using multiple independent features (`TV`, `Radio`, and `Newspaper` budgets).
- - Cleaning and preprocessing data (filling missing values).
  - - Training a multivariate regression model using `scikit-learn`'s `LinearRegression` algorithm.
    - - Verifying the model predictions mathematically using coefficients and intercept values.
     
      - ---


      ## :file_folder: Dataset Information

      - **Dataset Name**: `advertising.csv`
      - - **Features (Independent Variables)**:
        -   - `TV` (Numeric): Advertising budget spent on TV (in thousands of dollars). (Feature $x_1$)
            -   - `Radio` (Numeric): Advertising budget spent on Radio (in thousands of dollars). (Feature $x_2$)
                -   - `Newspaper` (Numeric): Advertising budget spent on Newspaper (in thousands of dollars). (Feature $x_3$)
                    - - **Target Variable (Dependent Variable)**:
                      -   - `Sales` (Numeric): Product sales (in thousands of units). (Target $y$)
                       
                          - ---


                          ## :gear: Model Training & Preprocessing Pipeline

                          The notebook contains the following steps:

                          1. **Data Preprocessing**:
                          2.    - Checking for null/missing values in the dataset.
                                -    - Preprocessing the `Newspaper` column to fill missing values with the column's mean:
                                     -      `df.Newspaper.fillna(df.Newspaper.mean(), inplace=True)`
                                 
                                     -  2. **Model Training**:
                                        3.    - Initializing scikit-learn's `LinearRegression` model.
                                              -    - Fitting the model on the full features space: `X = df[['TV', 'Radio', 'Newspaper']]` and `y = df.Sales`.
                                               
                                                   - 3. **Mathematical Representation**:
                                                     4.    The trained model builds a linear plane represented by the equation:
                                                     5.   $$y = m_1 \cdot x_1 + m_2 \cdot x_2 + m_3 \cdot x_3 + b$$
                                                    
                                                     6.      Where:
                                                     7.     - **Intercept ($b$)**: `4.619625400823253` (Base sales when all advertising budgets are zero)
                                                     8.    - **TV Coefficient ($m_1$)**: `0.05444333`
                                                           -    - **Radio Coefficient ($m_2$)**: `0.1068452`
                                                                -    - **Newspaper Coefficient ($m_3$)**: `0.00064038`
                                                                 
                                                                     -    Thus, the prediction equation is:
                                                                     -       $$\text{Sales} = 0.05444 \times (\text{TV}) + 0.10685 \times (\text{Radio}) + 0.00064 \times (\text{Newspaper}) + 4.61963$$
                                                                 
                                                                     -   4. **Prediction & Mathematical Validation**:
                                                                         5.    - **Sample Inputs**: TV budget = **200**, Radio budget = **20**, Newspaper budget = **35.2**.
                                                                               -    - **Model Prediction**: `lr.predict([[200, 20, 35.2]])` outputs approximately **17.6677** (representing 17,668 units sold).
                                                                                    -    - **Manual Verification**:
                                                                                         -      $$\text{Sales} = 0.05444333(200) + 0.1068452(20) + 0.00064038(35.2) + 4.619625400823253 = 17.6677$$
                                                                                         -       This matches the model's prediction exactly.
                                                                                     
                                                                                         -   ---

                                                                                         ## :rocket: How to Run the Notebook

                                                                                         You can open and run this notebook directly in Google Colab. Click the badge below:

                                                                                         [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/umertabraiz/multivariate-linear-regression-practice/blob/main/Multivariant_Linear_Regression.ipynb)

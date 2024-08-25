# Predict Bikesharing Demand with Autogluon
This repository contains the code and resources for the Kaggle competition **"Predict Bike-sharing Demand"** using the [AutoGluon](https://auto.gluon.ai/stable/index.html) library. 
This project is part of **Udacity** nanodegree program [AWS Machine Learning Fundamentals](https://www.udacity.com/enrollment/nd189-aws-fundamentals)

## Project Overview
In this project, we utilize AutoGluon's **Tabular Prediction** to fit data from the CSV files provided by the Kaggle competition. The competition challenges participants to predict the total count of bikes rented during each hour, based on features such as weather conditions, seasonality, and holidays.

## Project Goals

- **Train several iterations of models:** Using AutoGluon to automatically explore a range of models and hyperparameters.
- **Optimize predictions:** Improve model accuracy through various optimization techniques.
- **Submit competition entries:** Achieve competitive results by submitting predictions to Kaggle.
- **Document findings:** Create a report to summarize the key learnings and results.

## Key Features

- **Automated Model Training:** Leverage AutoGluon's capabilities to train and evaluate models with minimal code.
- **Tabular Prediction:** Efficiently handle tabular datasets and extract useful insights.
- **Optimization Techniques:** Explore various methods to optimize model performance, such as feature engineering and hyperparameter tuning.
- **Kaggle Submissions:** Submit predictions to Kaggle and track ranking progress.

## Results

This project culminates in several submissions to the Kaggle competition, each representing different strategies and iterations. The final report will detail the best-performing models, the optimizations applied, and the overall ranking achieved.

## How to Use
1. Clone the repository:
```bash
git clone https://github.com/Menna-Elmeligy/udacity_predict_bikesharing_demand_autogluon.git
cd udacity_predict_bikesharing_demand_autogluon
```
2. Set up the Conda environment:

```bash
conda create --name bike_share python=3.8
conda activate bike_share
```

3. Install dependencies:
`pip install -r requirements.txt`

4. Run the Jupyter notebook:
`jupyter lab` and then choose the project notebook.

5. Follow the steps in the notebook to train models and make predictions.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue to discuss improvements or suggestions.





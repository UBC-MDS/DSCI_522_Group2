# Diabetes Classification Models

Members: Angela Chen, Ella Hein, Scout McKee, and Sharon Voon.

Milestone 2 project for DSCI 522.

## About

In this project, we try to create models for predicting diabetes. We try
several different models such as logistic regression, k- nearest
neighbours (k-nn), and decision tree. The logistic regression model was
most accurate and the k-nn model was second best. We attempted to
optimize the hyperparameters of the k-nn model to see if we could make it
as accurate as the logistic regression in predicting diabetes.

At the end we evaluated our following best performing models based on accuracy,
precision, recall, and AUC-ROC score using the test dataset:
- logistic regression model
- k- nearest neighbours (k-nn) with n_neighbours = 100
Based on the evaluation metrics, the Logistic Regression model performs better
than the K-Nearest Neighbors model on the provided test dataset. Considering
these results and the fact that Logistic Regression also offers interpretability
of feature coefficients, we decided to recommend the logistic regression model.

The data set used for this project was created through funding from the
CDC to "better understand the relationship between lifestyle and
diabetes in the US". It can be found in the UC Irvine Machine Learning
Repository
(<https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators>).
Each row is data for one patient. As explained in the UC Irvine Machine
Learning Repository for this data, there are 35 features which consist
of some demographics, lab test results, and answers to survey questions
for each patient.

## Report

The final report can be found [here](https://github.com/UBC-MDS/diabetes_classification_model/blob/main/doc/diabetes_classification_model_report.pdf).

## Dependencies

This project uses Docker image that is built on  quay.io/jupyter/minimal-notebook:2023-11-19. Additional dependencies can be found 
in the DockerFile as well as the env-dsci-522.yaml.

## Usage

This analysis can be run with either Docker or Virtual Environment through the respective set-up instructions provided below.

### Set up:

### Virtual Environment:

1. Clone the GitHub repository for this project.
2. Run the following from the root of this repository:

``` bash
conda env create --file env-dsci-522.yaml
```

### Docker:

1. Clone the GitHub repository for this project.
2. Install Docker [here](https://www.docker.com/get-started/) and  follow the given instruction.
3. Launch  Docker on your local computer.

## Running the Analysis

### Virtual Environment:

1. To run the analysis, run the following from the root of this repository:

``` bash
conda activate Diabetes_Prediction
jupyter lab 
```

2. Open `diabetes_classification_model.ipynb` in Jupyter Lab that is located inside the src folder. Under the "Kernel" menu click
"Restart Kernel and Run All Cells...".


### Docker:

1. To run the analysis, run the following from the root of this repository:
```         
docker compose up
```

2. Click on the link provided in the terminal that starts with `http://127.0.0.1:8888/lab` or copy and paste it into your web browser.

3. Navigate into the 'work/src' folder and open the jupyter notebook named 'diabetes_classification_model.ipynb. under the "Kernel" menu click
"Restart Kernel and Run All Cells...".

## Running the tests

The test written for each function is stored in the tests folder. To run the tests, run the following from the root of this repository:

``` bash
pytest tests/* 
```

## Important note on obtaining the dataset

The UC Irvine Machine Learning Repository gives a link to download the dataset off Kaggle. Since this requires authenication, here is a more direct way to obtain the data form UC Irvine without using Kaggle.

On the command line run: pip install ucimlrepo

Then paste the following code at the beginning of the analysis document, replacing the current section which reads in the data.

from ucimlrepo import fetch_ucirepo \# fetch dataset cdc_diabetes_health_indicators = fetch_ucirepo(id=891) \# data (as pandas dataframes) X = cdc_diabetes_health_indicators.data.features y = cdc_diabetes_health_indicators.data.targets

## License

The Diabetes Prediction materials here are licensed under the Creative Commons Attribution-NonCommercial-NoDerivs 4.0 International (CC BY-NC-ND 4.0 DEED) and the MIT license. If re-used/re-mixed please provide attribution and link to this webpage.

## Contributing

Contributions are always welcome but please do refer to [CONTRIBUTING.md](https://github.com/UBC-MDS/diabetes_classification_model/blob/main/CONTRIBUTING.md) for more details.

## References

Centers for Disease Control and Prevention. (2014). CDC Diabetes Health 
Indicators. University of California, Irvine, School of Information; 
Computer Sciences. Retrieved November 14, 2023, from 
https://archive.ics.uci.edu/dataset/891/cdc+diabetes+health+indicators

Sapra, A., & Bhandari, P. (2023, June 21). Diabetes. In StatPearls [Internet].
Treasure Island (FL): StatPearls Publishing. Available from: 
https://www.ncbi.nlm.nih.gov/books/NBK551501/

VanderPlas, J., Granger, B., Heer, J., Moritz, D., Wongsuphasawat,
K., Satyanarayan, A., ... Sievert, S. (2018). Altair: Interactive statistical
visualizations for Python. Journal of Open Source Software, 3(32), 1057.

Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python.
Journal of Machine Learning Research, 12, 2825-2830.

McKinney, W. (2010). Data structures for statistical computing in Python.
Proceedings of the 9th Python in Science Conference, Volume 445.

# Predicting international football results from past performance

The use of data in football is getting more and more sophisticated, while access to data remains difficult and expensive. The purpose of this project is to take a step back, and examine how much one can get meaningful insights from data that are readily accessible to public.

The initial motivation for this exercise came from Euro 24, as I was working on classical machine learning projects when I was watching the tournament. So the focus here is international football, and models have been trained with data prior to summer 2024, keeping Euro 24 results as unseen data for final tests.

Overall, the notebooks in this repo seek to answer the following question: If we want to predict match results in a main international tournament like Euro 24, should predictions made with a general-purpose model or a model tailored for big tournaments?

## Project contents

### Data

The data come from this Kaggle dataset: [International football results from 1872 to 2024](https://www.kaggle.com/datasets/martj42/international-football-results-from-1872-to-2017). It was saved under the directory 'data/raw/' with the file name 'results.csv'. The processed datasets are saved under directory 'data/processed/'. Note that data files are not pushed.

### Notebooks

Two approaches have been followed here: (1) predicting any result from past performance from a rolling-window time frame, and (2) prediction main tournament results from qualification phase performance. There are separate notebooks for data processing and modelling regarding these two approaches, names beginning with 'rolling_perf' and 'qual_perf' respectively.

The notebooks with names ending with '_data_prep' are for data processing, which take the main data, calculate performance metrics from respective time frames, add these back to the dataset, and save it. The notebooks with names ending with '_model' are for modelling, which take the processed data, compare the performance of potential models, conduct hyperparameter tuning and (as applicable) feature selection, evaluate the model and save it.

The notebook 'euro24_test' is for testing and comparing two modelling strategies with Euro 24 data.

### Models

These are the models created in the notebooks mentioned above. 

## Requirements

Data processing mainly relies on `pandas`, and modelling makes use of `PyCaret` workflows. The project has been conducted in a conda virtual environment, and the environment file is included for reproducibility.

## Insights and future directions

The final tests on unseen Euro 24 data show that the model tailored for big international tournaments performs better. This is despite the fact that this modelling strategy can make use of smaller training datasets, and that the general-purpose model had seemed to perform better in training.

The exercise can be extended to match results from club football, and comparisons can be made between domestic leagues, domestic cups, and European tournaments. Similar comparisons can also be made with more sophisticated data, features, and models, to see if the difference between the modelling strategies hold with more accurate models.
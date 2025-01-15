# Predicting international football results from past performance

The use of data in football is getting more and more sophisticated, while access to data remains difficult and expensive. The purpose of this project is to take a step back, and examine how much one can get meaningful insights from data that are readily accessible to public.

Focusing on international football, the notebooks in this repo look for answers to these questions:
* Can we predict match results from past performance? If so, how long should the timeframe be?
* Should big international tournaments, like World Cup and European Championship, be modelled differently?

## Project contents

### Data

The data come from this Kaggle dataset: [International football results from 1872 to 2024](https://www.kaggle.com/datasets/martj42/international-football-results-from-1872-to-2017). It was saved under the directory 'data/raw/' with the file name 'results.csv'. The processed datasets are saved under directory 'data/processed/'. Note that data files are not pushed.

### Notebooks

Two approaches have been followed here: (1) predicting any result from past performance from a rolling-window time frame, and (2) prediction main tournament results from qualification phase performance. There are separate notebooks for data processing and modelling regarding these two approaches, names beginning with 'rolling_perf' and 'qual_perf' respectively.

The notebooks with names ending with '_data_prep' are for data processing, which take the main data, calculate performance metrics from respective time frames, add these back to the dataset, and save it. The notebooks with names ending with '_model' are for modelling, which take the processed data, compare the performance of potential models, conduct hyperparameter tuning and (as applicable) feature selection, evaluate the model and save it.

### Models

These are the models created in the notebooks mentioned above. 

## Requirements

Data processing mainly relies on `pandas`, and modelling makes use of `PyCaret` workflows. The project has been conducted in a conda virtual environment, and the environment file is included.
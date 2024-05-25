# California Housing Data Analysis

This project involves analyzing the California Housing dataset using different polynomial regression models (linear, quadratic, and cubic) to predict the median house values. The performance of each model is evaluated based on the prediction error.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Functions](#functions)
- [Dataset](#dataset)
- [Output](#output)

## Installation

To run this project, you'll need Python 3 and the following libraries:
- `numpy`
- `matplotlib`
- `scikit-learn`

You can install the required libraries using pip:
```bash
pip install numpy matplotlib scikit-learn
```

## Usage

1. Clone this repository or download the script `hw12prog.py`.
2. Run the script using Python:
```bash
python hw12prog.py
```

## Functions

### `dist(x, y)`
Computes the Euclidean distance between two vectors `x` and `y`.

### `linear_design_matrix(ind_vars)`
Builds the design matrix for fitting a linear function to the dataset.

### `quadratic_design_matrix(ind_vars)`
Builds the design matrix for fitting a quadratic function to the dataset.

### `cubic_design_matrix(ind_vars)`
Builds the design matrix for fitting a cubic function to the dataset.

### `fit(design_matrix, observations)`
Solves the least squares equation for the given design matrix and observations, and returns the parameters, predicted values, and prediction error.

## Dataset

The California Housing dataset is fetched using `sklearn.datasets.fetch_california_housing`. It contains the following information:
- Number of data points: 20,640
- Independent variables (8 total):
  - Median Income
  - House Age
  - Average Rooms
  - Average Bedrooms
  - Population
  - Average Occupancy
  - Latitude
  - Longitude
- Dependent variable: Median house value (in multiples of $100,000)

## Output

The script outputs a report with the following information:
- Dataset information
- Prediction errors for the linear, quadratic, and cubic models

Sample output:
```
======
REPORT
======

Dataset Info
------------
    - Number of data points: 20640

    - Independent variables: (8 total)

    - MedInc        median income in block group
    - HouseAge      median house age in block group
    - AveRooms      average number of rooms per household
    - AveBedrms     average number of bedrooms per household
    - Population    block group population
    - AveOccup      average number of household members
    - Latitude      block group latitude
    - Longitude     block group longitude

    - Dependent variable: median house value (multiples of $100,000)

    - Note: from 1990 census, each row represents a single district

Prediction Error
----------------
   linear func. model:   104.02877080332314
quadratic func. model:   93.29519827668858
    cubic func. model:   86.47992658692596
```

## Visualization

The script also includes code to plot the predictions against the actual values, which can be uncommented to visualize the results:
```python
plt.scatter(dep_vars, y_hat_cube)
plt.plot([0, 5], [0, 5], color='red')
plt.show()
```
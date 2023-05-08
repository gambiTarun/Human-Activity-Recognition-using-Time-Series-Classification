# Human Activity Recognition using Time-Series Classification

This project aims to classify human activities based on time series data obtained from a Wireless Sensor Network. The dataset used in this project is the [AReM dataset](https://archive.ics.uci.edu/ml/datasets/Activity+Recognition+system+based+on+Multisensor+data+fusion+\%28AReM\%29).

## Dataset

The dataset contains 7 folders representing seven types of activities. In each folder, there are multiple files, each representing an instance of a human performing an activity. Each file contains 6 time series collected from the activities of the same person, which are:

- avg rss12
- var rss12
- avg rss13
- var rss13
- avg rss23
- var rss23

There are 88 instances in the dataset, each containing 6 time series with 480 consecutive values.

## Project Structure

The project consists of the following steps:

1. **Time Series Classification Part 1: Feature Creation/Extraction**
    - Research and list time-domain features used in time series classification.
    - Extract time-domain features (minimum, maximum, mean, median, standard deviation, first quartile, and third quartile) for all 6 time series in each instance.
    - Estimate the standard deviation and build a 90% bootstrap confidence interval for each feature's standard deviation.
    - Select the three most important time-domain features.

2. **Time Series Classification Part 2: Binary and Multiclass Classification**
    - Binary Classification using Logistic Regression
        - Depict scatter plots of selected features and distinguish bending from other activities.
        - Break each time series into two equal parts and repeat the experiment.
        - Break each time series into `l ∈ {1, 2, ..., 20}` time series and use logistic regression to solve the binary classification problem.
    - Binary Classification using L1-penalized logistic regression
        - Repeat the previous step using L1-penalized logistic regression.
        - Compare L1-penalized logistic regression with variable selection using p-values.
    - Multi-class Classification (The Realistic Case)
        - Build an L1-penalized multinomial regression model to classify all activities.
        - Repeat the process using Naïve Bayes' classifier with Gaussian and Multinomial priors.
        - Compare the results to determine the better method for multi-class classification.

## Usage

To run the project, follow these steps:

1. Clone the repository and navigate to the project directory.
2. Download and extract the AReM dataset into the project directory.
3. Install the required packages:
    ```
    pip install -r requirements.txt
    ```
4. Run the project script:
    ```
    python main.py
    ```

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).
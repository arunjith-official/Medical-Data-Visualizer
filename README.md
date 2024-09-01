# Medical Data Visualizer

This project involves visualizing and analyzing medical examination data using Python libraries like Pandas, Matplotlib, and Seaborn. The data includes various patient measurements, blood test results, and lifestyle choices. The goal is to explore relationships between cardiac disease, body measurements, blood markers, and lifestyle factors.

## Data Description

- **File name**: `medical_examination.csv`
- The rows represent individual patients, while columns provide information about body measurements, blood test results, and lifestyle choices.

| Feature                              | Variable Type        | Variable        | Value Type                          |
|--------------------------------------|----------------------|-----------------|-------------------------------------|
| Age                                  | Objective Feature    | age             | int (days)                          |
| Height                               | Objective Feature    | height          | int (cm)                            |
| Weight                               | Objective Feature    | weight          | float (kg)                          |
| Gender                               | Objective Feature    | gender          | categorical code                    |
| Systolic blood pressure              | Examination Feature  | ap_hi           | int                                 |
| Diastolic blood pressure             | Examination Feature  | ap_lo           | int                                 |
| Cholesterol                          | Examination Feature  | cholesterol     | 1: normal, 2: above normal, 3: well above normal |
| Glucose                              | Examination Feature  | gluc            | 1: normal, 2: above normal, 3: well above normal |
| Smoking                              | Subjective Feature   | smoke           | binary                              |
| Alcohol intake                       | Subjective Feature   | alco            | binary                              |
| Physical activity                    | Subjective Feature   | active          | binary                              |
| Presence or absence of cardiovascular disease | Target Variable     | cardio          | binary                              |

## Tasks

The goal is to create a series of visualizations and analyses based on the data. The steps are as follows:

1. **Add an Overweight Column**:
   - Calculate BMI by dividing weight in kilograms by the square of height in meters.
   - Mark a person as overweight if their BMI is greater than 25 (1 for overweight, 0 otherwise).

2. **Normalize Data**:
   - Convert the cholesterol and glucose columns by setting values of 1 to 0 (good) and values greater than 1 to 1 (bad).

3. **Create a Categorical Plot**:
   - Convert the DataFrame into long format using `pd.melt()` to include the variables: cholesterol, gluc, smoke, alco, active, and overweight.
   - Use Seaborn’s `catplot()` to create a chart showing counts of each feature grouped by the presence or absence of cardiovascular disease (`cardio`). 

4. **Clean the Data**:
   - Filter out erroneous data:
     - Remove rows where diastolic pressure (`ap_lo`) is higher than systolic pressure (`ap_hi`).
     - Exclude data points that fall outside the 2.5th and 97.5th percentiles for height and weight.

5. **Create a Heat Map**:
   - Clean the data further to remove outliers based on height and weight percentiles.
   - Calculate the correlation matrix and visualize it using Seaborn’s `heatmap()`, masking the upper triangle of the matrix.

## Instructions

The code is implemented in `medical_data_visualizer.py`. Follow these instructions to complete the tasks:

1. **Import the data** from `medical_examination.csv` into a DataFrame called `df`.
2. **Add the overweight column** to the DataFrame.
3. **Normalize the data** for cholesterol and glucose.
4. **Create the categorical plot** using Seaborn's `catplot()` function.
5. **Clean the data** to remove erroneous rows based on specific conditions.
6. **Create the heat map** by plotting the correlation matrix.

## Development

- Write your code in `medical_data_visualizer.py`. 
- Use `main.py` to test your code during development.

## Testing

- Unit tests are provided in `test_module.py`.
- Tests are automatically imported into `main.py` for convenience.

## Example Output

- **Categorical Plot**: Displays counts of good and bad outcomes for cholesterol, gluc, alco, active, and smoke variables split by cardiovascular condition (`cardio`).
- **Heat Map**: Visualizes correlations between various features in the dataset.

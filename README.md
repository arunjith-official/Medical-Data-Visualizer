# Medical Examination Data Analysis and Visualization

This project involves visualizing and analyzing medical examination data using Python libraries such as `matplotlib`, `seaborn`, and `pandas`. The data represents various health and lifestyle metrics collected from patients during medical examinations. This project explores the relationship between cardiovascular disease, body measurements, blood markers, and lifestyle choices.

## Project Overview

The aim of this project is to provide insights into medical data through data visualization and statistical calculations. We explore key health metrics and visualize their impact on cardiovascular health, creating categorical plots and a heatmap to represent the data effectively.

## Dataset Description

- **File Name**: `medical_examination.csv`
- **Dataset**: Each row represents a patient, and each column represents patient information, such as body measurements, blood test results, and lifestyle choices.

### Features and Variable Descriptions

| Feature                     | Variable Type        | Value Type                                  |
|-----------------------------|----------------------|---------------------------------------------|
| Age                         | Objective Feature    | Age in days (int)                           |
| Height                      | Objective Feature    | Height in cm (int)                          |
| Weight                      | Objective Feature    | Weight in kg (float)                        |
| Gender                      | Objective Feature    | Categorical code (1: Female, 2: Male)       |
| Systolic blood pressure     | Examination Feature  | `ap_hi` (int)                               |
| Diastolic blood pressure    | Examination Feature  | `ap_lo` (int)                               |
| Cholesterol                 | Examination Feature  | 1: normal, 2: above normal, 3: well above normal |
| Glucose                     | Examination Feature  | 1: normal, 2: above normal, 3: well above normal |
| Smoking                     | Subjective Feature   | Binary (0: No, 1: Yes)                      |
| Alcohol intake              | Subjective Feature   | Binary (0: No, 1: Yes)                      |
| Physical activity           | Subjective Feature   | Binary (0: No, 1: Yes)                      |
| Presence of cardiovascular disease | Target Variable | Binary (0: No, 1: Yes)                      |

## Tasks Performed

1. **Data Cleaning and Preparation:**
   - Added an `overweight` column by calculating BMI (weight divided by height squared). If BMI > 25, set to 1 (overweight), else set to 0 (not overweight).
   - Normalized `cholesterol` and `gluc` values to indicate good (0) and bad (1) levels.
   - Removed incorrect data points:
     - Diastolic pressure higher than systolic.
     - Height and weight values outside the 2.5th and 97.5th percentiles.

2. **Data Visualization:**
   - Created categorical plots (`catplot`) using Seaborn to show value counts of categorical features (`cholesterol`, `gluc`, `smoke`, `alco`, `active`, and `overweight`), split by cardiovascular disease presence (`cardio`).
   - Generated a heatmap to visualize the correlation between different health indicators.

## Key Insights

- **Categorical Plots**: Show the distribution of good and bad values for key health indicators split by the presence of cardiovascular disease.
- **Heatmap**: Reveals the relationships and correlations between various health metrics, offering a deeper understanding of the data.

## How to Run the Project

1. **Install Dependencies**:
   Ensure you have Python installed, along with the necessary libraries:

   ```bash
   pip install pandas seaborn matplotlib
   ```

2. **Run the Analysis**:
   Use the provided Python scripts to load, clean, and visualize the data:

   ```bash
   python medical_data_visualizer.py
   ```

3. **Testing**:
   Unit tests are included in `test_module.py`. Run the tests with:

   ```bash
   python -m unittest test_module.py
   ```

## Conclusion

This project provides a comprehensive analysis of medical examination data, offering insights into the relationship between health metrics and cardiovascular disease. The visualizations and calculations help in understanding the impact of lifestyle choices and body measurements on heart health.

Feel free to explore the project, run the code, and gain insights from the data visualizations.

## License

This project is licensed under the MIT License.

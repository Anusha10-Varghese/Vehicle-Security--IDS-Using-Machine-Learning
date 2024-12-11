Enhancing Vehicle Security: Intrusion Detection Using Machine Learning

Dataset Information
Two datasets were used for this project:
1. Attack-Free Dataset: Contains normal network traffic.
2. DoS Attack Dataset: Contains network traffic with simulated DoS attacks.

Dataset Structure:
Timestamp: Time of data capture.
ID: Identifier for the message.
RTR: Remote Transmission Request (binary feature).
DLC: Data Length Code, indicating the size of the Data field.
Data: A list of hexadecimal values representing the message payload.

Dataset Sizes:
Attack-Free Dataset: ~2.27M records.
DoS Attack Dataset: ~656K records.

Key Steps in the Workflow
1. Data Preprocessing:
Handling Missing Values: The Data column in the DoS Attack dataset contained ~10,794 missing values, which were filled with a default value of ['00', '00', '00', '00', '00', '00', '00', '00'].
Data Conversion: The Data column, initially stored as strings, was converted into lists of integers representing hexadecimal values.
Column Removal: Columns with no variance or deemed irrelevant (e.g., RTR in the Attack-Free dataset) were removed.

2. Feature Engineering:
Features were extracted from the processed Data column:
min_data: Minimum byte value.
max_data: Maximum byte value.
mean_data: Mean of byte values.
std_data: Standard deviation of byte values.

3. Feature Selection:
Used the SelectKBest method with mutual_info_classif to evaluate feature importance.
Feature scores:
min_data: 0.0001
max_data: 0.2137
mean_data: 0.2036
std_data: 0.2977

4. Balancing the Dataset:
Applied SMOTE (Synthetic Minority Oversampling Technique) to address class imbalance.
Before SMOTE:
Class 0 (Normal): 2,268,519
Class 1 (Attack): 656,579

After SMOTE:
Class 0: 2,268,519
Class 1: 2,268,519

5. Modeling:
Two models were trained and evaluated:
(a) Random Forest Classifier:
    Features scaled using StandardScaler.
    Trained with balanced class weights to handle residual imbalance.
(b) Voting Classifier:
    Combined predictions from:
    Random Forest Classifier
    Logistic Regression
    Voting mechanism: Hard voting.

6. Model Evaluation:
Random Forest Results:
  Accuracy: 89.61%
  Precision: 91.24%
  Recall: 87.64%
  F1-Score: 89.41%

Confusion Matrix:
  True Positive: 596,713
  False Positive: 57,270
  True Negative: 622,984
  False Negative: 84,145

Voting Classifier Results:
  Accuracy: 76.16%
  Precision: 88.84%
  Recall: 59.86%
  F1-Score: 71.53%

Confusion Matrix:
  True Positive: 407,567
  False Positive: 51,188
  True Negative: 629,066
  False Negative: 273,291

7. Feature Importance:
From Random Forest Classifier:
  std_data: 37.70%
  mean_data: 35.03%
  max_data: 27.27%
  min_data: 0.00%

Visualization
Distribution of Features:
Histograms were plotted to visualize the distribution of Timestamp and DLC values for both datasets.

Confusion Matrices:
Heatmaps were generated for Random Forest and Voting Classifier predictions to better understand the performance.

How to Run the Project
Prerequisites: Python 3.13.10

Required Libraries:
    pandas
    numpy
    matplotlib
    scikit-learn
    imblearn
    ast

Steps:
Clone the repository or download the project files.
Place the Attack_free_dataset.csv and DoS_attack_dataset.csv in the project directory.
Run the script using:
python dos_detection.py
The script will output evaluation metrics and feature importance. Confusion matrices and other visualizations will also be displayed.


Project Overview
This project focuses on analyzing and classifying Denial of Service (DoS) attack data using machine learning techniques. It involves loading datasets, performing exploratory data analysis (EDA), preprocessing data, and training classification models to distinguish between attack and non-attack scenarios.

Prerequisites
The following software installed:
- Python: Version 3.8 or later
- Required Libraries: The project requires several Python libraries for data manipulation, visualization, and machine learning.

Required Libraries
install the necessary libraries using `pip`. Here’s a list of the required libraries:

pip install pandas numpy scikit-learn matplotlib imbalanced-learn


Dataset Requirements
The code requires two CSV files:
1. Attack_free_dataset.csv
2. DoS_attack_dataset.csv

Make sure these files are located in the same directory as the script.

Installation Instructions
1. Clone or Download the Repository: 
   Clone this repository to local machine or download it as a ZIP file.
2. Navigate to the Project Directory:
   cd <project-directory>
3. Install Required Libraries:
   If you have a `requirements.txt` file, run: 
   pip install -r requirements.txt
   If not, manually install the libraries listed above.
4. Place Datasets: Ensure that the dataset files are in the same directory as script.


How to Run the Code
1. Open a terminal or command prompt.
2. Run the script using Python:
   python <script_name>.py
3. The script will perform the following tasks:
   - Load and preprocess both datasets.
   - Conduct exploratory data analysis (EDA).
   - Train a Random Forest Classifier and a Voting Classifier.
   - Evaluate model performance with various metrics.

Output
The script will generate:
- Descriptive statistics for both datasets.
- Histograms showing distributions of key features.
- Confusion matrices for model evaluation.
- Feature importance scores from the Random Forest model.

Additional Notes
- The code handles class imbalance using SMOTE (Synthetic Minority Over-sampling Technique).
- Feature scaling is applied before training models.
- The Random Forest Classifier and Voting Classifier (which combines Random Forest and Logistic Regression) are used for classification tasks.

For any issues or questions regarding this project, please contact [Anusha Varghese].
GitHub URL: https://github.com/Anusha10-Varghese/Vehicle-Security--IDS-Using-Machine-Learning.git
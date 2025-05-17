# Heart Disease Prediction

Heart disease is a leading cause of death for people of most races in the U.S. (African Americans, American Indians and Alaska Natives, and whites). 
In this project we have predicted whether individuals have heart disease or not (HeartDisease column). 
This dataset includes information on 18 variables.

There are more than 3 lakhs records in this dataset.

Created separate .py files for model training and prediction.

Make sure that our dataset during the model building and prediction phase gone through the same data processing and feature creation steps.

# Target Column

HeartDisease – Binary classification: Yes or No (whether the individual has heart disease)


# Features

| Feature          | Type                                                     | Description                         |
| ---------------- | -------------------------------------------------------- | ----------------------------------- |
| BMI              | Numeric                                                  | Body Mass Index                     |
| Smoking          | Categorical (Yes/No)                                     | Whether the person smokes           |
| AlcoholDrinking  | Categorical (Yes/No)                                     | Drinks alcohol or not               |
| Stroke           | Categorical (Yes/No)                                     | History of stroke                   |
| PhysicalHealth   | Numeric                                                  | Number of physically unhealthy days |
| MentalHealth     | Numeric                                                  | Number of mentally unhealthy days   |
| DiffWalking      | Categorical (Yes/No)                                     | Difficulty walking                  |
| Sex              | Categorical (Male/Female)                                | Gender                              |
| AgeCategory      | Categorical (e.g., 55-59)                                | Age range                           |
| Race             | Categorical                                              | Race of the individual              |
| Diabetic         | Categorical (Yes/No/No, borderline/Yes during pregnancy) | Diabetes status                     |
| PhysicalActivity | Categorical (Yes/No)                                     | Involved in physical activity       |
| GenHealth        | Categorical (Poor to Excellent)                          | Self-assessed health                |
| SleepTime        | Numeric                                                  | Average hours of sleep per day      |
| Asthma           | Categorical (Yes/No)                                     | Whether the individual has asthma   |
| KidneyDisease    | Categorical (Yes/No)                                     | Kidney disease history              |
| SkinCancer       | Categorical (Yes/No)                                     | Skin cancer history                 |

# 🔍 Data Preprocessing

1. Missing values handled
2. Encoding: [One-Hot Encoding], pd.get_dummies()
3. Feature scaling: [MinMaxScaler]
4. Train/Test split: 80/20

# Model Selection
* Tried models:
    1. Random Forest
    2. XGBoost
*  Final model chosen: XGBoost

# 📈 Performance Metrics

  1. Confusion Matrix:
     
| Actual \ Predicted | Predicted 0 | Predicted 1 |
| ------------------ | ----------- | ----------- |
| **Actual 0**       | 54,418      | 4,153       |
| **Actual 1**       | 3,613       | 1,775       |

* True Negatives (TN): 54418
* False Positives (FP): 4153
* False Negatives (FN): 3613
* True Positives (TP): 1775
        
2. Classification Report (XGBoost)

| Metric    | Class 0 (No Disease) | Class 1 (Heart Disease) |
| --------- | -------------------- | ----------------------- |
| Precision | 0.94                 | 0.30                    |
| Recall    | 0.93                 | 0.33                    |
| F1-score  | 0.93                 | 0.31                    |
| Support   | 58,571               | 5,388                   |

  3. Overall:

| Metric          | Score  |
| --------------- | ------ |
| Accuracy        | 87.86% |
| Macro Avg F1    | 0.62   |
| Weighted Avg F1 | 0.88   |

# 🔍 Feature Importance (XGBoost): 

| Rank | Feature                   | Notes                                             |
| ---- | ------------------------- | ------------------------------------------------- |
| 1    | `DiffWalking`             | Most influential feature — difficulty in walking. |
| 2    | `AgeCategory_80 or older` | High risk associated with advanced age.           |
| 3    | `Stroke`                  | Prior stroke is a key health indicator.           |
| 4    | `AgeCategory_25-29`       | Surprisingly impactful for younger adults.        |
| 5    | `Diabetic_Yes`            | Diabetes strongly correlates with heart disease.  |
| 6    | `AgeCategory_75-79`       | Age continues to be an important factor.          |
| 7    | `GenHealth_Poor`          | Poor self-reported health = higher risk.          |



# Deliverables
✅ Trained ML model (.pkl)

✅ Python scripts (train, predict, utility)

Steps:
          
          # Create train_model.py
          with open("train_model.py", "w") as f:
              f.write("""# Your model training code here
          print("Training model...")""")
              
          import os
          print(os.getcwd())  # Usually outputs /content
          # OP: /content
          
          !ls
          # OP: sample_data  train_model.py
          
          !cat train_model.py
          # OP: Your model training code here
          #        print("Training model...")


from google.colab import files
files.download('train_model.py')
# Download the file

✅ Final Report with insights & performance

✅ Flask API (optional)

✅ README and documentation

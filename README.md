# SGD-Regressor-for-Multivariate-Linear-Regression

## AIM:
To write a program to predict the price of the house and number of occupants in the house with SGD regressor.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
## SGD Regressor for Multivariate Linear Regression

### Python Program

```
import numpy as npfrom sklearn.linear_model import SGDRegressorfrom sklearn.preprocessing import StandardScalerfrom sklearn.model_selection import train_test_splitfrom sklearn.metrics import mean_squared_error, r2_score# Dataset: Study hours, attendance, assignmentsX = np.array([    [2, 60, 3],    [3, 65, 4],    [4, 70, 5],    [5, 75, 6],    [6, 80, 7],    [7, 85, 8],    [8, 90, 9],    [9, 95, 10]])# Target: Marks scoredy = np.array([40, 45, 50, 55, 60, 65, 70, 75])# Split datasetX_train, X_test, y_train, y_test = train_test_split(    X, y, test_size=0.25, random_state=42)# Standardize featuresscaler = StandardScaler()X_train = scaler.fit_transform(X_train)X_test = scaler.transform(X_test)# Train SGD Regressormodel = SGDRegressor(max_iter=1000, tol=1e-3, random_state=42)model.fit(X_train, y_train)# Predict marksy_pred = model.predict(X_test)print("Actual Marks:", y_test)print("Predicted Marks:", np.round(y_pred, 2))print("Mean Squared Error:", round(mean_squared_error(y_test, y_pred), 2))print("R2 Score:", round(r2_score(y_test, y_pred), 2))# Predict marks for a new studentnew_student = np.array([[5, 75, 6]])new_student = scaler.transform(new_student)predicted_marks = model.predict(new_student)print("Predicted Marks for New Student:", round(predicted_marks[0], 2))
```

### Algorithm (5 Points)

1. Start the program and import the required libraries.
2. Create a dataset containing multiple input features and the target marks.
3. Split the dataset into training and testing sets, then standardize the input features.
4. Train the SGD Regressor model using the training data.
5. Predict marks for test and new student data, then evaluate the model using MSE and R² score.

## Program:
```
import numpy as np
from sklearn.linear_model import SGDRegressor
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

# Dataset: Study hours, attendance, assignments
X = np.array([
    [2, 60, 3],
    [3, 65, 4],
    [4, 70, 5],
    [5, 75, 6],
    [6, 80, 7],
    [7, 85, 8],
    [8, 90, 9],
    [9, 95, 10]
])

# Target: Marks scored
y = np.array([40, 45, 50, 55, 60, 65, 70, 75])

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.25, random_state=42
)

# Standardize features
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# Train SGD Regressor
model = SGDRegressor(max_iter=1000, tol=1e-3, random_state=42)
model.fit(X_train, y_train)

# Predict marks
y_pred = model.predict(X_test)

print("Actual Marks:", y_test)
print("Predicted Marks:", np.round(y_pred, 2))
print("Mean Squared Error:", round(mean_squared_error(y_test, y_pred), 2))
print("R2 Score:", round(r2_score(y_test, y_pred), 2))

# Predict marks for a new student
new_student = np.array([[5, 75, 6]])
new_student = scaler.transform(new_student)
predicted_marks = model.predict(new_student)

print("Predicted Marks for New Student:", round(predicted_marks[0], 2))
```

## Output:
<img width="941" height="107" alt="image" src="https://github.com/user-attachments/assets/119ea89f-64e7-4521-bff4-82d935dbd0f5" />



## Result:
Thus the program to implement the multivariate linear regression model for predicting the price of the house and number of occupants in the house with SGD regressor is written and verified using python programming.

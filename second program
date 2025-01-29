# Import necessary libraries
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
import matplotlib.pyplot as plt

# Import the given "Salary_Data.csv".
datasets = pd.read_csv("Salary_Data.csv")

# Splitting the data into train and test partitions.
# X = data[['YearsExperience']]
# y = data['Salary']

X = datasets.iloc[:, :-1].values
y = datasets.iloc[:, 1].values

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=1/3, random_state=0)

# Training and predict the model.
model = LinearRegression()
model.fit(X_train, y_train)
y_train_pred = model.predict(X_train)
y_test_pred = model.predict(X_test)


# Calculate the mean_squared error.
mse_train = mean_squared_error(y_train, y_train_pred)
mse_test = mean_squared_error(y_test, y_test_pred)

print(f"Mean Squared Error (Train): {mse_train}")
print(f"Mean Squared Error (Test): {mse_test}")

# Visualize both train and test data using a scatter plot.
plt.scatter(X_train, y_train, label='Train Data')
plt.scatter(X_test, y_test, label='Test Data', marker='x')
plt.plot(X_train, y_train_pred, color='red', label='Linear Regression (Train)')
plt.plot(X_test, y_test_pred, color='green', linestyle='dashed', label='Linear Regression (Test)')
plt.xlabel('Years of Experience')
plt.ylabel('Salary')
plt.legend()
plt.show()

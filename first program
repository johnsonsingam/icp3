import pandas as pd

# Reading the CSV file 'data.csv'.
url = "data.csv"
df = pd.read_csv(url)

# Showing the basic statistical description of the data.
description = df.describe()
print("Basic Statistical Description:")
print(description)

# Checking if the data has null values.
null_values = df.isnull().sum()

# Replace the null values with the mean.
df.fillna(df.mean(), inplace=True)

# Selecting at least two columns and aggregate the data using: min, max, count, mean
aggregated_data = df[['Duration', 'Calories']].agg(['min', 'max', 'count', 'mean'])
print("\nAggregated Data:")
print(aggregated_data)

# Filtering the dataframe to select the rows with calories values between 500 and 1000.
filtered_df1 = df[(df['Calories'] >= 500) & (df['Calories'] <= 1000)]

#  Filtering the dataframe to select the rows with calories values > 500 and pulse < 100.
filtered_df2 = df[(df['Calories'] > 500) & (df['Pulse'] < 100)]

# Creating a new "df_modified" dataframe that contains all the columns from df except for "Maxpulse".
df_modified = df.drop(columns=['Maxpulse'])
print("Deleting Maxpulse column.")
print(df_modified)

# Deleting the "Maxpulse" column from the main df dataframe.
df.drop(columns=['Maxpulse'], inplace=True)

# Converting the datatype of Calories column to int datatype
df['Calories'] = df['Calories'].astype(int)

# k. Using pandas create a scatter plot for the two columns (Duration and Calories)
import matplotlib.pyplot as plt

plt.scatter(df['Duration'], df['Calories'])
plt.xlabel('Duration')
plt.ylabel('Calories')
plt.title('Scatter Plot: Duration vs Calories')
plt.show()

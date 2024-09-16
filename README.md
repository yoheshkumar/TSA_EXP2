# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date: 25-08-24
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:
```
Name   : YOHESH KUMAR R.M
Reg No : 212222240118
```
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load the Microsoft Stock dataset
file_path = 'Microsoft_Stock.csv'
data = pd.read_csv(file_path)

# Convert 'Date' column to datetime with the correct format and sort
data['Date'] = pd.to_datetime(data['Date'], format='%m/%d/%Y %H:%M:%S')
data.sort_values('Date', inplace=True)

# Filter data for a specific range (e.g., 1 year)
start_date = '2019-01-01'
end_date = '2020-01-01'
filtered_data = data[(data['Date'] >= start_date) & (data['Date'] <= end_date)]

# Extract date and price for the filtered range
dates = filtered_data['Date']
prices = filtered_data['Close']

# Calculate linear trend
coeffs_linear = np.polyfit(np.arange(len(prices)), prices, 1)
linear_trend = np.polyval(coeffs_linear, np.arange(len(prices)))

# Calculate polynomial trend (degree 2)
coeffs_poly = np.polyfit(np.arange(len(prices)), prices, 2)
poly_trend = np.polyval(coeffs_poly, np.arange(len(prices)))

# Plotting Linear Trend
plt.figure(figsize=(12, 6))
plt.plot(dates, prices, color='blue', alpha=0.3, label='Original Data')  # Use transparency
plt.plot(dates, linear_trend, color='red', linewidth=2, label='Linear Trend')
plt.xlabel('Date')
plt.ylabel('Price')
plt.title('Linear Trend Estimation (Microsoft Stock)')
plt.legend()
plt.grid(True)
plt.show()

# Plotting Polynomial Trend
plt.figure(figsize=(12, 6))
plt.plot(dates, prices, color='blue', alpha=0.3, label='Original Data')  # Use transparency
plt.plot(dates, poly_trend, color='green', linewidth=2, label='Polynomial Trend (Degree 2)')
plt.xlabel('Date')
plt.ylabel('Price')
plt.title('Polynomial Trend Estimation (Microsoft Stock)')
plt.legend()
plt.grid(True)
plt.show()


```

### OUTPUT
A - LINEAR TREND ESTIMATION
![download](https://github.com/user-attachments/assets/71e37e1e-4a42-4795-974b-05f3f336cf64)


B- POLYNOMIAL TREND ESTIMATION
![download (1)](https://github.com/user-attachments/assets/0faf94f4-4512-4ca7-b86a-6a78c4c20c1b)


### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.

 import pandas as pd
import matplotlib.pyplot as plt

# Read the CSV data from the URL
url = "https://pynative.com/wp-content/uploads/2019/01/company_sales_data.csv"
df = pd.read_csv(url)

# ------------------------------------------------------------
# Exercise 1: Read Total profit of all months and show it using a line plot
# ------------------------------------------------------------
plt.figure(figsize=(10, 5))
plt.plot(df['month_number'], df['total_profit'], color='blue', marker='o', linestyle='-', linewidth=2, label='Total Profit')
plt.title("Company Profit Per Month")
plt.xlabel("Month Number")
plt.ylabel("Total Profit (in USD)")
plt.xticks(df['month_number'])
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()

# ------------------------------------------------------------
# Exercise 2: Read data for Bathing soap and Facewash of all months and display it using the Subplot
# ------------------------------------------------------------
plt.figure(figsize=(10, 8))

# Subplot 1: Bathing Soap Sales
plt.subplot(2, 1, 1)
plt.plot(df['month_number'], df['bathingsoap'], color='green', marker='o')
plt.title('Bathing Soap Sales Data')
plt.ylabel('Units Sold')
plt.xticks(df['month_number'])
plt.grid(True)

# Subplot 2: Facewash Sales
plt.subplot(2, 1, 2)
plt.plot(df['month_number'], df['facewash'], color='red', marker='o')
plt.title('Facewash Sales Data')
plt.xlabel('Month Number')
plt.ylabel('Units Sold')
plt.xticks(df['month_number'])
plt.grid(True)

plt.tight_layout()
plt.show()

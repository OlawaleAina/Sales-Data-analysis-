# Sales-Data-analysis-
import pandas as pd

# Load the sales data from a CSV file
sales_data = pd.read_csv('sales_data.csv')

# Perform data analysis and identify trends

# Calculate total sales
total_sales = sales_data['sales'].sum()

# Calculate average sales per customer
average_sales_per_customer = sales_data['sales'].mean()

# Calculate the top-selling products
top_selling_products = sales_data.groupby('product_name')['sales'].sum().nlargest(5)

# Generate recommendations for improving sales

# Calculate the overall sales growth rate
sales_growth_rate = (sales_data['sales'].iloc[-1] - sales_data['sales'].iloc[0]) / sales_data['sales'].iloc[0] * 100

# Identify underperforming products
underperforming_products = sales_data.groupby('product_name').filter(lambda x: x['sales'].sum() < 1000)['product_name'].unique()

# Output the results

print("Total Sales: $", total_sales)
print("Average Sales per Customer: $", average_sales_per_customer)
print("Top Selling Products:")
print(top_selling_products)
print("Sales Growth Rate: ", sales_growth_rate, "%")
print("Underperforming Products:")
print(underperforming_products)

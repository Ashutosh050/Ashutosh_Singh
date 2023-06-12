#Lawtech_assignment
#Enter the following worksheet and save this with the name ‘second sheet'. Now do any two of the following activities: .
#(a) Write a function to find the maximum no with the range C2 to F5
import pandas as pd

def find_maximum(worksheet):
    df = pd.DataFrame(worksheet)
    range_df = df.iloc[1:6, 2:6]  # Selecting the range C2 to F5
    return range_df.max().max()

worksheet = [
    ['A','B','C','D','E','F'],
    [20,200,25,35,35,44],
    [5,15,7,37,37,55],
    [7,17,1,18,18,22],
    [10,11,18,5,5,11],
    [15,23,17,7,7,9]
]

maximum_number = find_maximum(worksheet)
print("Maximum number within the range C2 to F5:", maximum_number)

#(b) Write a formula to find the average of the numbers within the range A1 to B5:
def find_average(worksheet):
    df = pd.DataFrame(worksheet)
    range_df = df.iloc[1:6, 0:2]  # Selecting the range A1 to B5
    return range_df.mean().mean()

average_number = find_average(worksheet)
print("Average of the numbers within the range A1 to B5:", average_number)

#(c) What will be the total of all numbers within the range A1 to F5:
def calculate_total(worksheet):
    df = pd.DataFrame(worksheet)
    range_df = df.iloc[1:6, 0:6]  # Selecting the range A1 to F5
    return range_df.values.sum()

total_sum = calculate_total(worksheet)
print("Total sum of all numbers within the range A1 to F5:", total_sum)

#(d) Find the minimum value within the range D1 to F5:
def find_minimum(worksheet):
    df = pd.DataFrame(worksheet)
    range_df = df.iloc[1:6,3:6]  # Selecting the range D1 to F5
    return range_df.min().min()

minimum_number = find_minimum(worksheet)
print("Minimum number within the range D1 to F5:", minimum_number)

#2. Make a bar chart to compare the sales figures of first 3 quarters of different item as shown in the following table.
#1 A 200 230 210 2 B 190 200 211 3 C 180 190 170 4 D 200 210 220
#Enter the above data in a worksheet and plot the bar chart along with the data.
import matplotlib.pyplot as plt
import numpy as np

# Data for the bar chart
items = ['A','B','C','D']
quarters = ['Q1','Q2','Q3']
sales_figures = np.array([
    [200,230,210],
    [190,200,211],
    [180,190,170],
    [200,210,220]
])

# Create the bar chart
x = np.arange(len(items))  # X-axis locations for the bars
width = 0.2  # Width of the bars

fig, ax = plt.subplots()
for i, quarter in enumerate(quarters):
    ax.bar(x + i * width, sales_figures[:, i], width, label=quarter)

# Set labels and titles
ax.set_xlabel('Items')
ax.set_ylabel('Sales Figures')
ax.set_title('Comparison of Sales Figures by Quarter')
ax.set_xticks(x + width)
ax.set_xticklabels(items)
ax.legend()

# Display the bar chart
plt.show()

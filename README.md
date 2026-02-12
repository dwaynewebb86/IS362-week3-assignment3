# IS362-week3-assignment3
# This Notebook will use Pandas and Python to analyze a hyphothetical bicyle trip from New York to Key West


# miles from new york to key west 1,436
# bring in NumPy and pandas

import numpy as np
import pandas as pd

# create one item Series
cumulative_miles = pd.Series([55, 120, 150, 180, 210, 250, 290, 330, 370, 420, 470, 510, 560, 600, 660, 710, 780, 830, 880, 940, 980, 1100, 1170, 1230, 1290, 1370, 1436], index=['Day 1', 'Day 2', 'Day 3', 'Day 4', 'Day 5', 'Day 6', 'Day 7', 'Day 8', 'Day 9', 'Day 10', 'Day 11', 'Day 12', 'Day 13', 'Day 14', 'Day 15', 'Day 16', 'Day 17', 'Day 18', 'Day 19', 'Day 20', 'Day 21', 'Day 22', 'Day 23', 'Day 24', 'Day 25', 'Day 26', 'Day 27'])
daily_miles = cumulative_miles.diff()
daily_miles.iloc[0] = cumulative_miles.iloc[0] 

# Display cumulative miles
print("Cumulative Miles (Odometer miles):")
print(cumulative_miles)

print("\n" + "="*50 + "\n")

# Display daily miles
print("Daily Miles Ridden:")
print(daily_miles)

# Create a DataFrame combining both Series to visualize the data together

bike_trip = pd.DataFrame({
    'Cumulative Miles': cumulative_miles,
    'Daily Miles': daily_miles
})

# Display the DataFrame
bike_trip
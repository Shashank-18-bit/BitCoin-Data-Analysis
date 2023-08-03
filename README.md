import matplotlib.pyplot as plt

# Assuming 'data' is your DataFrame containing the 'Close' column and the index is a datetime object

# Resample the 'Close' data yearly and calculate the mean
resampled_data = data['Close'].resample('Y').mean()

# Create a new figure and axis
fig, ax = plt.subplots(figsize=(10, 6))

# Plot the resampled data with a line plot
ax.plot(resampled_data.index, resampled_data, color='blue', marker='o', linestyle='-', linewidth=2, label='Yearly Average Close')

# Set the title and axis labels
ax.set_title('Yearly Average Closing Price', fontsize=16)
ax.set_xlabel('Year', fontsize=14)
ax.set_ylabel('Average Close Price', fontsize=14)

# Add gridlines for better readability
ax.grid(True)

# Add a legend to identify the plot
ax.legend(loc='upper left', fontsize=12)

# Beautify the x-axis date labels for better readability
fig.autofmt_xdate()

# Show the plot
plt.tight_layout()
plt.show()

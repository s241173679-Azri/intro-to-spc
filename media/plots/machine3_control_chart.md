# Python code to generate the control chart
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Assuming `data` is a pandas Series of measurements
# data = filtered_measurements_for_machine_3

mean = np.mean(data)
moving_ranges = np.abs(np.diff(data))
avg_moving_range = np.mean(moving_ranges)
d2 = 1.128 # Constant for subgroup size n=2 (for moving range)
ucl = mean + 3 * (avg_moving_range / d2)
lcl = mean - 3 * (avg_moving_range / d2)

fig, ax = plt.subplots(figsize=(12, 6))
ax.plot(data.index, data, marker='o', linestyle='-', color='#0072B2', label='Individual Measurement', markersize=4)
ax.axhline(mean, color='#009E73', linestyle='--', linewidth=2, label=f'Mean ({mean:.2f})')
ax.axhline(ucl, color='#E69F00', linestyle='-', linewidth=2, label=f'UCL ({ucl:.2f})')
ax.axhline(lcl, color='#D55E00', linestyle='-', linewidth=2, label=f'LCL ({lcl:.2f})')

ax.set_title(f'Individual Control Chart for Machine 3 (P=200kPa, T=338K)', fontsize=18)
ax.set_xlabel('Observation Index', fontsize=18)
ax.set_ylabel('Measurement Value', fontsize=18)
ax.tick_params(axis='x', labelsize=14)
ax.tick_params(axis='y', labelsize=14)
ax.legend(fontsize=12)
ax.grid(True, linestyle=':', alpha=0.7)
ax.set_facecolor('white')
fig.patch.set_facecolor('white')

plt.tight_layout()
plt.show()

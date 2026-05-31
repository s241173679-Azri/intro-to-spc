# Python code to generate the process capability chart
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats

# Assuming `data` is a pandas Series of measurements
# data = filtered_measurements_for_machine_3
# USL = 55, LSL = 45

mean = np.mean(data)
std = np.std(data, ddof=1)

fig, ax = plt.subplots(figsize=(12, 6))
sns.histplot(data, bins=30, kde=False, stat="density", color="#56B4E9", ax=ax, label='Process Data Histogram')

xmin, xmax = ax.get_xlim()
x = np.linspace(xmin, xmax, 100)
p = stats.norm.pdf(x, mean, std)
ax.plot(x, p, color="#CC79A7", linewidth=2, label=f'Normal Distribution (\$\mu={mean:.2f}\$, \$\sigma={std:.2f}\$)')

ax.axvline(55, color='red', linestyle='--', linewidth=2, label=f'USL ({usl})')
ax.axvline(45, color='red', linestyle='--', linewidth=2, label=f'LSL ({lsl})')
ax.axvline(mean, color="#009E73", linestyle=':', linewidth=2, label=f'Mean ({mean:.2f})')

ax.set_title(f'Process Capability for Machine 3 (P=200kPa, T=338K)', fontsize=18)
ax.set_xlabel('Measurement Value', fontsize=18)
ax.set_ylabel('Density', fontsize=18)
ax.tick_params(axis='x', labelsize=14)
ax.tick_params(axis='y', labelsize=14)
ax.legend(fontsize=12, loc='upper right')
ax.grid(True, linestyle=':', alpha=0.7)
ax.set_facecolor('white')
fig.patch.set_facecolor('white')

plt.tight_layout()
plt.show()

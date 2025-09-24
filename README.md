# wind-turbine

import numpy as np
import matplotlib.pyplot as plt

# Constants
air_density = 1.225  # kg/m^3
rotor_radius = 40    # meters
area = np.pi * rotor_radius**2  # swept area
Cp = 0.4  # Power coefficient (typical value for modern turbines)
efficiency = 0.9  # Generator efficiency

# Wind speed range
wind_speeds = np.linspace(3, 25, 100)  # m/s

# Power output calculation
def calculate_power(wind_speed):
    power = 0.5 * air_density * area * Cp * wind_speed**3 * efficiency
    return power / 1000  # Convert to kW

power_output = [calculate_power(ws) for ws in wind_speeds]

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(wind_speeds, power_output, label='Power Output (kW)', color='green')
plt.title('Wind Turbine Power Output vs Wind Speed')
plt.xlabel('Wind Speed (m/s)')
plt.ylabel('Power Output (kW)')
plt.grid(True)
plt.legend()
plt.show()

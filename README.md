# Mini-wind-power-generation# Mini Wind Power Generation Simulator

import math

# Constants
rho = 1.225          # Air density (kg/m^3)
radius = 0.5         # Turbine blade radius (m)
Cp = 0.35            # Power coefficient
generator_eff = 0.85 # Generator efficiency

# Swept area of turbine
A = math.pi * radius**2

def wind_power(wind_speed):
    """Calculate electrical power generated from wind speed."""
    
    if wind_speed < 3:
        return 0  # Cut-in speed
    
    if wind_speed > 20:
        wind_speed = 20  # Limit for safety
    
    mechanical_power = 0.5 * rho * A * Cp * wind_speed**3
    electrical_power = mechanical_power * generator_eff
    
    return electrical_power


print("Mini Wind Power Generation System")
print("----------------------------------")

wind_speed = float(input("Enter wind speed (m/s): "))

power = wind_power(wind_speed)

print(f"Wind Speed: {wind_speed:.2f} m/s")
print(f"Generated Power: {power:.2f} W")


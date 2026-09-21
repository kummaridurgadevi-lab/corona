# corona
import math

# Corona calculation in a transmission line

print("======================================")
print("   CORONA IN POWER SYSTEMS")
print("======================================")

# Input values
V = float(input("Enter line voltage (kV): "))
r = float(input("Enter conductor radius (cm): "))
d = float(input("Enter conductor spacing (cm): "))
m0 = float(input("Enter surface irregularity factor (m0): "))
delta = float(input("Enter air density factor (delta): "))

# Convert line voltage to phase voltage
V_phase = V / math.sqrt(3)

# Disruptive critical voltage
Vc = 21.1 * m0 * delta * r * math.log10(d / r)

print("\nResults")
print("--------------------------------------")
print(f"Phase voltage              = {V_phase:.2f} kV")
print(f"Disruptive critical voltage = {Vc:.2f} kV")

# Check corona condition
if V_phase > Vc:
    print("Corona is likely to occur.")
else:
    print("Corona is not likely to occur.")

print("--------------------------------------")

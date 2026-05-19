# Vehicle-Fuel-Efficiency-Analyser
The Vehicle Fuel Efficiency Analyser is a Python application that calculates vehicle mileage using distance and fuel consumption. It analyzes fuel efficiency and displays vehicle performance as excellent, good, average, or poor.
# Vehicle Fuel Efficiency Analyzer
# Simple Python program to calculate and analyze mileage

class Vehicle:
    def __init__(self, name, distance, fuel):
        self.name = name
        self.distance = distance      # in kilometers
        self.fuel = fuel              # in liters

    def calculate_efficiency(self):
        if self.fuel == 0:
            return 0
        return self.distance / self.fuel

    def efficiency_status(self):
        efficiency = self.calculate_efficiency()

        if efficiency >= 25:
            return "Excellent Fuel Efficiency"
        elif efficiency >= 15:
            return "Good Fuel Efficiency"
        elif efficiency >= 10:
            return "Average Fuel Efficiency"
        else:
            return "Poor Fuel Efficiency"

    def display_report(self):
        print("\n----- Vehicle Fuel Efficiency Report -----")
        print(f"Vehicle Name       : {self.name}")
        print(f"Distance Travelled : {self.distance} km")
        print(f"Fuel Consumed      : {self.fuel} liters")
        print(f"Fuel Efficiency    : {self.calculate_efficiency():.2f} km/l")
        print(f"Performance Status : {self.efficiency_status()}")


# Main Program
print("=== Vehicle Fuel Efficiency Analyzer ===")

vehicle_name = input("Enter Vehicle Name: ")
distance = float(input("Enter Distance Travelled (km): "))
fuel = float(input("Enter Fuel Consumed (liters): "))

vehicle = Vehicle(vehicle_name, distance, fuel)
vehicle.display_report()
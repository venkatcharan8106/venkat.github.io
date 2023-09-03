# venkat.github.io
# Constants for room rates and amenities costs
ROOM_RATES = {
    "Delux Room": 2500,
    "Suite Room": 4000
}

AMENITIES_COST = {
    "AC": 1000,
    "Locker": 300
}

# Function to calculate total cost
def calculate_total_cost(room_type, total_days, total_persons, amenities, advance_amount):
    room_cost = ROOM_RATES[room_type] * total_days
    amenities_cost = sum(AMENITIES_COST[amenity] for amenity in amenities)
    total_cost = room_cost + amenities_cost
    balance = total_cost - advance_amount
    return room_cost, amenities_cost, total_cost, balance

# Taking user inputs
customer_name = input("Customer Name: ")
check_in_date = input("Check-in Date: ")
total_days = int(input("Total No of Days: "))
total_persons = int(input("Total No of Persons: "))
room_type = input("Room Type (Delux Room/Suite Room): ")
amenities = input("Amenities (AC, Locker - separated by commas): ").split(", ")
advance_amount = int(input("Advance Amount: "))

# Calculating costs
room_cost, amenities_cost, total_cost, balance = calculate_total_cost(room_type, total_days, total_persons, amenities, advance_amount)

# Displaying results
print("\nBooking Details:")
print(f"Customer Name: {customer_name}")
print(f"Check-in Date: {check_in_date}")
print(f"Total No of Days: {total_days}")
print(f"Total No of Persons: {total_persons}")
print(f"Room Type: {room_type}")
print(f"Amenities: {', '.join(amenities)}")
print(f"Advance Amount: {advance_amount}")
print("\nCost Breakdown:")
print(f"Room Cost: {room_cost}")
print(f"Amenities Cost: {amenities_cost}")
print(f"Total Cost: {total_cost}")
print(f"Balance: {balance}")

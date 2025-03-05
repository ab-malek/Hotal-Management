# Hotal-Management
Python program to assist a hotel manager in offering rooms to customers based on their preferences. 


# Example usage:
# Create a hotel
hotel = Hotel("Ocean View Hotel")
# Add rooms to the hotel
hotel.add_room(Room(101, "Single", 100, ["Wi-Fi", "Air Conditioning", "TV"]))
hotel.add_room(Room(102, "Double", 150, ["Wi-Fi", "Air Conditioning", "TV", "Minibar"]))
hotel.add_room(Room(103, "Suite", 250, ["Wi-Fi", "Air Conditioning", "TV", "Minibar", "Ocean View"]))
hotel.add_room(Room(104, "Single", 90, ["Wi-Fi", "TV"]))
hotel.add_room(Room(105, "Double", 200, ["Wi-Fi", "Air Conditioning", "TV", "Minibar", "Balcony"]))
# Customer inputs preferences
print("Welcome to the hotel! Please provide your preferences:\n")

try:
    budget = float(input("Enter your budget (in USD): $"))
    preferred_room_type = input("Enter your preferred room type (Single, Double, Suite, or leave blank for any): ")
    required_amenities = input("Enter the amenities you require (comma separated, e.g., Wi-Fi, TV): ").split(",")
    required_amenities = [amenity.strip() for amenity in required_amenities]
    # Create a customer object
    customer = Customer(budget, preferred_room_type, required_amenities)
    # Offer rooms based on customer's preferences
    customer.offer_room(hotel)
except ValueError:
    print("Invalid input! Please enter valid numbers for budget.")

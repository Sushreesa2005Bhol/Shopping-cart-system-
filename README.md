# Shopping-cart-system-
For shopping cart

cart = {}

def add_item():
    name = input("Enter item name: ").title()
    price = float(input("Enter price: "))
    quantity = int(input("Enter quantity: "))

    if price < 0 or quantity <= 0:
        print("Invalid price or quantity!")
        return

    cart[name] = {
        "price": price,
        "quantity": quantity
    }
    print("Item added successfully!")

def view_cart():
    total = 0

    for name, item in cart.items():
        cost = item["price"] * item["quantity"]
        print(name, "=", cost)
        total += cost

    print("Total Bill: Rs.", total)

while True:
    print("\n1. Add Item")
    print("2. View Cart")
    print("3. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        add_item()
    elif choice == "2":
        view_cart()
    elif choice == "3":
        break
    else:
        print("Invalid choice!")
        

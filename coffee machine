MENU = {
    "espresso": {
        "ingredients": {
            "water": 50,
            "coffee": 18,
        },
        "cost": 1.5,
    },
    "latte": {
        "ingredients": {
            "water": 200,
            "milk": 150,
            "coffee": 24,
        },
        "cost": 2.5,
    },
    "cappuccino": {
        "ingredients": {
            "water": 250,
            "milk": 100,
            "coffee": 24,
        },
        "cost": 3.0,
    }
}

resources = {
    "water": 300,
    "milk": 200,
    "coffee": 100,
}
profit=0
button=True

def res_ing(odering):
    for item in odering:
        if odering[item] >= resources[item]:
            print(f"sorry you dont have enogh {item}")
            return False
    return True
def process_coins():
    """Returns the total calculated from coins inserted."""
    print("Please insert coins.")
    total = int(input("how many quarters?: ")) * 0.25
    total += int(input("how many dimes?: ")) * 0.1
    total += int(input("how many nickles?: ")) * 0.05
    total += int(input("how many pennies?: ")) * 0.01
    return total

def is_transaction_successful(money_received, drink_cost):
    """Return True when the payment is accepted, or False if money is insufficient."""
    if money_received >= drink_cost:
        change = round(money_received - drink_cost, 2)
        print(f"Here is ${change} in change.")
        global profit
        profit += drink_cost
        return True
    else:
        print("Sorry that's not enough money. Money refunded.")
        return False
    

def make_coffee(drink_name, order_ingredients):
    """Deduct the required ingredients from the resources."""
    for item in order_ingredients:
        resources[item] -= order_ingredients[item]
    print(f"Here is your {drink_name} . Enjoy!")


while button:
    wish=input("What do you like to oder Sir . (espresso/latte/cappuccino)")
    if wish=='off':
        button=False
    elif wish=='report':
        print(f"""Water: {resources['water']}ml
Milk: {resources['milk']}ml
Coffee: {resources['coffee']}g
Money: ${profit}""")
    else:
        drink=MENU[wish]
        print(drink)
        res_ing(drink['ingredients']) 
        payment = process_coins()
        if is_transaction_successful(payment, drink["cost"]):
            make_coffee(wish, drink["ingredients"])

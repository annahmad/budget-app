# Budget App
 
A Python budget tracker that manages spending across categories and visualizes expenses as a bar chart. Built as part of the [freeCodeCamp Python Certification]((https://www.freecodecamp.org/learn/python-v9)).
 
## Features
 
- Create spending categories (e.g. Food, Clothing, Auto)
- Deposit and withdraw funds per category
- Transfer funds between categories
- Check balances and prevent overdrafts
- Print a formatted ledger per category
- Generate a percentage-based bar chart across categories
## Usage
 
```python
from budget import Category, create_spend_chart
 
food = Category('Food')
food.deposit(1000, 'initial deposit')
food.withdraw(10.15, 'groceries')
food.withdraw(15.89, 'restaurant and more food for dessert')
 
clothing = Category('Clothing')
food.transfer(50, clothing)
 
auto = Category('Auto')
auto.deposit(1000, 'initial deposit')
auto.withdraw(15, 'gas')
 
print(food)
print(create_spend_chart([food, clothing, auto]))
```
 
## Example Output
 
```
*************Food*************
initial deposit        1000.00
groceries               -10.15
restaurant and more foo -15.89
Transfer to Clothing    -50.00
Total: 923.96
```
 
```
Percentage spent by category
100|          
 90|          
 80|          
 70|          
 60| o        
 50| o        
 40| o        
 30| o        
 20| o  o     
 10| o  o  o  
  0| o  o  o  
    ----------
     F  C  A  
     o  l  u  
     o  o  t  
     d  t  o  
        h     
        i     
        n     
        g     
```
 
## Class & Function Reference
 
### `Category(name)`
| Method | Description |
|---|---|
| `deposit(amount, description='')` | Adds funds to the category |
| `withdraw(amount, description='')` | Removes funds; returns `True` if successful |
| `get_balance()` | Returns current balance |
| `transfer(amount, category)` | Transfers funds to another category; returns `True` if successful |
| `check_funds(amount)` | Returns `False` if amount exceeds balance |
 
### `create_spend_chart(categories)`
Takes a list of `Category` instances and returns a bar chart string showing the percentage spent per category (withdrawals only, rounded down to the nearest 10).
 
## Project Structure
 
```
budget-app/
├── budget.py       # Category class and create_spend_chart function
├── main.py         # Example usage
└── README.md
```
 
## Running the Tests
 
```bash
python main.py
```
## Author
Ann Ahmad
 
## License
 
This project is for educational purposes as part of the freeCodeCamp curriculum.
 

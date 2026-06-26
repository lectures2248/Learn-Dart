In this task, you will create a simple console-based shopping system using Dart basics. 
The program should allow the user to view products, add products to a cart, calculate the total bill,apply discount, and exit the program.
You must use lists, maps, loops, conditions, switch statements, and basic control statements.

TASK DETAIL:

Create Product List
Create a list of at least 5 products.
Each product must contain: id,name,price
This list will represent all available items in the store.

Display Products
Show all products using a loop.
Display them in this format:
id - name - price


Create Cart
Create an empty list called cart.
This list will store selected products.


Menu System
Create a menu using a while loop.

The menu must show these options:
	Show Products
	Add To Cart
	Show Cart
	Show Total Bill
	Exit


Add To Cart
When user selects Add To Cart:
Ask for product id.
If product exists, add it to cart.
If the same product is added again, increase its quantity instead of adding duplicate.
Each cart item must contain:
	id
	name
	price
	quantity


Show Cart
Display all cart items with:
name
price
quantity

Calculate Total
Calculate the total amount using a loop.
Do not hardcode the total.
Use the formula:
price × quantity


Discount System
Apply discount based on total:
	If total > 1000 → 10% discount
	If total > 500 → 5% discount
	Otherwise → no discount

Show:
	Subtotal
	Discount amount
	Final total

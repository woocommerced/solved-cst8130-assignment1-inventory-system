Download Link: https://assignmentchef.com/product/solved-cst8130-assignment1-inventory-system
<br>
In this assignment, you will write efficient Java code to create a basic inventory system using a dynamically allocated data structure to hold the inventory and another dynamically allocated array to hold a record of transactions.  Your code must  handle every single possible condition.   The inventory system will contain two types of items – items that are purchased from a supplier; and items that our company manufactures which contains items purchased.  Our program will run with a basic menu that allows the user to add an item to inventory, display to the screen the inventory, buy an item (ie add to the quantity of that item) and sell an item (ie subtract from the quantity of that item).  You are allowed to buy and sell any item (purchased or manufactured) in the inventory.

<strong><em>Note</em></strong> – You are welcome to add to the assignment, but I am trying to bound the scope of the assignment so that you do not have too much work.   Assume that all <strong><em>string </em></strong>field input does not contain spaces which will make the input easier.

<strong><em>Hint:</em></strong>  This assignment needs to be tackled in a     structured fashion in order for it to be finished quickly.   Do not write more than 20-30 lines of code at a time without running your program.   I will be discussing structured strategies  in class.   Enjoy!!

The following is a suggestion of how to structure the code (you may make changes, but they must follow Object-Oriented Principles as discussed in class)

<strong><em>Item </em></strong>class:

<ul>

 <li>Has (private) data members:

  <ul>

   <li><strong><em>itemCode (int)</em></strong></li>

   <li><strong><em>itemName (String)</em></strong></li>

   <li><strong><em>itemQuantityInStock (int)</em></strong></li>

   <li><strong><em>itemPrice (float)</em></strong></li>

  </ul></li>

 <li>Has methods:

  <ul>

   <li>Constructors</li>

   <li><strong><em>boolean addItem (Scanner) –</em></strong>reads from the Scanner object passed in  and fills the data member fields with valid data; method  returns true if successfully reads in all fields else returns false</li>

   <li><strong><em>String toString()</em></strong></li>

   <li><strong><em>boolean updateItem (int amount) – </em></strong>updates the quantity field by amount (note amount could be positive or negative) – returns true if successful else false  Note- <strong><em>quantityInStock</em></strong> field can never be less than 0.</li>

   <li><strong><em>boolean isEqual (Item) </em></strong>returns true if the<strong><em> itemCode</em></strong> of the object being acted on and the<strong><em> item</em></strong> object parameter are the same value</li>

   <li><strong><em>boolean inputCode(Scanner) –</em></strong> reads a valid itemCode from the Scanner object and returns true/false if successful</li>

  </ul></li>

</ul>

<strong><em>NOTE:   </em></strong>because the data members are all private in the<strong><em> Item</em></strong> class, <strong>only this class can access them</strong>.  So If you need to do something to any of these data members, you must write a method to do it (for example – methods <strong><em> isEqual</em></strong>,   <strong><em>inputCode</em></strong>)

<strong><em>PurchasedItem</em></strong> class – extended from<strong><em> Item</em></strong> class

<ul>

 <li>has (private) data members:

  <ul>

   <li><strong><em>supplierName (String)</em></strong></li>

  </ul></li>

 <li>has methods:

  <ul>

   <li>constructor</li>

   <li><strong><em>boolean addItem (Scanner)</em></strong> – per Item class</li>

   <li><strong><em>String toString()</em></strong></li>

  </ul></li>

</ul>

<strong><em>ManufacturedItem</em></strong> class – extended from<strong><em> Item</em></strong> class

<ul>

 <li>has (private) data members:

  <ul>

   <li><strong><em>itemsUsed – array of 10 ints (</em></strong>to contain the <strong><em>itemCodes</em></strong>)</li>

   <li><strong><em>numItemsUsed (int)</em></strong></li>

  </ul></li>

 <li>has methods:

  <ul>

   <li>constructor</li>

   <li><strong><em>boolean addItem (Scanner)</em></strong> – per Item class</li>

   <li><strong><em>String toString()</em></strong></li>

  </ul></li>

</ul>

<strong><em>Inventory </em></strong>class

<ul>

 <li>Has (private) data members:

  <ul>

   <li><strong><em>inventory</em></strong> (dynamically allocated array of <strong><em>Item</em></strong> objects)</li>

   <li><strong><em>numItems (</em></strong>int)</li>

  </ul></li>

 <li>Has methods:

  <ul>

   <li>Constructors</li>

   <li><strong><em>boolean addItem (Scanner)</em></strong> – adds an item to the <strong><em>inventory</em></strong> array – (uses polymorphism to call<strong><em> addItem </em></strong>method  in the correct derived <strong><em>Item</em></strong> class for input of the fields of the Item)</li>

   <li><strong><em>String toString()</em></strong></li>

   <li><strong><em>int alreadyExists (Item) – </em></strong>returns the index of an<strong><em> Item</em></strong> in the <strong><em>inventory</em></strong> array with the same<strong><em> itemCode</em></strong> as the<strong><em> Item</em></strong> object in the parameter list, else returns -1</li>

   <li><strong><em>boolean updateQuantity (Scanner, boolean) – </em></strong>reads in an <strong><em>itemCode</em></strong> to update and <strong><em>quantity</em></strong> to update by and updates that item by the input quantity in the <strong><em>inventory </em></strong> The <strong><em>boolean</em></strong> parameter is used to denote whether buying operation or selling operation is occurring.  Method returns true/false on whether update was successful or not</li>

  </ul></li>

</ul>

<strong><em>Assign1Main </em></strong>class

<ul>

 <li>Has methods:

  <ul>

   <li><strong><em>main </em></strong>– menu processing</li>

  </ul></li>

</ul>

<strong><em>Sample Output: green is user input</em></strong>

Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

1

Do you wish to add a purchased item (enter P/p) or manufactured (enter anything else)? p

Enter the code for the item: 123

Enter the name for the item: paper

Enter the quantity for the item: 100

Enter the price of the item: 0.50

Enter the name of the supplier:

Staples




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

1

Do you wish to add a purchased item (enter P/p) or manufactured (enter anything else)? P

Enter the code for the item: ab

Invalid code…please enter integer greater than 0

Enter the code for the item: 234

Enter the name for the item: nails

Enter the quantity for the item: a

Invalid quantity…please enter integer greater than 0

Enter the quantity for the item: -5

Invalid quantity…please enter integer greater than 0

Enter the quantity for the item: 5000

Enter the price of the item: a

Invalid price…please enter float greater than 0

Enter the price of the item: -2

Invalid price…please enter float greater than 0

Enter the price of the item: 2.00

Enter the name of the supplier:

ABConstruction




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

1

Do you wish to add a purchased item (enter P/p) or manufactured (enter anything else)? m

Enter the code for the item: 444

Enter the name for the item: Instructions

Enter the quantity for the item: 25

Enter the price of the item: 1.00

Enter up to 10 codes used in this item (-1 to quit):

123

-1




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

2

Inventory:

Item: 123 paper 100 price: $0.5 Supplier: Staples

Item: 234 nails 5000 price: $2.0 Supplier: ABConstruction

Item: 444 Instructions 25 price: $1.0 Codes used: 123,







Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

3

Enter valid item code: 456

Code not found in inventory…

Error…could not buy item




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

3

Enter valid item code: 444

Enter valid quantity : 5




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

4

Enter valid item code: 123

Enter valid quantity : 50000

Error… could not sell item




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

2

Inventory:

Item: 123 paper 100 price: $0.5 Supplier: Staples

Item: 234 nails 5000 price: $2.0 Supplier: ABConstruction

Item: 444 Instructions 30 price: $1.0 Codes used: 123,







Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

4

Enter valid item code: 123

Enter valid quantity : 9




Enter 1 to add an item to inventory

2 to display current inventory

3 buy some of an item

4 sell some of an item

5 to quit

2

Inventory:

Item: 123 paper 91 price: $0.5 Supplier: Staples

Item: 234 nails 5000 price: $2.0 Supplier: ABConstruction

Item: 444 Instructions 30 price: $1.0 Codes used: 123,

<strong><em> </em></strong>

<strong><em> </em></strong>

<strong><em>Submission:</em></strong>

You must submit to the assignment link in Blackboard by the due date and time a zip file (named  LastnameFirstNameAssign1) containing:

<ul>

 <li>all source code – ie .java files (Note – I will re-compile and run your program….so all code must be available to me and MUST not be in a package) with headers.  (Headers should contain  name, student number, assignment number, date, purpose of class, brief description of each data member and method</li>

 <li>Your test plan in either .docx or .xls format</li>

</ul>




Failure to provide any of the above will have an effect on your grade for this assignment.   Marking guide will be published shortly.






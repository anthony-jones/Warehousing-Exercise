# Warehousing-Exercise

Part 1: Product warehouse, step 1
The class Warehouse handles the functions related to the amount of a product. Now we want a product name for the product and a way to handle the name. Let's write ProductWarehouse as a subclass of Warehouse! First, we'll just create a private object variable for the product name, a constructor, and a getter for the name field:

   - public ProductWarehouse(String productName, double capacity) - Creates an empty product warehouse. The name of the product and the capacity of the warehouse are provided as parameters.
   
   - public String getName() - Returns the name of the product.
   
Part 2: Product warehouse, step 2
As we can see from the previous example, the toString() inherited by the ProductWarehouse object doesn't (obviously!) know anything about the product name. Something must be done! Let's also add a setter for the product name while we're at it:

   - public void setName(String newName) - sets a new name for the product.

   - public String toString() - Returns the state of the object represented as a string like this Juice: balance = 64.5, space left 123.5
   
Part 3: Change History, step 1
Sometimes it might be useful to know how the inventory of a product changes over time: Is the inventory often low? Are we usually at the limit? Are the changes in inventory big or small? Etc. Thus we should give the ProductWarehouse class the ability to remember the changes in the amount of a product. Let's begin by creating a tool that aids in the desired functionality. The tool should be implemented by encapsulating the ArrayList<Double> object.

   - public ChangeHistory() creates an empty ChangeHistory object.

   - public void add(double status) adds provided status as the latest amount to remember in the change history.
   
   - public void clear() empties the history.
   
   - public String toString() returns the string representation of the change history. The string representation provided by the ArrayList class is sufficient.

Part 4: Change History, step 2
Build on the ChangeHistory class by adding analysis methods:

   - public double maxValue() returns the largest value in the change history. If the history is empty, the method should return zero.
   
   - public double minValue() returns the smallest value in the change history. If the history is empty, the method should return zero.
   
   - public double average() returns the average of the values in the change history. If the history is empty, the method should return zero.
   
Part 5: Product warehouse with history, step 1
Implement ProductWarehouseWithHistory as a subclass of ProductWarehouse. In addition to all the previous features this new warehouse also provides services related to the change history of the warehouse inventory. The history is managed using the ChangeHistory object. Public constructors and methods:

   - public ProductWarehouseWithHistory(String productName, double capacity, double initialBalance) creates a product warehouse. The product name, capacity, and initial balance are provided as parameters. Set the initial balance as the initial balance of the warehouse, as well as the first value of the change history.

   - public String history() returns the product history like this [0.0, 119.2, 21.2]. Use the string representation of the ChangeHistory object as is.

Part 6: Product warehouse with history, step 2
Expand the class with the following methods:

   - public void addToWarehouse(double amount) works just like the method in the Warehouse class, but we also record the changed state to the history.

   - public double takeFromWarehouse(double amount) works just like the method in the Warehouse class, but we also record the changed state to the history.

Part 7: Product warehouse with history, step 3
Expand the class with the method:

   - public void printAnalysis(), which prints history related information for the product in the way presented in the example.
   
    Product: Juice
    History: [1000.0, 988.7, 989.7]
    Largest amount of product: 1000.0
    Smallest amount of product: 988.7
    Average: 992.8
    
         - From MOOC.fi



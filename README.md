# Model.java

## Update Functions

### addEmployee

Summary:
  addEmployee takes 4 string values (employeeName, employeeID, manager, and password)
  and inserts a new employee into the employees db, and returns whether or not it
  inserted correctly.

Parameters:
  String employeeName,
  String employeeID, - Should be an int passed as a string.
  String manager, - Should be a boolean passed as a string.
  String password - Should be a hash for the password, passed as a string.

Return Value:
  boolean - returns whether or not it successfully inserted.

### removeEmployee

Summary:
  removeEmployee takes the primary_key, verifies manager status, and deletes the
  specified entry.

Parameters:
  String product_name

Returns:
  boolean whether or not it deleted.

### addProduct

Summary:
  addProduct takes 2 string values (product_name, price) and inserts a new product
  with those values.

Parameters:
  String product_name,
  String price - Double converted to string

Returns:
  boolean whether or not it inserted correctly

### removeProduct

Summary:
  removeProduct takes the primary_key, verifies manager status, and deletes the
  specified entry.

Parameters:
  String primary_key

Returns:
  boolean whether or not it deleted.

### AddItem

Summary:
  addItem takes 3 strings (itemName, supplierPricePerUnit, isAddable) compiles
  two lists: 1 for the items db, and one for the inventory db. Then inserts
  into both the items table, and inventory table, and lastly checks to make
  sure both were inserted to properly, and throws an InvalidInputException
  if not.

Parameters:
  String itemName,
  String supplierPricePerUnit, - Double as String.
  String isAddable - Boolean as String.

Returns:
  boolean whether or not it inserted correctly

### removeItem

Summary:
  Removes specified item from inventory and items tables.

Parameters:
  String itemName

Returns:
  boolean whether or not it is removed properly

## Query Functions

### getLowStockItems

getLowStockItems returns a table of all the low stock items with their column names.

### getSalesReport

Summary:
  Queries order history, orders_products, and products to return the itemized sales report (Product Name, Units Sold, Total Revenue) within the given start and end dates.

Parameters:
  String startDate (format: YYYY-MM-DD)
  String endDate (format: YYYY-MM-DD)

Returns:
  ArrayList<ArrayList<String>> containing headers and sales data rows ordered by units sold descending.

## SQL Helper Functions

If these functions are not used outside of model, private them.

### selectFromDB

SelectFromDB returns a ResultSet containing the values associated with the table,
conditions, and column, passed to it.

SelectFromDB(String table) Returns a ResultSet with all the entries in that table.

SelectFromDB(String table, String conditions) returns a ResultSet with all the values
in that table that satisfy the conditions.

SelectFromDB(String table, String conditions, String column) returns the ResultSet
containing the column values in the table that satisfy the conditions.

### insertEntry

insertEntry adds an entry to the table with the passed values, the returns a boolean
indicating whether or not it succeeded in doing so.

### updateEntry

updateEntry takes the table, primary_key_column, primary_key, field_column, and
the new updated value, then updates that value within the table that matches those
parameters.

TODO: Will be overloading the function to automatically handle primary_key_column
so that it is not necessary to do so in future.

### deleteEntry

deleteEntry takes the table, primary_key_column, and primary_key and deletes the
entry associated with that primary key.


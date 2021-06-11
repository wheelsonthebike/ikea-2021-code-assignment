# IKEA 2021 Interview code assignment

### Code Assignment

#### Intro
This assignment will be used as a discussion during a technical interview.
The primary values for the code we look for are: simplicity, readability, maintainability, testability. It should be easy to scan the code, and rather quickly understand what it’s doing. Pay attention to naming.
 
You may choose any coding language, and we look forward to discussing your choice.

#### The Task

The assignment is to implement a warehouse software. This software should hold articles, and the articles should contain an identification number, a name and available stock. It should be possible to load articles into the software from a file, see the attached inventory.json.

The warehouse software should also have products, products are made of different articles. Products should have a name, price and a list of articles of which they are made from with a quantity. The products should also be loaded from a file, see the attached products.json. 
 
The warehouse should have at least the following functionality;
* Get all products and quantity of each that is an available with the current inventory
* Remove(Sell) a product and update the inventory accordingly


## Notes

* This problem is called 'Bill of Materials'. It's a bit hard to search for, so use 'Inventory Management System' keywords too.
  * https://en.wikipedia.org/wiki/Bill_of_materials
  * https://github.com/inventree/InvenTree

* Blog about the BOM structure: https://www.vertabelo.com/blog/identifying-the-bill-of-materials-bom-structure-in-databases/
* "Available stock" either means 
  * "potential stock", as in "given 4 legs, 1 table top, and 1 chair seat then expect `chair.stock = 1` *and* `table.stock = 1`
  * "actual stock", as in "given 4 legs, 1 table top, and 1 chair seat then expect 
    * `chair.stock = 1` *and* `table.stock = 0`, 
    * **or** vice versa. 
    
    ("actual stock" seems much more vague to me (there's no indication of the priority in which stock should be assembled and marked as such), and not what the assignment is requesting, but this is what the technical interviewer wanted).
  
* This is an open ended assignment with different interpretations, but the technical interviewer will judge the assignment based on their interpretation of the assignment.
* Recursive SQL queries are a potential solution, see 
  * mysql '`WITH` (Common Table Expressions)' https://dev.mysql.com/doc/refman/8.0/en/with.html 
  * MariaDB https://mariadb.com/kb/en/with/

### Gotchas

* Products have no IDs, only a name (workaround: use the name)
* An Article and Product could have the same name (workaround: use a composite key, combining a string (e.g. `article`, `product`) and the name/id)


#### Other implementations

* Kafka Streams 
  * https://sleeplessinslc.blogspot.com/2018/02/inventory-microservice-example-with.html 
  * https://github.com/sanjayvacharya/sleeplessinslc/tree/master/inventory-example

* Another applicant's project https://github.com/hilios/warehouse


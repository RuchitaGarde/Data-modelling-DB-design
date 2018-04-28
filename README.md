# Data modelling and Database Design

### This repository contains documentation, media files and SQL files required to fully design and implement an SQL database.
How to navigate this repository?
- Please find below the problem statement and description of the requirements, as one might get from a client.
- The `DB-design` folder contains a diagrammatic representation of the designed database, alongwith assumptions and constraints.
- Then go to the `DB-implementation` folder where you will find SQL queries to implement your designed database.
- Lastly, the `SQL-views` folder contains some complex SQL queries written to query the db, and answer some questions about the data.

## To design a Supply Chain Information System (CSIP)
#### Requirements:
- The CSIP is composed of suppliers, manufacturers, shippers and end-customers. Items of different kinds are being moved in the supply chain. Manufacturers use Items of materials to manufacture Items of products for customers. Suppliers supply Items of materials to manufacturers; they also supply Items directly to Customers. Shippers (e.g., UPS, Fedex etc) move items from one business entity (supplier, manufacturer, customer etc) to another.
- Items have a unique id and weight. Every business entity (suppliers, manufacturers, customers etc.) is identified by its id, and has a shipping location (to be used by Shippers for shipping orders), address, phone, web location, and contact information.
- Every product item (e.g., a table) has a number of associated material/part items in certain quantities necessary to produce 1 unit of the product item. For example, a table product item requires 1 table top item, 4 leg items and 8 screw items.
- Suppliers supply Items using price per unit, which may vary among different Suppliers for the same Item.
- Suppliers apply a volume computed on the dollar amount based on price per unit.
- Volume discount is described by a percentage deducted for an amount higher than a predetermined amount.
- Manufacturers produce product Items; this production has an associated setUpCost and product cost per unit.
- Manufacturers may offer volume discounts to customers applied the same way suppliers apply volume discounts.
- Shippers price shipping services per <source, destination> pairs, where sources and destinations are shipping locations of business entities.
- The pricing of each shipper is based on the total weight of shipment from source to destination, using price per lb, and a volume discount applied on the total dollar amount.
- Customers have demand quantity for certain Items.
- The orders are recorded separately for shipping, manufacturing and supply.
- Shipping orders capture information about a shipper, sender, and recipient (who are business entities) and the Item being shipped, and record the quantity of the Item shipped.
- Manufacturing orders capture information about a manufacturer, a manufactured Item and the ordered quantity.
- Supply orders capture information about a supplier, Item and the quantity supplied.
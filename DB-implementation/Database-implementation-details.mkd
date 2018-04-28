## Database implementation details

This folder contains SQL queries required to create the tables and insert some preliminary test data into them. Please find below the description of the schema. the underlined words are the primary key for the tables. Please note that the primary key can be composite.

1. items (item, unitWeight)
	- item has unitWeight
2. busEntities(entity, shipLoc, address, phone, web, contact)
	- Every business entity has shipLoc (to be used by shipping companies), address, phone, web link, and contact info
3. billOfMaterials(prodItem, matItem, QtyMatPerItem)
	- To produce 1 unit of prodItem, manufacturers need QtyPerItem units of matItems
4. supplierDiscounts(supplier, amt1, disc1, amt2, disc2)
	- Supplier gives discount disc1 for purchase amount between amt1 and amt2, and disc2 for purchase amount above amt2. Note that discounts will be expressed as fractions rather then percentage, e.g., 0.15 rather than 15 (%).
5. supplyUnitPricing(supplier, item, ppu)
	- Item supplied by sup has ppu (price per unit)
6. manufDiscounts(manuf, amt1, disc1)
	- Manufacturer manuf gives discount disc1 for manufacturing cost in excess of amt1 of the base cost, which is computed according to manufUnitPricing table 	- see below.
7. manufUnitPricing(manuf, prodItem, setUpCost, prodCostPerUnit)
	- For manufacturing of prodItem by manuf, the manufacturer base cost is computed as setUpCost plus the prodPricePerUnit times the qty of the produced prodItem
8. shippingPricing(shipper, fromLoc, toLoc, minPackagePrice, pricePerLb, amt1, disc1, amt2, disc2)
	- The shipping cost for a shipper from fromLoc to toLoc is computed as follows: determine the total weight of all items shipped from fromLoc to toLoc (by all senders at fromLoc to all recipients at toLoc) base cost: is computed based on total weight of shipment and pricePerLb discounted cost: then for amount between amt1 and amt 2, disc 1 is applied; and to the amount above amt2, disc2 is applied total cost: the maximum of inPackagePrice and the discounted price
9. customerDemand(customer, item, qty)
	- The demand by customer is qty units of item; note that items may come from any combination of manufacturers and/or suppliers.
10. supplyOrders(item, supplier, qty)
	- Qty units of item were ordered from supplier
11. manufOrders(item, manuf, qty)
	- Qty units of item were ordered to be produced by manuf
12. shipOrders(item, shipper, sender, recipient, qty)
	- Qty units of item were requested to be shipped by shipper from sender to recipient
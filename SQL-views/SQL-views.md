## Generating SQL views.

#### Based on the database created, the following data views were generated using SQL. Please refer a SQL-views.sql file in the folder for the code.

1. **shippedVsCustDemand**: For every (customer, item) in customerDemand, compute the total qty of this item shipped to this customer, along with the demand qty. Note that the items may come from manufacturers and/or suppliers
2. **totalManufItems**: For every item in manufOrders, compute the total qty of this (product) item produced
3. **matsUsedVsShipped**: For every manuf in manufOrders, and matItem used by this manuf (i.e., manuf ordered a prodItem that requires a matItem according to billOfMaterials) compute:
	- the total qty of this matItem necessary to produce all the ordered (product) items by this manuf,
	- the total qty of this matItem shipped (by all shippers) to this manufacturer
4. **producedVsShipped**: For every (item, manuf) in manufOrders compute the total qty of this item shipped out from this manuf (by all shippers to any recipient), along with the total qty of this item produced by this manufacturer (in manufOrders).
5. **suppliedVsShipped**: For every (item, supplier) in supplyOrders compute the total qty of this item shipped from this supplier (by all shippers to any recipient), along with the ordered qty of this item.
6. **perSupplierCost**: For each supplier in supplierDiscounts, compute the total cost of items supplied by this supplier (according to supplyOrders).
7. **perManufCost**: For each manufacturer in manufDiscounts, compute the total manufacturing cost of all items produced by this manufacturer (according to manufOrders).
8. **perShipperCost**: For each shipper in shippingPricing, compute the total shipping cost of this shipper.
9. **totalCostBreakdown**: Compute the total supply cost, manufacturing cost, shipping cost, and the overall cost.

#### Based on the views created, the data was queried to answer the following questions. Please refer a sql-queries.sql file in the folder for the code.

1. Find customers, whose demand is NOT satisfied, i.e., are not shipped all the quantities of items.
2. Find suppliers, whose orders (in supplyOrders table) are not fully shipped out.
3. Find manufacturers who do NOT have enough materials to produce ordered product quantities, i.e., not enough materials were shipped to them.
4. Find manufacturers whose orders are not fully shipped out.
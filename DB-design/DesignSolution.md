## Design solution with Entity-Relationship (ER) diagram.

### Assumptions (which can later be clarified by meeting with the Business Analyst):
- Participation constraints: Supplier_discount_price, Manuf_discount_price and Shipping_pricing entities must have an Entity existing in the Business_entity entity (“atleast one” constraint)
- Weak entities: Supplier_discount_price, Manuf_discount_price and Shipping_pricing entities are weak entities as they cannot exist without the Business_entity entity. Thus, the relations connecting them are also weak.
- The attribute Entity_type belonging to the entity Business_entity is a set-valued attribute having values: Customer, manufacturer, supplier and shipper.
- Each Entity_id has to be unique irrespective of its entity_type. Two entities of different entity_types  must NOT have the same entity_id.

### Constraints not covered in the ERD:
- The relations dedicated to specific entities, eg: supply_orders, manuf_orders, cust_orders etc must contain the business entity specific to its type. For eg, the relation ManufUnitPricing must have an entity_id as its primary key which belongs to the type “manufacturer”. This ERD fails to make this consideration, and it completely rests on the data entry operator to take care of this.
- In entity Ship_orders, the shipper, sender and recipient attributes have to belong to three different entities belonging to the correct type. This ERD does not take care of this.

<img src="https://github.com/RuchitaGarde/Data-modelling-DB-design/blob/master/DB-design/Entity-Relationship-diagram.jpg" width="1000px" height="500px"/>



## Exercise 1

Go to the website: https://wolt.com/en/dnk/copenhagen/restaurants

- Identify the different views that is required to put food in the basket.
- Identify: 
  - What are the entities?
  - What data are fetched together?
  - What data should be stored together? 
  - Model the data from the Wolt views as BSON objects (same as JSON) that represents one or more entities.
- E.G:

```json
{
    "_id": ObjectId("5fa123456789abcdef012345"),
    "name": "Sunset Grill",
    "cuisine": ["American", "BBQ"],
    "location": {
        "address": "123 Sunset Blvd",
        "city": "Los Angeles",
        "state": "CA",
        "zip": "90028"
    },
    "contact": {
        "phone": "+1-310-555-0199"
    },
    "menu": [
        {
            "dish_id": ObjectId("5fa123456789abcdef012346"),
            "name": "BBQ Ribs",
            "price": 18.50
        },
        {
            "dish_id": ObjectId("5fa123456789abcdef012347"),
            "name": "Grilled Salmon",
            "price": 22.00
        }
    ],
    "average_rating": 4.3,
    "review_ids": [
        ObjectId("5fa123456789abcdef012348"),
        ObjectId("5fa123456789abcdef012349")
    ]
}
```



## Exercise 2

https://www.mongodb.com/docs/manual/crud/



Insert the following collection in a database and a collection called inventory:

```json
db.inventory.insertMany( [
   { item: "canvas", qty: 100, size: { h: 28, w: 35.5, uom: "cm" }, status: "A" },
   { item: "journal", qty: 25, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
   { item: "mat", qty: 85, size: { h: 27.9, w: 35.5, uom: "cm" }, status: "A" },
   { item: "mousepad", qty: 25, size: { h: 19, w: 22.85, uom: "cm" }, status: "P" },
   { item: "notebook", qty: 50, size: { h: 8.5, w: 11, uom: "in" }, status: "P" },
   { item: "paper", qty: 100, size: { h: 8.5, w: 11, uom: "in" }, status: "D" },
   { item: "planner", qty: 75, size: { h: 22.85, w: 30, uom: "cm" }, status: "D" },
   { item: "postcard", qty: 45, size: { h: 10, w: 15.25, uom: "cm" }, status: "A" },
   { item: "sketchbook", qty: 80, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
   { item: "sketch pad", qty: 95, size: { h: 22.85, w: 30.5, uom: "cm" }, status: "A" }
] );
```



**A) ** 

Add a new document to the `inventory` collection with the following details:

- Item: Sticker
- Qty: 150
- Size
  - h = 5
  - w = 5
  - uom = cm
  - Status = A

**B)** 

Retrieve all items that have a status of "A"

**C)** 

Increase the qunaittiy of the item journal by 10 of it's current qunatity

**D)**

Retrieve all items with a height greater than 20

**E)**

Change the status of all items with a qty less than 50 to "D" (Discontinued)

**F)**

Retrieve all items with a width between 20 and 30 and uom of CM

**Advanced (Optional)**

**G)**

Update the `qty` and `status` fields for items that meet the following conditions:

- If the item’s height (`h`) is greater than 25 *and* the width (`w`) is greater than 30, increase `qty` by 20.
- For items that meet this size requirement *and* have a `status` of `"A"`, additionally update the `status` to `"S"` (special).
- Hint: Use the [$inc](https://www.mongodb.com/docs/upcoming/reference/operator/update/inc/) and [set](https://www.mongodb.com/docs/manual/reference/operator/update/set/) operators



## Exercise 3

In the same dataset as before

**A)**

Group the documents by `status` and calculate the total quantity (`qty`) for each status type.



**B)**

Calculate the average `qty`of all items in the inventory



**C)**

Group the documents by `size.uom` (unit of measure), and calculate the total quantity (`qty`) for each unit of measure (e.g., "cm" and "in").



**D)**

Group the documents by `status` and calculate the total quantity (`qty`) for items where the `status` is either "A" or "P".



**E) Advanced (Optional)**

Group the documents by `item` and calculate both the average and total quantity for each item type.
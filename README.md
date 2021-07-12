# Grofers_Delivery_Assignment

## Problem statement
You are running an e-commerce business like Grofers. You have received n orders for the day. You have to deliver these n orders to the customers in 4 delivery slots ( 6-9, 9-13,16-19,19-23 hours). There are delivery partners who deliver these orders. Each delivery partner has their own vehicle and each vehicle has a carrying capacity i.e total weight of the orders which is dependent on the vehicle type (bike, scooter, or truck).

Each slot can take orders with an overall max weight of 100 kg. There are no trucks available in the morning slot (6-9 hours) and there are no scooters and bikes available in the evening slot (19-23 hours). All vehicle types are available for the other two slots (9-13,16-19 hours). You can’t order more than 1 truck, 3 bikes, 2 scooters a day. Also, the vehicles’ capacity should be used optimally.

## Constraints
Bike capacity - 30 kg per trip

Scooter capacity - 50 kg per trip

Truck capacity - 100 kg per trip

slot capacity - 100 Kg

maximum 4 slots allowed

## Approach

- Assume that Total sum of order weight can'not be more than total vehicle capity if so, We cannot deliver that order.

- Vehicles are sorted in non-increasing order of their max capacity

Repeat below until all orders are assigned

  - A vehicle is chosen based on the total weight of orders in the given slot
  - Choose a vehicle large enough to accommodate all orders in that given slot.
  - If no vehicle can accommodate all orders, choose the largest vehicle available
  - If the chosen vehicle cannot accommodate the largest remaining order, We cannot deliver orders
  - Orders are filled in chosen vehicle
  - Repeat until we cannot add any item in the remaining space of current vehicle
  - Choose the largest order that can be filled in the remaining space (using modified binary search)

## Tech Stack
- Python
- Flask
- MongoDB
- Deployed on Heroku

## Steps to run and execute the program
1. Clone the repository
2. Install all the required modules using pip command.
3. Install MongoDB (https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)
4. In db.py file change the CARRIER_PATH and PARTNER_PATH according to json file location.
5. Run the progam.
6. API could be accessed at http://127.0.0.1:5000/

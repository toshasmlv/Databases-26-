Solution Description

The ERD represents an International Airport Database designed to manage information about airports, airlines, flights, passengers, bookings, boarding passes, baggage, baggage checks, security checks, and booking changes.

The main entities in the system are Airport, Airline, Flight, Passenger, Booking, Booking Change, Boarding Pass, Baggage, Baggage Check, and Security Check. Each entity has a primary key that uniquely identifies each record. Foreign keys are used to establish relationships between related entities. The database also uses unique keys for attributes such as airline codes, passport numbers, and booking IDs where uniqueness is required.

An Airline can operate multiple Flights, while each flight is operated by one airline. A Flight is associated with one departure airport and one arrival airport. The Airport entity is therefore connected to Flight through two different relationships: departs_from and arrives_at. These relationships represent the two different roles that an airport can have in relation to a flight.

A Passenger can make multiple Bookings, and each booking belongs to one passenger. Similarly, a Flight can have multiple bookings. Therefore, the relationship between Passenger and Flight is many-to-many, and it is resolved through the Booking entity. The Booking entity contains foreign keys referencing both Passenger and Flight, as well as information such as booking status, booking platform, ticket price, creation date, and update date.

A Booking can have multiple Booking Changes, which allows the system to keep a record of changes made to a booking. A booking can also have zero or one Boarding Pass, since a boarding pass may not yet have been issued. The unique constraint on booking_id in the Boarding Pass entity ensures that one booking cannot have multiple boarding passes in this model.

Passengers can register Baggage as part of their booking. Baggage is optional, so one booking can have zero or multiple baggage items. Each baggage item contains information such as its weight and is associated with a booking. Each registered baggage item must undergo a Baggage Check, which is represented as a one-to-one relationship between Baggage and Baggage Check. The Baggage Check entity stores the checking result as well as the related baggage, booking, and passenger information.

The system also stores Security Check information for passengers. A passenger can be associated with security check records, and each security check contains its own ID, the passenger ID, the check result, and timestamps.

Overall, the ERD shows how the main airport entities are connected and specifies the primary keys, foreign keys, unique keys, relationships, cardinalities, and optional or mandatory participation of the entities. The cardinalities were selected based on the business requirements described in the tas

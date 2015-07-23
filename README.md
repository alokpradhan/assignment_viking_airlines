# assignmnent_viking_analytics

-- 1. Get a list of all users in California

User.find_by_sql(
SELECT *
FROM users JOIN states ON users.state_id = states.id \
WHERE states.name = 'California')

-- 2. Get a list of all airports in Minnesota

Airport.find_by_sql(
SELECT *
FROM airports JOIN states ON airports.state_id = states.id \
WHERE states.name = 'Minnesota')

-- 3. Get a list of all payment methods used on itineraries by the user with email address "heidenreich_kara@kunde.net"

Itinerary.find_by_sql(
SELECT payment_method
FROM itineraries JOIN users ON users.id = itineraries.user_id \
WHERE email = 'heidenreich_kara@kunde.net' )

-- 4. Get a list of prices of all flights whose origins are in Kochfurt Probably International Airport.

Flight.find_by_sql(
SELECT flights.price
FROM flights JOIN airports ON flights.origin_id = airports.id \
WHERE airports.long_name = 'Kochfurt Probably International Airport')


-- 5. Find a list of all Airport names and codes which connect to the airport coded LYT.


-- 6. Get a list of all airports visited by user Dannie D'Amore after January 1, 2015. (Hint, see if you can get a list of all ticket IDs first).
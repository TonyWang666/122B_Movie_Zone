# Welcome to Movie Zone

## What is Movie Zone?
Movie Zone is a a commercial movie website. The customers are able to browse, search, do davance searching, manage shopping cart and pay with the paypal.

## Back-End and Front-End
The Back-End and Front-End is written by Java and JavaScript. 60+ RESTful APIs are built to send and receive the request and responses between the Back-End and the Front-End. API-Gateway is built to handle all the API resquests and then send the requests to the correct server in order to protect the system and increase the efficiency of fetching or updating among the 4 databases. Besides, the Back-End is using multi-threading to increase the throughput of the Back-End.

## Database
There are 4 databases total, using the Microservices technique while it is capable of handling requests for 100,000+ data entries. They are user databse, cart database, movie database, shopping_cart database and API_Gateway database. 


### API_Gateway database:
This database will store and handle all the API requests from the client(Front-End). Once an API request is sent to the Back-End, it will be saved into this database with a given transaction-ID. After API_Gateway will send the request to the corresponding servers and then wait for response. After getting an response from one of the servers(User/ShoppingCart/Movie), API-Gateway will use the transactionID from the response to find the source of the corresponding request and send the data to it.

### User Database:
This database contains all the information of all users. More importantly, the user are given rank from 1 to 5 to limit the user's access ability to some actions. For example, the user(admin) with highest rank(rank = 1) is able to do all the actions, including updating movie databas, changing users' rank. Instead, the user(normal customer) with lowest rank are only to browse and buy movies. The user(vip) with rank 4 are able to view the hidden movie. The user with rank 2 and 3 are able to update movie database but not changing users' rank. The other database will check user's rank with user database before allowing the further action.

### Shopping_Cart Database:
This database is to save the movies in the shopping cart for all the users. Therefore, each cart is binded with one user. It contains the information of the movie(movieId), user(userId) and the quantity of each movies. User are able to manage their shopping carts easily through it, such as adding quantity, delete movie, clear shopping cart, payment.

### Movie Database:
This databases contains all the information of the movies. The other databases are able to get all the movie realted information with the movieId.

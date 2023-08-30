# Airborne
This is a base file of Airborne. Airborne is a flight management and booking system. There are four services implemented including Management service, API Gateway, Booking Service, Notification Service which are implemeneted in MVC.

## Services
Airborne is divided into four services:
- [Management service](https://github.com/abhay2002-pro/Airborne) - CRUD operations for Airplane, Airport, City and Flight.
- [API Gateway](https://github.com/abhay2002-pro/Airborne_API_Gateway) - Authentication,  Authorisation, Reverse Proxy, Rate limiter and Sign In and Sign Up for User
- [Booking Service](https://github.com/abhay2002-pro/Airborne_booking_service) - Booking Flights and Payment
- [Notification Service](https://github.com/abhay2002-pro/Airborne_notification_service) - Notification via mail

## Non Functional Requirements

- We can expect more fight searches than bookings
- The system needs to be reliable in terms of booking
- We expect to have 1,00,000 total users ,
- 1,00,000 bookings might come up in a quarter.
- In one day we can get 100 bookings.
- System shoud be able to make sure that we dont change the prices whe the booking payment is going on.
- System should be able to auto scale itself for atleast 3x more traffic.

## System Diagram
![Screenshot 2023-08-30 152043](https://github.com/abhay2002-pro/Airborne/assets/76939279/49e63db7-6d46-4cf8-b75e-1628c317f1e5)

### Folder structure followed in every service
`src` -> Inside the src folder all the actual source code regarding the service resides.

Lets take a look inside the `src` folder

 - `config` -> In this folder, anything and everything regarding any configurations or setup of a libraray or module will be done. For example: setting up `dotenv` so that we can use the environment variables in a cleaner fashion, this is done in the `server-config.js`. One more example can be to setup your logging library that can help you to prepare meeaningful logs, comfiguration for this library should also be done here.

 - `routes` -> In this folder, we register a route and the corresponding middlewares and controllers to it.

 - `middlewares` -> They are just going to intercept the incoming requests where we can write our validators, authenticators.

 - `controllers`  - They are kind of the last middlewares as post them you can call your business layer to execute the business logic. In controllers we just receive the incoming requests and data, and then pass it to the business layer, and once business layer returns an ouput, we structure the API response object in controllers and send the output.

 - `repositories` -> This folder contains all the logic using which we interact the DB by writing quesries, all the raw queries or ORM queries will go here.

 - `services` -> contains the business logic and interacts with repositories for data from the database.

 - `utils` -> contains helper methods, error classes etc.

## Major Tech

Airborne uses a number of open source projects to work properly. Major ones are listed here:
- [node.js] - evented I/O for the backend
- [Express] - fast node.js network app framework
- [sequelize](https://github.com/sequelize) - ORM for sql databases
- [RabbitMQ](https://www.rabbitmq.com/) - setting up message queue
- [Docker](https://www.docker.com/) - containersation tool

## License

MIT

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>

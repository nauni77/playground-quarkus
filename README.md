# project : playground-quarkus

This project is created to try the basic features for develop a real application. In my opinion you must know at least the following things:

* Logging - which logging frameworks are supported (SLF4J, Log4j, etc.)? How configure the logging
  * how should a log line be formated
  * what should be logged (path with reference to DEBUG, INFO, etc.)
  * where to log this information (STDOUT, File, Log-Server)?
* Configure application with properties (Injection of the values)
  * Howto use profiles (dev, test, prod, etc.)
* Testing Applications
  * automatically start the server for the test - like SpringBoot will do? Or need to start `devQuarkus` and run the tests against this instance?
  * how does the injection of properties works inside/ with Tests? For plain Unit-Testing ...
* Beans (Stateless, Stateful, Singleton)
  * create bean
  * use/ address bean
  * lifecycle
* Injection of Objects/ Beans?
* How to access a SQL database?
* REST-Service
* REST-Client - can use Feign?

Very interesting is also how to create releases and even how to put theses releases into a container.

* create a layered release and upload to a repository (incl. tagging, etc.)
* create binary release and upload to a repository (incl. tagging, etc.)
* create a layered container (first add all dependencies and latest the own project)
* create a container from the binary

# creating a operator with quarkus

This is a very interesting topic.

# manipulating the keycloak server

This is very interesting for the project "CIAM".
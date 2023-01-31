# 🚕 Taxi service app

### 📄 Project description:

Simple proof of concept web app that supports user authentication and have basic CRUD operations. Created using in-build java functionality (java.sql and javax.servlets) without using any additional frameworks.

### 💻 Current project functionality:

- register as driver
- login as driver
- add a driver
- display all drivers
- delete a driver
- add a manufacturer
- display all manufactures
- delete a manufacturer
- add a car
- display all cars
- delete a car
- add a driver to a car
- display all cars for currently login driver

### 📂 Project has the following structure:

#### java/

- controller -all http servlets classes
- dao -classes responsible for crud operations with db
- exception -custom exceptions
- lib -custom implementation of field injector, that is used in this project
- model -Car, Driver and Manufacturer model classes
- service -classes that are responsible for connecting dao with controllers
- util -util class needed to connect to db
- web.filter -basic authentication filter

#### resources/
- init_db.sql -file containing sql queries needed to create db tables for this project

#### wepapp/
- WEB-INF -jsp pages and corresponding css files
- web.xml -contains mapping for servlets and corresponding endpoints

#### other
- Pom.xml -contains maven build configs and dependencies
- Procfile and system.properties are needed for proper heroku deployment

### 🔨 Technologies used

Java 11, MySql, Tomcat, Maven

### 🔮 How to use app

This app is hosted on herokuapp.com. You can access it by following this [link](https://enigmatic-dawn-28719.herokuapp.com/login).
To log in you can use existing user (login: _bob_, password: _1234_) or create a new one for yourself.

Alternatively you can run this app by yourself (**requires Intellij and jdk 11 already installed**). First you will need to pull this project from github. You can do this by running below command in terminal:
```
git clone git@github.com:dmytro-mk/taxi-service.git
```
##### To run app locally on your pc you will need to install tomcat 9.0.50 and mysql 8.0. After that:

1. Execute queries from init_db.sql to create needed tables.
2. Replace username, password and url in util/ConnectionUtil with your own.
3. Create new run configuration tomcat_local (requires intellij premium).
4. Delete heroke related plugin from pom.xml.
5. Run ```mvn package``` command in termanal.
6. Click debug configuration.
7. Enjoy :smiley:

##### If you want to host your version of this app on heroku:
1. Create remote MySql db (use init_db.sql to create tables).
2. Replace username, password and url in util/ConnectionUtil with your own.
3. Create heroku account and run following commands:
```
git add .
git commit -m "first commit"
heroku login
heroku create
git push heroku master
heroku open
```
4. Enjoy :smiley:


















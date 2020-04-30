# Idea
## Corona Terminator

# What it does
COVID-19 Terminator aims at providing immediate support for the users, including self-checking symptoms, spotting highly contaminated regions, designing the safest route from home to the grocery stores/workplaces, checking the availability of goods and wait time of the grocery stores, offering educational information and recommendations about how to take the proper prevention methods, and building a platform to connect users lack of PPE and essential goods with organizations who can donate during the coronavirus outbreak.

# How we built it
Learn about the Value of this App a) “We answer all your concerns on COVID-19.” b) “We help you find the safest zone.” c) “We help you connect with people in your community.”
Sign up a) Username: email address/phone number b) Password c) Optional: home address, emergency contact d) Terms and conditions
Check Symptoms a) Why is self-checking important? - List out the reasons - List out 2 options of self-check: chatbot/checklist b) Self-check questionnaire c) Final score and suggestions d) Chatbot - connect to physicians
Share Travel History - Connect to Google Maps/Apple Maps a) Screen whether a person is at high risk or low risk based on the places he/she has been to in the past 14 days. b) Locations with high risk will also be spotted on the maps.
Check Locations & Design Routes - Connect to Google Maps/Apple Maps a) Type the store you want to go to b) The heat map will show you the areas with high/low risk c) Estimate the wait time and check the availability of certain goods in the store
Useful Information & Recommendations a) Proper use of PPE b) DIY mask/goggles tutorial c) An online community to share the resources (like PPE, essentials, etc.) – using the algorithm to match users in need and organization who can provide In the 2nd phase, we are going to use Python Django, Java Springboot to build our application.

## Steps to Setup the Spring Boot Back end app (evliion-app-server)

1. **Clone the application**

	```bash
	git clone git@github.com:swachev/swachev-api.git
	cd evliion-app-server
	```

2. **Create MySQL database**

	```bash
	create database evliion_app
	```

3. **Change MySQL username and password as per your MySQL installation**

	+ open `src/main/resources/application.properties` file.

	+ change `spring.datasource.username` and `spring.datasource.password` properties as per your mysql installation

4. **Run the app**

	You can run the spring boot app by typing the following command -

	```bash
	mvn spring-boot:run
	```

	The server will start on port 8080.

	You can also package the application in the form of a `jar` file and then run it like so -

	```bash
	mvn package
	java -jar target/ev-0.0.1-SNAPSHOT.jar
	```
5. **Default Roles**
	
	The spring boot app uses role based authorization powered by spring security. To add the default roles in the database, I have added the following sql queries in `src/main/resources/data.sql` file. Spring boot will automatically execute this script on startup -

	```sql
	INSERT IGNORE INTO roles(name) VALUES('ROLE_USER');
	INSERT IGNORE INTO roles(name) VALUES('ROLE_ADMIN');
	```

	Any new user who signs up to the app is assigned the `ROLE_USER` by default.

## Steps to setup the React Front end app (evliion-app-client)

Clone the application

```bash
git clone git@github.com:swachev/marketplace.git
cd evliion-app-server
```

First go to the `evliion-app-client` folder -

```bash
cd evliion-app-client
```

Then type the following command to install the dependencies and start the application -

```bash
npm install && npm start
```

The front-end server will start on port `3000`.



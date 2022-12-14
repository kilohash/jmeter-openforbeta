# jmeter-openforbeta

1. Define load scenarios:

JMeter is set to run with 500 users and a ramp-up time of 120 seconds.

During the test run the following steps are performed:

1. Login
Assertion: verify that Response Code equals 200 for the Main sample only (since one of the subsamples returns the Response Code 302 (Moved Temporarily))

2. Edit Profile
Assertion: verify that the following sequence appeared in the response: “<p class="good">Your account has been successfully updated.</p>”

3. View Profile
Assertion:  verify that Response Code equals 200 for the Main sample only

4. Send message
Assertion: verify that server response is “success”

5. Browse website (list of 42)
Assertion:  verify that Response Code equals 200 for the Main sample only

6. Add to Favorites
In order to add a website to Favorites list of an authenticated user the following parameters are passed in GET request:
action=add
id=${siteId}

Assertion: verify that Response Code equals 200 for the Main sample only

7. Delete from Favorites
In order to add a website to Favorites list of an authenticated user the following parameters are passed in GET request:
action=delete
id=${siteId}

Assertion: verify that Response Code equals 200 for the Main sample only

8. Vote yes
To vote up for the site the following parameter are passed in POST request to vote_yes.php:
id=${siteId}
nb=0

Assertion: verify that server response is “1”




9. Vote no
To vote up for the site the following parameter are passed in POST request to vote_no.php:
id=${siteId}
nb=1

Assertion: verify that server response is “2”

10. Logout
Assertion: verify that Response Code equals 200 for the Main sample only

2. Create load testing suite using Apache JMeter.

In order to run the created suite Maven environment variables has to be defined beforehand. From the project working directory (openforbeta.com) invoke the command line and enter the following command mvn verify or mvn jmeter:gui (to run with JMeter GUI).

3. Analyze the results and create the report (you are free to choose the form and content).

The table below was generated by Summary Report Listener.

...

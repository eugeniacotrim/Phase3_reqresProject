# simplilearnPhase3Project2

I have performed API testing on the base URL (https://reqres.in/) using Postman, RestAssured, and performed load testing, stress testing and spike testing on the API with the help of JMeter.

*POSTMAN
-GET request
I performed the GET request for a single user (https://reqres.in/api/users/2) with a Data Driven Collection. For that, I created collection variables (U_ID and U_Name) for which the values were defined through a set of expected variables (E_ID and E_Name) given in an external .csv file. This was defined in the Pre-request script.
The Test asserted that the status code of the request would return as 200, and that the collection values of the IDs and Names were matching with the expected values from the external file. All 3 tests passed for the IDs from <7> through <12>.

-POST request
I created 2 lines of input data to be passed on the post request.
Under the Test, I asserted that the status code of the request would return as 201, and that the response for <name> and <job> were matching with the request body.
All 3 tests passed.


*RESTASSURED
I created a log4j2.xml file to set the logging properties, such as appenders, pattern layout and the root tags. The log was set to be saved to a subfolder of the project named log, and the file named as app.log.

-GET request
This request was performed for a single user (https://reqres.in/api/users/2) using the given/when/then approach. The response was validated through assertions using Hamcrest matchers.

-POST request
This request was performed using the given/when/then approach. The response was validated through assertions using Hamcrest matchers.

-Log4j2 logging
A filter class was created to define the conditions for the logging parameters. An if condition was used to search the requests and responses and perform the logger.info method when applicable.

A filter method was added to the given() statement on each of the API requests, to call the logging functionality when applicable.

JMETER
-Load testing
A total of 3 tests were performed on load testing for the GET request, and another total of 3 tests were performed on load testing for the POST request. Each of these tests were performed in triplicate.
The first test was defined for #ThreadCount = 5 users and Ramp-Up time = 2 seconds;  the second test for #ThreadCount = 25 users and Ramp-Up time = 2 seconds; and the third one for #ThreadCount = 50 users and Ramp-Up time = 2 seconds.

-Stress testing
This test was performed in triplicate for #ThreadCount = 1000 users and Ramp-Up time = 5 seconds.

-Spike testing
This test was performed in triplicate for #ThreadCount = 2000 users and Ramp-Up time = 1 second.

Finally, A Summary report was produced where the error percentage can be analyzed for all the different testings.

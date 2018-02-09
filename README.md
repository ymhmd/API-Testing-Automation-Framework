# WebservicesTestZona

Used tools and frameworks
---------------------------------------
1. Rest-Assured
2. TestNg
3. Jxl to extract test data from Excel files

Projects
---------
1. WebservicesTestZona was used to test RESTful webservices of My Vodafone Greece Mobile Application
2. Now, WebservicesTestZona is used to test RESTful webservices of Mi Vodafone Spain Mobile Application

Main features
----------------------------
1. Hybrid framework to test automation Webservices. It is keyword-driven and data-driven framework. So, you can separate testing data in Excel sheet with predefined schema and using some keywords inside Excel sheet you can validate the returned response body and headers.
2. Supports REST API testing. I am working now to make the framework support the SOAP Webservices.
3. All classes and methods are implemented in Java with Maven repository to include all dependencies needed. REST-Assured is used to offer a friendly DSL (Domain specific Languages) that describes a connection to an HTTP endpoint and expected results.
4. Utilizes the capabilities of TestNG such as Data provider annotation to separate test data in external file and flexible test suites configuration and management. Also, TestNG generates 2 types of reports, HTML and XML reports. The HTML reports are very descriptive with good statistics and the Junit XML reports that can be integrated with Jenkins after test execution to have summary status of each deployment.
5. To use the framework, NO need to have any coding skills. ZERO line of needed. Each test cases can be represented as a row or some rows (if the test case consists of some correlated steps) in the relevant Excel sheet. All you need is to know what is your scope in testing and just add the test data in the Excel sheet with the predefined schema then create the TestNG runner xml file that points to test data. For example:
The predefined schema in that format:
[URL], [Request method: GET, POST, ...], [Headers keys], [Headers values], [Body(if needed)], [Expected status code], [Assertions]
6. REST-Assured Java API is to test REST webservices and has no direct support for SOAP webservices. However, REST-Assured can test SOAP webservices by adding xml request in the body and execute POST HTTP request. Now, I am working to add this feature to the framework.
7. The framework validates the returned status code, response body and headers. It can validate each field data type and value. If the returned response includes object of arraylist, the framework can validate its size using the keyword ".size()"
8. Can be integrated into DevOps environment to accelerate the delivery process. After each Jenkins deployment, test cases can be executed automatically and the generated XML reports can be passed to Jira to log Defects/Tests automatically. Some configurations needed in Jenkins side.
9. Solves the complexity of testing correlated APIs as any test step can use data (body value, header or cookie) received in the previous steps. For example and more details you can check Sample_2 sheet in Excel test data. For more details about Keywords used and test data schema, you can have a look at the test data samples.


New Features in version 2.0
-----------------------------
1. The returned cookies can be validated using keyword `cookie:` 
2. The returned cookies can be reused in the next steps using keyword `#prev_cookies_res[STEP]:PREV_COOKIE_KEY`
* NB: For more details how to use cookie keywords, Please refer to TestDataSample.xls > sample_04


New Features in version 3.0
-----------------------------
1. Vesion 3.0 supports BDD test cases: The first column called "Description" should have simple plain text illustrating what each step does.
2. 

Demo
----------
1. In the command line execute : `java -jar APITool_1.0.jar Runners\Sample2_Runner.xml`.
2. It generates test-output directory which contains the TestNG HTML and XML reports.

Future Work
------------
1. To integrate with Jira to log bugs automatically as soon as having bugs 
2. To support Business Driven Develpment (BDD) test cases
3. Simple GUI should be used to execute test suites instead of using command line

![alt text](screenshots/BDD.png "Description goes here")

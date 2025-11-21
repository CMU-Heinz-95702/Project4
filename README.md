# Project 4
- **Assigned: Friday October 31**
- **Task 1 Due: Friday November 7, 11:59pm**
- **Task 2 Due: Friday November 21, 11:59pm**

Assigned by Marty Barrett
Please direct questions to Piazza. Only email a TA or Marty if absolutely needed.

**Three status notes:**
 - Like the other projects, you must do this project alone.
 - The updated information on how to deploy Task 2 to the cloud and how to submit Task 2 for grading has been added below.
  - The images have been re-labled to reflect using GitHub Codespaces.

## Project Topics: Mobile to Cloud application

This project has 2 tasks:
- Task 1 involves researching, selecting, and demonstrating that you can successfully use the technologies you plan to use in your project.
- Task 2 will build on _Lab 3 - Creating Containers and Deploying to the Cloud_ and _Lab 8 - Android Lab_. You will design and build a distributed application consisting of a mobile application, a web service that communicates with a RESTful web service in the cloud, and a dashboard that displays logging and simple analytics about your application.

## Task 1: Demonstrate Project Feasibility

The goal of this task is to develop an idea for your application and to demonstrate the feasibility of using a 3rd party API and a database-as-a-service.

**Start by researching and choosing a 3rd party API to use in Task 2.**  Be sure to read Task 2 carefully to see how you will use the API, and to understand what APIs cannot be used - see the "Banned APIs" section.

To complete Task 1, you should satisfy the following requirements:

**1. Fetch data from a 3rd party API**  
a. Create a simple Java application that will make a request to the API that you'll use in Task 2 and receive structured JSON or XML data.  
b. Extract some piece of data and print it to the console.

**2. Write and read data to MongoDB Atlas**  
a. Read the Database section below about creating and using mongoDB with Atlas.   
b. Create a mongoDB database on Atlas.  
c. Create (another) simple Java application that will:  
- Prompt the user for a string.
- Write the string as part of a document to the mongoDB database.  
- Read all documents currently stored in the database.  
- Print all strings contained in these documents to the console.  

**3. Create a document that contains:**  
a. Your name and Andrew ID  
b. The name of the API (e.g. Flickr - but not actually Flickr: see the list of sites and topics on the Banned API's list below).
c. The URL of the API documentation (e.g. https://www.flickr.com/services/api/).  
d. A short description (1-3 sentences) of what your mobile application will do with the information from the API (e.g. My mobile app will prompt the user for a string and then search Flickr using their API to display an interesting picture tagged with that string.)  
e. A screenshot of the console output from section 1b.  
f. A screenshot of the console output from section 2c.

**4.	Submit your document (only) to Canvas as a pdf by the Task 1 deadline.**  
Do not submit your code. It will be integrated into Task 2.

**Grading:**  
- Task 1 complete and submitted on time: Bonus 5 points
- Task 2 does not use the API demonstrated in Task 1:  Penalty 10 points

If you don’t submit Task 1 on time, you get no bonus points.

If you have not committed to an API by submitting Task 1 by the deadline, you can’t be penalized for not using that API.  

If you do not use the API submitted in Task 1 on time, you still get the 5 bonus points, but are penalized 10 points, resulting in a net penalty of 5 points.

Grace days **cannot** be used for Task 1.  Grace days, if you have some remaining, can be used for Tasks 2.

**Banned APIs:** There are a number of APIs that have been used too often and are no longer interesting in this class.  Therefore, you **cannot** use any of the following:
- anything related to Project 1 (flags, simple country data), but you can do something with more detailed country demographics or trends.
- Agify.io
- Alpha Vantage
- any beer API (choose by type, etc.)
- Dog.ceo
- Eventful
- Flickr (we've have already done that)
- Google Maps (unless you also use a 2nd API to get info to put on the map)
- IsEvenAPI.xyz
- Last.fm
- Merriam-Webster Dictionary
- mixed drinks (how-to's, catalogs)
- NASA Astronomy Picture of the Day
-	NYTimes APIs: specifically top stories, news wires, popular, and books.
-	OpenMovieDatabase
- Pokemon API
- Spoonacular
- Spotify
- Any weather API
-	Yahoo Finance API
-	Yelp
- YouTube
- Zomato

## Task 2: Distributed Application and Dashboard
### The Distributed Application

Your application must be of your own creative design. (We will use software similarity detection software to identify those who do not.) It can be simple, but should fetch information from a 3rd party source and do something of at least marginal value.  For example, we have assigned projects that generate hash values, implement clickers, or manage a blockchain.  Your application should do something similarly simple but useful (but you should not reuse our ideas or the ideas of your peers!).

The following is a diagram of the components for your this part of your application:
![Task 2 Diagram](docs/Project4-Diagram-Partial.png)

Your web service should be deployed to the cloud and provide a simple RESTful API similar to those you have developed in prior projects. You do NOT have to implement all HTTP methods, only those that make sense for your application. Your web service must fetch information from some 3rd party API.  In Project 1 you experimented with screen scraping, therefore that is not allowed in this project.  Rather, you must find an API that provides data via XML or JSON.  It is easy and can be fun to search for APIs; the [GitHub Public APIs repository](https://github.com/public-apis/public-apis) is a good place to start. But again, see the Banned API's list below.

**See the Banned APIs section.** Do not use any of the banned API's. Some students forget this if they change API's after Task 1 (and don't get the bonus, either).

**Use APIs that require authentication with caution.** Many APIs will require you get a key (e.g. Flickr, which you used in the Android lab, required an API key).  This is ok. But APIs that require authentication via OAuth or other schemes add a lot of work. Experiment ahead of time, but if you are brave, go ahead…

**Do not use APIs that require a fee.** The TA's are poorly paid.

**Be sure your API is from a reputable source.  Your API still needs to be available when the TAs go to grade your project.** Make sure you do not base your project on an API built by a 7th grade student…

Users will access your application via a native Android application. **You do not need to have a browser-based interface for your application** (only for the Dashboard). The Android application should communicate with your web service deployed to the cloud. Your web service is where the business logic for your application should be implemented (including fetching information from the 3rd party API).

In detail, your distributed application should satisfy the following requirements:

### Distributed Application Requirements
##### 1.	Implement a native Android application
a.	Has at least three different kinds of Views in your Layout (TextView, EditText, ImageView, or anything that extends android.view.View). **In order to figure out if something is a View, find its API.  If it extends android.view.View then it is a View.**  
b.	Requires input from the user  
c.	Makes an HTTP request (using an appropriate HTTP method) to your web service  
d.	Receives and parses an XML or JSON formatted reply from your web service  
e.	Displays new information to the user  
f.	Is repeatable (I.e. the user can repeatedly reuse the application without restarting it.)

##### 2.	Implement a web service
a.	Implement a simple (can be a single path) API.  
b.	Receives an HTTP request from the native Android application  
c.	Executes business logic appropriate to your application.  This includes fetching XML or JSON information from some 3rd party API and processing the response.
- -10 if you use a banned API
- -10 if screen scrape instead of fetching XML or JSON via a published API

d.	Replies to the Android application with an XML or JSON formatted response. The schema of the response can be of your own design.  
-	-5 if more information is returned to the Android app that is needed, forcing the mobile app to do more computing than is necessary. The web service should select and pass on only the information that the mobile app needs.

**Use Servlets, not JAX-RS, for your web services.** Students have had issues deploying web applications built with JAX-RS to Docker Containers and a solution has not yet been found.

**Updated guidelines for deploying your web service to GitHub Codespaces will be provided before the Task 1 deadline.**

##### 3. Handle error conditions
Your application should test for and handle gracefully:
 - Invalid mobile app input
 - Invalid server-side input (regardless of mobile app input validation)
 - Mobile app network failure, unable to reach server
 - Third-party API unavailable
 - Third-party API invalid data

### Web Service Logging and Analysis Dashboard

Now enhance your web service to add logging, analysis, and reporting capabilities. In other words, create a web-based dashboard to your web service that will display information about how your service is being used. This will be web-page interface designed for laptop or desktop browser, not for mobile. In order to display logging and analytical data, you will have to first store it somewhere.  For this task, you are required to store your data in a noSQL database, or more specifically a MongoDB, database hosted in the cloud.

The following is a diagram showing the dashboard components of your distributed application:
![Task 2 Diagram](docs/Project4-Diagram-Full.png)

#### Logging data
Your web service should keep track (i.e. log) data regarding its use.  You can decide what information would be useful to track for your web application, but you should track at least 6 pieces of information that would be useful for including in a dashboard for your application. It should include information about the request from the mobile phone, information about the request and reply to the 3rd party API, and information about the reply to the mobile phone.  Information can include such parameters as what kind of model of phone has made the request, parameters included in the request specific to your application, timestamps for when requests are received, requests sent to the 3rd party API, and the data sent in the reply back to the phone. Be creative about what is useful for your application.

You should NOT log data from interaction with the operations dashboard, only from the mobile phone.

#### Storing logs
You should store your log data persistently so that it is available across restarts of the application. For this task you should use MongoDB to store your log data. MongoDB is a noSQL database that is easy to use.  By incorporating it into your web service you will gain experience using a noSQL database, and experience doing CRUD operations programmatically from a Java program to a database.

See the MongoDB section below for more information on MongoDB, how to set it up, and hints on how to connect to it.

#### The Dashboard
The purpose of logging data to the database is to be able to create an operations dashboard for your web service.  This dashboard should be web page interface for use from a desktop or laptop browser (not a mobile device).

The dashboard should display two types of data:
3.1. Operations analytics – display at least 3 interesting operations analytics from your web service.  You should choose analytics that are relevant to your specific web service. Examples for InterestingPicture might be top 10 picture search terms, average Flickr search latency, or the top 5 Android phone models making requests.
3.2. Logs – display the data logs being stored for each mobile phone user interaction with your web service. The display of each log entry can be simply formatted and should be easily readable. **(Three points will be lost if they are displayed as JSON or XML.)**  

3.3. You will likely find HTML tables useful for formatting tabular information on a web page.  And there are plenty of examples of embedding data in tables with JSP on the web.   No frameworks are necessary for this, just < 20 lines of JSP (i.e. mixed HTML and Java). You may use a client-side framework if you like (e.g. Twitter Bootstrap). Don't just use the json or xml format, use a table.

In detail, your dashboard should satisfy the additional requirements:

### Web Service Logging and Analysis Dashboard Requirements
##### 4.	Log useful information
At least 6 pieces of information is logged for each request/reply with the mobile phone.  It should include information about the request from the mobile phone, information about the request and reply to the 3rd party API, and information about the reply to the mobile phone. (You should NOT log data from interactions from the operations dashboard.)
#### 5.	Store the log information in a database
The web service can connect, store, and retrieve information from a MongoDB database in the cloud.
#### 6.	Display operations analytics and full logs on a web-based dashboard
a. A unique URL addresses a web interface dashboard for the web service.  
b. The dashboard displays at least 3 interesting operations analytics.  
c. The dashboard displays **formatted** full logs.

#### 7. Deploy the web service to GitHub Codespaces  

In order to deploy your web application to the cloud using Github Cloudspaces, first make sure you have the basics working.  

a. Accept the Github Classroom Assignment that you have been given the URL for.  You will find a repository with:
 - A `.devcontainer.json` and a `Dockerfile` which define how to create a Docker container, build a suitable software stack, and deploy the ROOT.war web application.
 - A ROOT.war file which, like in Lab 3, contains a web application that will deployed in the container.  This is a simple "Hello World!" application.
 - An identical copy of this `README.md`  

b. Click the green <> Code dropdown button, select the Codespaces tab, then click on "Create codespace on master".

c. Once the Codespace is running, the Terminal tab will show that Catalina (the Servlet container) is running.  You should also see a "1" next to the Ports tab.  Click on the Ports tab and you should see that port 8080 has been made available.  (Note: If you do not see the server running from the get-go (start of codespace), and do not see any port(8080) active, be sure to try running the 'build-and-run.sh' bash file by running `./build-and-run.sh' on the terminal. Confirm that the file is located and the root level of the project directory, and on the same level as your Dockerfile)

d. Mouse over the Local address item of the port 8080 line and you will find three icons.  The leftmost is to copy the URL of your deployed application, the middle one (a globe) is to launch that URL in a browser.  Clicking on the globe is a quick way to test your web service in a browswer.  The copy is useful to use the URL in your Android App.

e. Click on the globe to confirm that the Hello World servlet is working.

f. By default, the URL in (d) requires you to be authenticated with Github. To test in a browser, that is fine, but when accessing your web service from your Android app, the Android app will not be authenticated.  Therefore you must make the port visibility "Public".  To do this, right or control click on the word "Private" in the Visibility column, and change Port Visibility to "Public".  You will now be able to access the web service from your Android App or from an unauthenticated browser.

g. Copy the URL and paste into an Incognito Chrome window to confirm that the Hello World web app can be reached without authentication.

h. To deploy your own web service, create a ROOT.war like you did in Lab 3, upload or push the ROOT.war to your repository, and create a Codespace as has just been described.

### Writeup

Because each student's distributed application will be different, you are responsible for making it clear to the TAs how you have met these requirements, and it is in your best interest to do so. You will lose points if you don't make it clear how you have met the requirements. Therefore, you must create a document describing how you have met each of the requirements (1 – 7) above (you do **not** need to document _3. Handle error conditions_.) Your writeup will guide the TAs in grading your application.  See the provided example ([Project4Task1Writeup.pdf](https://github.com/CMU-Heinz-95702/Project4/blob/master/docs/Project4-WriteUp.pdf)) for the content and style of this document (but note that you're not using Heroku, you'll be using Codespaces instead).

Alternatively, instead of a document, you may submit a narrated screencast that includes the same information that would be in the writeup.

### Demos
The TAs will identify exemplar projects that are unique in some way and nominate them to be demonstrated in class.  Those who do so get a small prize!

### Questions
If you have a question, please post them to the course Piazza, ask a TA, or direct to Marty.

### Submission Summary

When you are done, you will have one web service, one Android app, and one writeup pdf document.

Be sure you meet the Documentation standards given in the first week of class, especially including an Author comment with your name and AndrewID in each source code file. Failing to include your name and AndrewID in each source file will result in losing 5 points.

All the following files should be left in your Github assignment repository.

a. ROOT.war - This is your working web service.  
b. Your IntelliJ IDEA project zip file.  Create this by using “File->Export To Zip File…”. You must export in this way and NOT just zip the project folders.  Your zip file should be clearly named to indicate this is your web service.  
c. Your Android Studio project folder as a single zip file.  Your zip file should be clearly named to indicate this is your android app.  
d. Your writeup document as a .pdf.  This file should be clearly named to indicate it is your writeup file.

**You should only push / upload your writeup file as the very last step of submitting your project.  Once a TA sees that you have a writeup file, they will consider your project submitted and available for grading.**

You do **not** have to submit anything to Canvas for Project 4 Task 1.

---
### MongoDB
The main MongoDB web site is https://www.mongodb.com. The site provides documentation, a [downloadable version of the database manager application](https://www.mongodb.com/try/download/enterprise) (*mongod*) that you can run on your laptop, and MongoDB drivers for many languages, including Java.

*Mongod* is the MongoDB database server. It listens by default on port 27017. Requests and responses with the database are made via a MongoDB protocol.

*Mongo* (without the DB) is a command line shell application for interacting with a MongoDB database.  It is useful for doing simple operations on the database such as finding all the current contents or deleting them.

Because your web service will be running in the cloud, you can’t run your database on your laptop.  Rather, you should use a MongoDB-as-a-Service to host your database in the cloud. Atlas (https://www.mongodb.com/atlas/database) is required because it has a free level of service that is adequate for your project.  

**Please read carefully…**
This project will challenge you to do a lot of research to understand enough MongoDB to create a simple database, add a collection, and insert, update, and find documents in that collection.  This is very much like you will need to do regularly in industry. Code examples are provided on the MongoDB site, and elsewhere. **As long as you include comments as to their source, you can use them in your code.**  If we search for a snippet of your code find it somewhere, and you have not attributed it to where you found it, that will be cheating and reason for receiving a failing grade in the course.  Of course, the bulk of your code that is unique to your application should be your own and not copied from anywhere.

#### Setting up MongoDB Atlas
In this project, you are going to us nosql-database-as-a-service with MongoDB Atlas. Information about MongoDB can be found here: https://www.mongodb.com/what-is-mongodb

Getting started:
1. Create your account. Go to https://www.mongodb.com/atlas/database and create your own free account.
2. Answer the "Tell us a few things..." questions however you like, but include Java as the preferred language.
3. Choose to create a FREE shared cluster.
4. Accept the default settings and Create Cluster.
5. In the Security Quickstart:
 - *How would you like to authenticate your connection?*  
 Authenticate using Username and Password.  Create a MongoDB user name and password (**only use letters and numbers to save yourself some hassle for encoding it later**) -  don't forget these.  The cluster takes a few minutes to provision, so be patient.
 - *Where would you like to connect from?*  
 Choose My Local Environment, add the IP address `0.0.0.0/0`, and Add Entry. What this IP address means is that your DB will be open to the world, which is required for the grading purposes. (You can check this later on the Security tab, IP Whitelist. If it doesn't have that IP address, click on Edit.)
 - Then Finish and Close.
 - If a popup window invites you to set up "Termination Protection", just "Close".  (You don't need that for this project.)
6. Connect to the cluster.  
  a) Click on the Connect button.  
  b) Select the MongoDB Drivers option, then choose the Driver as Java, use version 4.3 or later.  
  c) Select Include full driver code example. Click Copy to copy that code stub. For now, save that code in a file; later, you'll edit and paste into your application to connect to your MongoDB instance, but don't forget to replace your <password> with your database user‘s credentials (Note that when entering your password, any special characters are URL encoded; that's why a simple password is better here).  
  d) You will access this database in two ways:  
	**For Task 1:** Create a simple Java application to demonstrate reading and writing to the database as described in Task 1 above.  
  **For Task 2:** In your Web Service Logging and Analysis Dashboard

The sample code in the Quick Start guide shows how to access the database. You can access this cloud-based MongoDB database from your laptop as well as from your web service in the cloud.

Info about the MongoDB Java driver and sample code can be found here:  
https://docs.mongodb.com/drivers/java/sync/v4.3/quick-start/

The Usage Examples contains several code examples:
https://www.mongodb.com/docs/drivers/java/sync/current/usage-examples/


You can easily add the MongoDB Java Drivers to a project with Maven by adding these dependency lines to your pom.xml file inside the dependencies section (only add the first and last lines of the following if there isn't already a dependencies section):
```
<dependencies>
   <dependency>
      <groupId>org.mongodb</groupId>
      <artifactId>mongodb-driver-sync</artifactId>
      <version>4.3.4</version>
   </dependency>
</dependencies>
```
If you're seeing red in the pom.xml file, the, open the Maven panel in IntelliJ (it usually hides on the right margin) and click the "Reload all maven dependencies" button in the top-left corner (the circular arrows icon). Any red-highlighted Java code problems can be handled in the usual way by hovering your cursor over the code.

#### Hints for connecting to MongoDB Atlas

Use a password that uses only letters and numbers so you don't have to deal with encoding it.

The MongoDB connection string that Atlas provides is of the form:
```
mongodb+srv://USER:PASSWD@CLUSTER.mongodb.net/mydb?retryWrites=true&w=majority
```

But the `+srv` will not work with a number of DNS servers, and TLS and an authentication mechanism needs to be defined. Therefore:
1. On the MongoDB Atlas dashboard where you created the database, click on *Database* and then on *Cluster* link (it might be Cluster0, Cluster1, etc.)  Under the REGION label you will see three shard servers listed.  Click on the name of each to display the full server URL, and copy the full URL.  It will look something like  
 `cluster0-shard-00-02.cbkkm.mongodb.net:27017`
2. Find the URLs for the other two shard servers and copy them also.
3. Create your own connection string:  
`mongodb://USER:PASSWD@SERVER1,SERVER2,SERVER3/test?w=majority&retryWrites=true&tls=true&authMechanism=SCRAM-SHA-1`  
Be sure to substitute your own values for USER, PASSWD, and SERVER1-3

The resulting connection string should look similar to:  
```
mongodb://myuser:mysecretpassword@cluster0-shard-00-02.cbkkm.mongodb.net:27017,cluster0-shard-00-01.cbkkm.mongodb.net:27017,cluster0-shard-00-00.cbkkm.mongodb.net:27017/myFirstDatabase?w=majority&retryWrites=true&tls=true&authMechanism=SCRAM-SHA-1


```

When running your application, you will see the following warning:  
`WARNING: SLF4J not found on the classpath.  Logging is disabled for the 'org.mongodb.driver' component`

If you would like to see the messages logged from the MongoDB driver, add the following dependencies to the pom.xml file:
```
<!-- https://mvnrepository.com/artifact/org.slf4j/slf4j-api -->
 <dependency>
		 <groupId>org.slf4j</groupId>
		 <artifactId>slf4j-api</artifactId>
		 <version>1.7.36</version>
 </dependency>
 <!-- https://mvnrepository.com/artifact/org.slf4j/slf4j-simple -->
 <dependency>
		 <groupId>org.slf4j</groupId>
		 <artifactId>slf4j-simple</artifactId>
		 <version>1.7.36</version>
 </dependency>
```

Here is a link for more information about [BSON](https://www.mongodb.com/docs/drivers/java/sync/current/fundamentals/data-formats/document-data-format-bson/).

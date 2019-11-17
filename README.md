# JaxRS-Microservice
### this tutorial was made for windows
## You need the following
 - Eclipse
 - JDK 8
## Installing Wildfly
( I have used Wildfly 16 )
 1. Download [Wildfly zip](https://wildfly.org/downloads/) file
 2. Extract to c:\wildfly ( or any other folder you prefer )
 3. Go to Eclipse > Help > Eclipse Marketplace...
 4. Look for JBoss Tools and install
 5. Got to Servers > Click "No server are available. Click this link to create a new server..."
 6. Look for Wildfly ( Wildfly 16 for me ) then Next
 7. Create new runtime and specifiy wildfly directory c:\wildfly in our case
 8. choose java-8-jdk as runtime ( if it does not exist add one )
 9. Finish
 

## Installing Maven
( Maven 3.6.2 )
  1. Download [Maven](https://maven.apache.org/download.cgi) Binary zip file
  2. Extract to c:\maven
  3. Add M2_HOME and MAVEN_HOME to environement variables c:\maven\apache-maven-3.6.2 and add to PATH variable c:\maven\apache-maven-3.6.2\bin
  4. To verify installation open cmd and type mvn -version
  
## Download the project and Run

  1. Download the project as .zip then extract to your eclipse workspace OR run $ git clone https://github.com/psnpsn/JaxRS-Microservice.git into your eclipse workspace
  2. Go to eclipse File > Import
  3. Choose Existing Maven Project
  4. Add the downloaded project
  5. Fix any issue if there is any ( feel free to contact me about your issues )
  6. Right click on project > Run As > Maven install
  7. Right click on your server > Add and Remove
  8. Right click on your server > Start
  
## Testing with Postman
  
  1. Download [Postman](https://www.getpostman.com/downloads/) and install
  2. Open Postman and connect ( or create account )
  
  ### add Employee
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/add
  2. Choose your http method as POST
  3. go to Body > raw > XML(application/xml
  4. Manually simulate an xml employee to send 
    <employee>
	    <name>emp1</name>
	    <salary>100</salary>
	    <id>0</id>
    </employee>
  5. Send
  ### Get All Emlpoyees
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/getAll
  2. Choose your http method as GET
  3. Send
  ### Get One Emloyee by Id 
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/0/get
  2. Choose your http method as GET
  3. Send
  ### Delete Emloyee by Id 
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/0/delete
  2. Choose your http method as DELETE
  3. Send
  
  
## Create your own application
  
  


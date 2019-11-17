# Microservice CRUD Example using Wildfly Jax-RS 
### this tutorial was made for educational purposes

## You need the following
 - Eclipse
 - JDK 8
 
## Installing Wildfly
( I have used Wildfly 16 )
 1. Download [Wildfly zip](https://wildfly.org/downloads/) file
 2. Extract to c:\wildfly ( or any other folder you prefer )
 3. Go to Eclipse > Help > Eclipse Marketplace...
 4. Look for JBoss Tools and install
 ![Imgur Image](https://i.imgur.com/m0Pmzci.png)
 5. Got to Servers > Click "No server are available. Click this link to create a new server..."
 ![Imgur Image](https://i.imgur.com/FM5QQzj.png)
 6. Look for Wildfly ( Wildfly 16 for me ) then Next
 7. Create new runtime and specifiy wildfly directory c:\wildfly in our case
 ![Imgur Image](https://i.imgur.com/QKPSDw5.png)
 8. choose java-8-jdk as runtime ( if it does not exist add one )
 9. Finish
 
## Installing Maven
( Maven 3.6.2 )
  1. Download [Maven](https://maven.apache.org/download.cgi) Binary zip file
  2. Extract to c:\maven
  3. Add M2_HOME and MAVEN_HOME to environement variables c:\maven\apache-maven-3.6.2 and add to PATH variable c:\maven\apache-maven-3.6.2\bin
  4. To verify installation open cmd and type mvn -version
  ![Imgur Image](https://i.imgur.com/T3zFJsr.png)
  
## Download the project and Run
  1. Download the project as .zip then extract to your eclipse workspace OR run $ git clone https://github.com/psnpsn/JaxRS-Microservice.git into your eclipse workspace
  2. Go to eclipse File > Import
  3. Choose Existing Maven Project
  ![Imgur Image](https://i.imgur.com/qOcCjXM.png)
  4. Add the downloaded project
  5. Fix any issue if there is any ( feel free to contact me about your issues )
  6. Right click on project > Run As > Maven install
  7. Right click on your server > Add and Remove > Add your project
  ![Imgur Image](https://i.imgur.com/IbdLfdV.png)
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
  ![Imgur Image](https://i.imgur.com/ubMHESY.png)
  ### Get All Emlpoyees
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/getAll
  2. Choose your http method as GET
  3. Send
  ![Imgur Image](https://i.imgur.com/MJ3RmIL.png)
  ### Get One Emloyee by Id 
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/0/get
  2. Choose your http method as GET
  3. Send
  ### Delete Emloyee by Id 
  1. With your wildfly server running in eclipse type your endpoint address http://localhost:8080/MS-test/employee/0/delete
  2. Choose your http method as DELETE
  3. Send
  ![Imgur Image](https://i.imgur.com/0XY9Rog.png)
  
  
## Create your own application

  ### Configuration
  1. Create new dynamic web project
  2. Convert project to maven project ( right click > configure > )
  3. Modify pom.xml ( copy from another project )
  4. Modify web.xml ( copy from another project )
  ### Packaging
  - model : for storing your models
  - controller : for your rest api controllers
  - service : for your services
  - utils : for your utilitairies classes
  - repository : for your database operations
  ### Classes
  - In our case, models classes declaration begins with  `@XmlRootElement(name = "employee")` leaving the attribute name will take your class name by default.
  - A rest api controller should always start with these annotations
 ```
  > @Path("/route")
  > @Consumes(MediaType.APPLICATION_XML)
  > @Produces(MediaType.APPLICATION_XML)
```
These will tell that our route is /route and the body of our HTTP request will be XML for both consuming and exposing.
  - Every method inside this controller will have their own route defined with annotations above the declaration `@Path("/subroute")`
  - HTTP method can also be described e.g 
  ```
  > @GET
  > @POST
  > @DELETE
  > @PUT
  ```
  - To get parameters from URIs, an id for example, you can define them in your route then using the annotation
  ```
  > @Path("/route/{id})
  > public void getElement(@PathParam("id") int id)
  ```
  in front  of the method parameter declared for the id.
  
  Create a class extending Application from jax rs core and annoted with `@ApplicationPath("rest")`
	
# Thank you	
***Feel free to ask me anything here on github or my email mohamed.jridi.1@esprit.tn***

*ESPRIT 4IoSys 2019-2020*



# WebServices
This project is basically all about the problems and hustle bustle faced by the user while writing down the java servlet code. This project basically aims to save the user's time and hard work which is required in writing down the java servlets.In layman's terms, the only thing the user has to do is writing simple java code without any java servlets.This project will take care of the java servlets.
# Installation:- 
 Simply download the project file, save it and put your code in the folder **com.thinking.machines.user** and you are ready to go..!!
# Usage:-
  Steps are as follows:-
  1. First of all this project requires a file in root folder of the project or parallel to the WEB-INF folder.The file file should be        named as **servicesConf.conf**. This file should contain the path to the java code which the user wishes to integrate with the          project and java servlet. Example:-
     ```
     {"pathSpecifier":"C:.tomcat9.webapps.hussainindustries.WEB-INF.classes.com.thinking.machines.crud"}
     ```
  2. A tool is also avalable for verifying whether the user has correctly integrate the java code with the project or not.If **correct**      then a **services.pdf** would be generated containing the list of classes and methods and annotations applied on them.If                **incorrect**  a **Errors.pdf**  would be generated with error messages in it.
  3. Now to use this project the user should have the knowledge of the annotations.The user should apply following annotations on the          classes and methods.
     1. Path annotation:-Can be applied on class and method.Should be applied on a class and method which you want to invoke on a               request.The request should be of type **_/service/value of path annotation on class/value of path annotation on method**.
        For example the url is `http://localhost:8080/hussainindustries/service/student/addStudent` then the class and method should be         like this:-
        ```
        @path("student")
        class test
        {
         @path("addStudent")
         public void addStudent()
          {
           // some code
          }
        }
        ```
        In above example on this type of request in class with path annotation of value **student** the method with path annotation             value **/addStudent** would be invoked.All the methods which user wants to be invoked by a specific type of request should be           annotated by path annotation.
     2. Upload Annotation:- This annotation should be applied on methods which need some file or files uploaded by the user.All the             files uploaded by the user would also be saved on the local disk in uploads folder in project directory.
     3. ResponseSpecifier Annotation:-This annotation specifies in what form the user wants to send the end result after a method               has been invoked.Three options are avalaible : **1) JSON:-** the result would sent in json form. **2) HTML/TEXT:-** the result           would be sent to the client in simple text form.**3) NOTHING:-** An empty string would be sent to the client in response.
     4. Secured Annotation:-When applied this annotation would check if the user is logged in or not. For this annotation to work               user should provide the name of a class as value to this annotation.In turn the class provided by the user should have                   implemented the `SecurityInterface`.The user should provide a URL as a string in ` Response class`.
     

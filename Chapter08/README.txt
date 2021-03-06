Steps to Deploy examples from Chapter 08

1. Copy the war files to your application server's deployment directory
   a. For Tomcat, copy the war files to the Tomcat webapps directory
   b. For JBoss, copy the war files to the JBoss server\all\deploy directory
2. Access each application through the URL http://localhost:8080/Jdbc_Ex0n
   a. Replace localhost with host:port if your server is accessed on a different machine and different port
   b. Replace the 'n' in Jdbc_Ex0n with the correct example number, e.g. Jdbc_Ex03

These examples were built for Tomcat 5.5. They include context.xml files which define database connection parameters for a MySQL database. If your database is different, you will need to modify the context.xml file, or configure the data connection through your application server. SQL scripts to create the tables for MySQL are in the script mysql-setup.sql. If you are using pointbase, the tables already exist and you only need to setup the data source. If you are using some other database, you can modify the commands in mysql-setup.sql for your database.

If you want to experiment with the applications, or rebuild an application, you can expand each WAR file to a development directory to edit the application. Each WAR file includes an Ant build.xml file and an ant.properties file. Modify the ant.properties file to include the correct path to the server deploy directory. The build.xml file contains these targets:

compile - compiles the class files
stage-web - calls compile, then creates the WAR file
deploy - calls stage stage-web, then copies the WAR file to the deploy directory
clean - removes the build directory
cleanall - removes the compiled class files and the build directory

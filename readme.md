#Example for using liquibase:

##Start mysql and create databse
mysql.server start

mysql -u root -p
<EMPTY PASSWORD>

drop database if exists pilot;

create database pilot;

use pilot;

##Build and execute the app
mvn clean install

java -jar target/liquibase-demo-0.0.1-SNAPSHOT.jar

##Verify the changes in mysql
show tables;

select ID, AUTHOR, FILENAME from DATABASECHANGELOG;


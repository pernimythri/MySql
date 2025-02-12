**Run in command prompt ->    mysql -u root -p**
**Enter password:--**
--------------------------------------------------------------------------------------------------
**Creating database**
> create database mythri;
> use mythri;

> show databases;
    
    | Database           |
    +--------------------+
    |  mythri            |
    

> show tables;
   Empty set (0.00 sec)

**Creating table**
> create table customer(customerId INT PRIMARY KEY , customerName VARCHAR(80),lastName VARCHAR(50) , age INT CHECK(age>0  AND age<100),phoneNumber INT(10));
> show tables;
      
      | Tables_in_mythri |
      +------------------+
      | customer         |
      

**Inserting values to table**
> INSERT INTO customer(customerID,customerName,lastName,age,phoneNumber)VALUES(1,'mythri','p',19,1234567890),(2,'sai','k',20,9898989898),(3,'shiva','a',12,1212121212),(4,'ram','g',15,2323232323),(5,'krishna','m',24,4545454545);
> select * from customer;
      | customerId | customerName | lastName | age  | phoneNumber |
      +------------+--------------+----------+------+-------------+
      |          1 | mythri       | p        |   19 |  1234567890 |
      |          2 | sai          | k        |   20 |  2147483647 |
      |          3 | shiva        | a        |   12 |  1212121212 |
      |          4 | ram          | g        |   15 |  2147483647 |
      |          5 | krishna      | m        |   24 |  2147483647 |


**Create Table From Another Table**
  > CREATE TABLE subTable AS SELECT customerId,customerName FROM customer;
  > show tables;
        
        | Tables_in_mythri |
        +------------------+
        | customer         |
        | subtable         |
        

**Select Command**
  > select * from subtable;
        
        | customerId | customerName |
        +------------+--------------+
        |          1 | mythri       |
        |          2 | sai          |
        |          3 | shiva        |
        |          4 | ram          |
        |          5 | krishna      |
        

**Display the structure of the created table**    
   > desc customer;
            
            | Field        | Type        | Null | Key | Default | Extra |
            +--------------+-------------+------+-----+---------+-------+
            | customerId   | int(11)     | NO   | PRI | NULL    |       |
            | customerName | varchar(80) | YES  |     | NULL    |       |
            | lastName     | varchar(50) | YES  |     | NULL    |       |
            | age          | int(11)     | YES  |     | NULL    |       |
            | phoneNumber  | int(10)     | YES  |     | NULL    |       |
            

**Delete the table**
  > drop table subtable;
  > show tables;
    
    | Tables_in_mythri |
    +------------------+
    | customer         |
    





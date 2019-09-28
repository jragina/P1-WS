# P1-WS
MYSQL download available at: https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-web-community-8.0.17.0.msi

When setting up the MYSQL use the following creds:
username:root
password:12345

firstly create database from  MySQL 8.0 Command Line Client
Login with root password

execute this:
create database mydatabase;

then change database this way:
use mydartabase;

SQL FOR ESENTIAL DATA POPULATION:

create table Accounts (
        User_Name varchar(20) not null,
        Active bit not null,
        Password varchar(20) not null,
        User_Role varchar(20) not null,
        primary key (User_Name)
    );
 
    create table Order_Details (
        ID varchar(50) not null,
        Amount double precision not null,
        Price double precision not null,
        Quanity integer not null,
        ORDER_ID varchar(50) not null,
        PRODUCT_ID varchar(20) not null,
        primary key (ID)
    );
 
    create table Orders (
        ID varchar(50) not null,
        Amount double precision not null,
        Customer_Address varchar(255) not null,
        Customer_Email varchar(128) not null,
        Customer_Name varchar(255) not null,
        Customer_Phone varchar(128) not null,
        Order_Date datetime not null,
        Order_Num integer not null,
        primary key (ID)
    );
 
    create table Products (
        Code varchar(20) not null,
        Create_Date datetime not null,
        Image longblob,
        Name varchar(255) not null,
        Price double precision not null,
        primary key (Code)
    );
 
    alter table Orders
        add constraint UK_sxhpvsj665kmi4f7jdu9d2791  unique (Order_Num);
 
    alter table Order_Details
        add constraint ORDER_DETAIL_ORD_FK
        foreign key (ORDER_ID)
        references Orders (ID);
 
    alter table Order_Details
        add constraint ORDER_DETAIL_PROD_FK
        foreign key (PRODUCT_ID)
        references Products (Code);
 
---------------------------------------
insert into Accounts (USER_NAME, ACTIVE, PASSWORD, USER_ROLE)
values ('employee1', 1, '123', 'EMPLOYEE');
 
insert into Accounts (USER_NAME, ACTIVE, PASSWORD, USER_ROLE)
values ('manager1', 1, '123', 'MANAGER');
 
----------------
insert into products (CODE, NAME, PRICE, CREATE_DATE)
values ('S001', 'Core Java', 100, current_timestamp() );
 
insert into products (CODE, NAME, PRICE, CREATE_DATE)
values ('S002', 'Spring for Beginners', 50, current_timestamp() );
 
insert into products (CODE, NAME, PRICE, CREATE_DATE)
values ('S003', 'Swift for Beginners', 120, current_timestamp() );
 
insert into products (CODE, NAME, PRICE, CREATE_DATE)
values ('S004', 'Oracle XML Parser', 120, current_timestamp() );
 
insert into products (CODE, NAME, PRICE, CREATE_DATE)
values ('S005', 'CSharp Tutorial for Beginers', 110, current_timestamp() );
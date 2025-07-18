# DELETE-UPDATE-WHERE---SQL
BASICS OF DELETE/UPDATE/WHERE



-- BASICS OF DELETE/UPDATE/WHERE


drop table snapdeal_orders;

create table snapdeal_orders
(
order_Id int, 
order_date date, 
product_name varchar(50),
total decimal(10,2),
payment_method varchar(30),
discount INT,
category varchar,
primary key (order_Id,product_name)
); 

insert into snapdeal_orders (order_Id,order_date,product_name,total,payment_method,discount)
values (1,'2022-04-05 12:05:57','coat',4000,'card',5);


-- primary key can be a combination of two column, means combination of two column should be unique

insert into snapdeal_orders (order_Id,order_date,product_name,total,payment_method,discount)
values (1,'2022-04-05 12:05:57','shirt',4000,'card',5),
       (3,'2022-04-05 12:05:57','shirt',4000,'card',5),
	   (4,'2022-04-05 12:05:57','t-shirt',4000,'card',5);


select * from snapdeal_orders;

delete from snapdeal_orders where product_name = 'coat';

delete from snapdeal_orders where order_ID = 4;

update snapdeal_orders
set discount = 10;

update snapdeal_orders
set discount = 5
where order_ID = 3;


update snapdeal_orders
set discount = 5 , product_name = 'coat'
where order_ID = 3;

# user_details

## Feature 1: Registration
```sql
CREATE TABLE roles (id INT, NAME VARCHAR(20)NOT NULL unique(name),PRIMARY KEY(id));
```
```
INSERT INTO roles(id,NAME) VALUES (1,'USER');
INSERT INTO roles(id,NAME) VALUES (2,'ADMIN');
```

```sql

CREATE TABLE user_details(id INT AUTO_INCREMENT,NAME VARCHAR(20)NOT NULL, email_id VARCHAR(50) NOT NULL, UNIQUE(email_id),
PASSWORD VARCHAR(20) NOT NULL, created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,PRIMARY KEY(id), gender CHAR(1),role_id INT DEFAULT 1,
CONSTRAINT user_details_id_fk FOREIGN KEY(id) REFERENCES roles(id),
CONSTRAINT user_details_chk_pwd CHECK(LENGTH(PASSWORD)>=8),
CONSTRAINT user_details_chk_gender CHECK(gender IN('M','F')));
```

## Feature 2: Login user

```sql

SELECT name FROM user_details WHERE email_id='jay@gmail.com' AND PASSWORD ='j12345678';
```

## Feature 3: List All Users 

```sql
SELECT name,phone_no FROM user_details order by name;
```
## Feature 4: change password
```sql
UPDATE user_details SET PASSWORD ='jay1234',modified_date = current_timestamp WHERE id =2;
```
## Feature 5: change role
```sql
UPDATE user_details SET role_id =2,modified_date = CURRENT_TIMESTAMP WHERE id=1;
```
## Module 2: Task
```sql
CREATE TABLE task(id INT AUTO_INCREMENT, task_name VARCHAR(20) NOT NULL, STATUS VARCHAR(20) DEFAULT 'PENDING',
 PRIMARY KEY (id),
 start_date TIMESTAMP,
 end_date TIMESTAMP);
```
```sql
INSERT INTO task(task_name) VALUES ('sql');
INSERT INTO task(task_name) VALUES ('JavaScript');
INSERT INTO task(task_name) VALUES ('HTML');
INSERT INTO task(task_name) VALUES ('Java');
```
```sql

UPDATE task SET STATUS='Inprogress',start_date ='2020-03-20' WHERE id = 4;
UPDATE task SET STATUS='Inprogress',start_date ='2020-03-20' WHERE id = 3;
UPDATE task SET STATUS='Completed',end_date ='2020-05-20' WHERE id = 3;
```
```sql
ALTER TABLE task ADD priority INT;
```
```sql
UPDATE task SET priority=2 WHERE id =2;
UPDATE task SET priority=3 WHERE id =1;
UPDATE task SET priority=1 WHERE id =4;
```
## Feature 6: Others
```sql
ALTER TABLE user_details ADD DOB DATE;
```
```sql
ALTER TABLE user_details ADD phone_no LONG;
```
```sql
ALTER TABLE user_details DROP user_id;
```
```sql
DROP TABLE user_details;
```
```sql
INSERT INTO user_details (username,email_id,PASSWORD,created_date,gender,phone_no) VALUES ('jayanthi','jay@gmail.com','j1234','2020-02-03','F',9888888999);
```


```sql
SELECT gender, COUNT(*) FROM user_details GROUP BY gender;
```
```sql
SELECT * FROM user_details ORDER BY username DESC;
```
```sql
SELECT * FROM user_details ORDER BY username ASC;
```
```sql
SELECT COUNT(gender) FROM user_details;
```
```sql
DELETE FROM user_details WHERE username ='narain';
```
```

UPDATE task SET priority=2 WHERE id =2;
UPDATE task SET priority=3 WHERE id =3;
UPDATE task SET priority=1 WHERE id =4;
DROP TABLE task;
SELECT * FROM task;
```

# shopping
```sql
CREATE TABLE item(id INT AUTO_INCREMENT, item_name VARCHAR(20) NOT NULL, UNIQUE(item_name),price INT,PRIMARY KEY(id), created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
```


```sql-DDL
CREATE TABLE item_orders(order_id INT AUTO_INCREMENT,item_id INT NOT NULL,item_name VARCHAR(20) NOT NULL, price INT, quantitiy INT, total_price INT, order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
CONSTRAINT item_orders_item_id_fk FOREIGN KEY (item_id) REFERENCES item(id),PRIMARY KEY(order_id));
```
```sql
DROP TABLE item_orders;
```
```sql
ALTER TABLE item_orders ADD email_id VARCHAR(50);
```
```sql
TRUNCATE TABLE item_orders;
```
```sql- DML

INSERT INTO item_orders(item_id,item_name,price,quantitiy,total_price,order_date) VALUES (1,'soap',30,6,180,'2020-05-22');
INSERT INTO item_orders(item_id,item_name,price,quantitiy,total_price,order_date) VALUES (3,'dal',120,2,240,'2020-05-22');
INSERT INTO item_orders(item_id,item_name,price,quantitiy,total_price,order_date) VALUES (4,'rice',60,3,180,'2020-05-22');
INSERT INTO item_orders(item_id,item_name,price,quantitiy,total_price,order_date) VALUES (5,'shampoo',100,5,500,'2020-05-22');
INSERT INTO item_orders(item_id,item_name,price,quantitiy,total_price,order_date) VALUES (6,'ragi',40,5,200,'2020-05-22');
```
```sql
UPDATE item_orders SET price =35, quantitiy =6, total_price =210 WHERE item_id = 1;
```
```sql

DELETE FROM item_orders WHERE item_id = 6;
```

```sql-dql
SELECT * FROM item_orders;
```
```sql
SELECT item_name,quantitiy AS qty, price FROM item_orders;
```
```sql-TCL 
COMMIT;
```
```sql
ROLLBACK;
```
```sql-sorting

 SELECT * FROM item ORDER BY price ASC;
 ```
 ```sql
 SELECT * FROM item ORDER BY price DESC;
```

```sql- Restricting

SELECT * FROM item WHERE id=1;
```
```
SELECT * FROM item WHERE (item_name ='soap' AND price =30);
```
```
SELECT * FROM item WHERE (item_name ='soap' OR price =60);
```
```
SELECT * FROM item WHERE item_name='soap' AND price NOT IN(100,200);
```
```
SELECT * FROM item WHERE item_name LIKE 'r%';
```
```
SELECT * FROM item WHERE price IN(30,40);

```
```
SELECT * FROM item_orders WHERE MONTH(order_date) NOT BETWEEN  '05' AND '06' AND YEAR(order_date) NOT BETWEEN '2020' AND '2021';

```
```
SELECT * FROM item WHERE item_name IS NULL;

```
```
SELECT * FROM item WHERE item_name IS NOT NULL;

```
```
SELECT * FROM item WHERE price = 40;

```
```
SELECT * FROM item WHERE price > 50;

```
```
SELECT * FROM item WHERE price >= 40;

```
```
SELECT * FROM item WHERE price < 50;

```
```
SELECT * FROM item WHERE price <=40;

```
```
SELECT * FROM item WHERE price != 60;

```
```sql-aggregate function

SELECT COUNT(*) FROM item_orders;

```
```
SELECT MIN(price) AS amounnt FROM item_orders;

```
```
SELECT SUM(price) AS amounnt FROM item_orders;

```
```
SELECT AVG(price) AS amounnt FROM item_orders;

```
```
SELECT COUNT(*),price FROM item GROUP BY price;

```
```
SELECT * FROM item;

```
```


#  task1
SELECT * FROM task1;


SELECT SYSDATE();--sydate
SELECT SYSDATE() +1;---together


INSERT INTO task1 (id,task_name,STATUS,created_date) VALUES (1, 'java', 'completed','2020-09-03');----learned DATE FORMAT
INSERT INTO task1 VALUES (2, 'Javascript', 'pending','2020-10-13');
INSERT INTO task1 VALUES (3, 'SQL', 'pending','2020-12-13');

SELECT CONCAT('java' ,'is','completed') AS ConcatenatedString FROM task1;

SELECT task_name, CONCAT(task_name,' ','is',' ','completed',' ', 'on',' ',created_date ) AS ConcatenatedString FROM task1;

SELECT TRUNCATE(345.156, 0);

SELECT ROUND(345.156, 0);

SELECT CEIL(25);

SELECT * FROM task1 WHERE STATUS ='pending';

SELECT * FROM task1 WHERE (task_name ='javascript' AND STATUS ='pending');


SELECT * FROM task1 WHERE (task_name ='javascript') OR ( STATUS ='pending' AND created_date='2020-10-13');

SELECT task_name, STATUS FROM task1 WHERE task_name LIKE 's%';
SELECT task_name, STATUS FROM task1 WHERE task_name LIKE '%pt';

SELECT COUNT(*) FROM task1;
# table created SELECT * FROM item;

INSERT INTO item(item_name,price,created_date) VALUES ('soap', 30,'2020-03-04');
INSERT INTO item(item_name,price,created_date) VALUES ('shampoo', 100,'2020-03-05');
INSERT INTO item(item_name,price,created_date) VALUES ('dal', 120,'2020-03-05');
INSERT INTO item(item_name,price,created_date) VALUES ('rice', 60,'2020-03-14');
INSERT INTO item(item_name,price,created_date) VALUES ('ragi', 40,'2020-03-14');
INSERT INTO item(item_name,price,created_date) VALUES ('biscuit', 40,'2020-03-14');
INSERT INTO item(item_name,price,created_date) VALUES ('chocolate', 40,'2020-03-14');

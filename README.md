# user_details

## Feature 1: Registration
```sql
CREATE TABLE user_details(id INT AUTO_INCREMENT,username VARCHAR(20)NOT NULL, email_id VARCHAR(50) NOT NULL, UNIQUE(email_id),
PASSWORD VARCHAR(20) NOT NULL, created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,PRIMARY KEY(id), gender CHAR(1));
```

## Feature 2: Login user

```sql
SELECT  * FROM user_details WHERE email_id='jay@gmail.com' AND PASSWORD ='j1234';
```

## Feature 3: List All Users 

```sql
SELECT * FROM user_details;
```

## Feature 4: change password
```sql
UPDATE user_details SET PASSWORD ='jay1234' WHERE id =2;
```

## Feature 5: Others
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

# user_details

CREATE TABLE user_details(id INT AUTO_INCREMENT,username VARCHAR(20)NOT NULL, email_id VARCHAR(50) NOT NULL, UNIQUE(email_id),
PASSWORD VARCHAR(20) NOT NULL, created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,PRIMARY KEY(id), gender CHAR(1));

ALTER TABLE user_details ADD user_id INT;

ALTER TABLE user_details ADD phone_no LONG;

ALTER TABLE user_details DROP user_id;

SELECT * FROM user_details;
 
DROP TABLE user_details;

INSERT INTO user_details VALUES (1,'jayanthi','jay@gmail.com','j1234','2020-02-03','F',9888888999);

#task1
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

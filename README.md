# user_details

CREATE TABLE user_details(username VARCHAR(20)NOT NULL, email_id VARCHAR(20) NOT NULL, UNIQUE(email_id), PASSWORD VARCHAR(20) NOT NULL);

SELECT * FROM user_details;

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

mysql> drop database if exists careerhub;
Query OK, 0 rows affected, 1 warning (0.01 sec)

mysql> create database careerhub;
Query OK, 1 row affected (0.01 sec)

mysql> use careerhub;
Database changed
mysql> drop table if exists companies;
Query OK, 0 rows affected, 1 warning (0.01 sec)

mysql> ^C
mysql> create table if not exists companies (
    ->     company_id int primary key,
    ->     company_name varchar(255) not null,
    ->     location varchar(255) not null
    -> );
Query OK, 0 rows affected (0.03 sec)

mysql> drop table if exists jobs;
Query OK, 0 rows affected, 1 warning (0.00 sec)

mysql> create table if not exists jobs (
    ->     job_id int primary key,
    ->     company_id int not null,
    ->     job_title varchar(255) not null,
    ->     job_description text,
    ->     job_location varchar(255),
    ->     salary decimal(10, 2),
    ->     job_type varchar(50),
    ->     posted_date datetime not null,
    ->     foreign key (company_id) references companies(company_id)
    -> );
Query OK, 0 rows affected (0.06 sec)

mysql> CREATE TABLE applicants (
    ->     applicant_id INT PRIMARY KEY,       
    ->     first_name VARCHAR(50) NOT NULL,   
    ->     last_name VARCHAR(50) NOT NULL,    
    ->     email VARCHAR(100) NOT NULL UNIQUE, 
    ->     phone VARCHAR(15) NOT NULL,         
    ->     resume TEXT NOT NULL,               
    ->     experience INT NOT NULL,            
    ->     city VARCHAR(50) NOT NULL,          
    ->     state VARCHAR(50) NOT NULL          
    -> );
Query OK, 0 rows affected (0.07 sec)

mysql> create table applications (
    ->     application_id int primary key,
    ->     job_id int not null,
    ->     applicant_id int not null,
    ->     application_date datetime not null,
    ->     cover_letter text,
    ->     foreign key (job_id) references jobs(job_id),
    ->     foreign key (applicant_id) references applicants(applicant_id)
    -> );
Query OK, 0 rows affected (0.07 sec)

mysql> INSERT INTO companies (company_id, company_name, location) VALUES
    -> (1, 'Tata Consultancy services', 'Mumbai'),
    -> (2, 'Infosys', 'Bengaluru'),
    -> (3, 'Wipro', 'Bengaluru'),
    -> (4, 'HCL', 'Noida'),
    -> (5, 'Hexaware Technologies', 'Chennai');
Query OK, 5 rows affected (0.00 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> INSERT INTO jobs (job_id, company_id, job_title, job_description, job_location, salary, job_type, posted_date) VALUES
    -> (1, 1, 'Software Engineer', 'Develop and maintain software Applications', 'Mumbai', 60000.00, 'Fulltime', '2024-09-01 00:00:00'),
    -> (2, 2, 'Data Analyst', 'Analyze data and provide Insights', 'Bengaluru', 50000.00, 'FullTime', '2024-09-10 00:00:00'),
    -> (3, 3, 'Project Manager', 'Lead software development projects', 'Bengaluru', 70000.00, 'Fulltime', '2024-08-25 00:00:00'),
    -> (4, 4, 'System Administrator', 'Manage and maintain IT infrastructure', 'Noida', 20000.00, 'Part-time', '2024-08-20 00:00:00'),
    -> (5, 5, 'Full Stack Developer', 'Develop and manage web Applications', 'Chennai', 25000.00, 'FullTime', '2024-09-05 00:00:00'),
    -> (6, 2, 'Business Analyst', 'Analyze business processes and requirements.', 'Bengaluru', 65000.00, 'Full-Time', '2024-10-01 00:00:00'),
    -> (7, 3, 'Intern', 'Assist with tasks and gain experience', 'Bengaluru', 0.00, 'Part-Time', '2024-10-01 00:00:00');
Query OK, 7 rows affected (0.01 sec)
Records: 7  Duplicates: 0  Warnings: 0

mysql> INSERT INTO applicants (applicant_id, first_name, last_name, email, phone, resume, experience, city, state) VALUES
    -> (1, 'Rohit', 'Sharma', 'rohit.sharma@gmail.com', '9876543210', 'Experienced software engineer with 5+ years in development.', 5, 'Delhi', 'Delhi'),
    -> (2, 'Virat', 'Kohli', 'virat.kohli@gmail.com', '9876543211', 'Data analyst with expertise in Python and SQL.', 7, 'Mumbai', 'Maharashtra'),
    -> (3, 'Shubman', 'Gill', 'shubman.gill@gmail.com', '9876543212', 'Project manager with 2+ years of experience.', 2, 'Kolkata', 'West Bengal'),
    -> (4, 'Suryakumar', 'Yadav', 'surya@gmail.com', '9876543213', 'System administrator with strong Linux.', 2, 'Chennai', 'Tamil Nadu'),
    -> (5, 'Jasprit', 'Bumrah', 'jassi@gmail.com', '9876543214', 'Experienced full stack developer with good knowledge of both front and back end.', 5, 'Ahmedabad', 'Gujarat');
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> insert into applications (application_id, job_id, applicant_id, application_date, cover_letter)
    -> values
    -> (1, 1, 1, '2024-09-02', 'I am excited to apply for the Software Engineer role at TCS.'),
    -> (2, 2, 2, '2024-09-11', 'Looking forward to contributing as a Data Analyst at Infosys.'),
    -> (3, 3, 3, '2024-08-26', 'Eager to lead projects as a Project Manager at Wipro.'),
    -> (4, 4, 4, '2024-08-21', 'Passionate about IT infrastructure, applying for System Administrator at HCL.'),
    -> (5, 5, 5, '2024-09-06', 'Excited to handle marketing campaigns at Reliance Industries.');
Query OK, 5 rows affected (0.01 sec)
Records: 5  Duplicates: 0  Warnings: 0

mysql> select* from companies;
+------------+---------------------------+-----------+
| company_id | company_name              | location  |
+------------+---------------------------+-----------+
|          1 | Tata Consultancy services | Mumbai    |
|          2 | Infosys                   | Bengaluru |
|          3 | Wipro                     | Bengaluru |
|          4 | HCL                       | Noida     |
|          5 | Hexaware Technologies     | Chennai   |
+------------+---------------------------+-----------+
5 rows in set (0.00 sec)

mysql> select * from jobs;
+--------+------------+----------------------+----------------------------------------------+--------------+----------+-----------+---------------------+
| job_id | company_id | job_title            | job_description
                | job_location | salary   | job_type  | posted_date
|
+--------+------------+----------------------+----------------------------------------------+--------------+----------+-----------+---------------------+
|      1 |          1 | Software Engineer    | Develop and maintain software Applications   | Mumbai       | 60000.00 | Fulltime  | 2024-09-01 00:00:00 |
|      2 |          2 | Data Analyst         | Analyze data and provide Insights            | Bengaluru    | 50000.00 | FullTime  | 2024-09-10 00:00:00 |
|      3 |          3 | Project Manager      | Lead software development projects           | Bengaluru    | 70000.00 | Fulltime  | 2024-08-25 00:00:00 |
|      4 |          4 | System Administrator | Manage and maintain IT infrastructure        | Noida        | 20000.00 | Part-time | 2024-08-20 00:00:00 |
|      5 |          5 | Full Stack Developer | Develop and manage web Applications          | Chennai      | 25000.00 | FullTime  | 2024-09-05 00:00:00 |
|      6 |          2 | Business Analyst     | Analyze business processes and requirements. | Bengaluru    | 65000.00 | Full-Time | 2024-10-01 00:00:00 |
|      7 |          3 | Intern               | Assist with tasks and gain experience        | Bengaluru    |     0.00 | Part-Time | 2024-10-01 00:00:00 |
+--------+------------+----------------------+----------------------------------------------+--------------+----------+-----------+---------------------+
7 rows in set (0.00 sec)

mysql> select * from applicants;
+--------------+------------+-----------+------------------------+------------+----------------------------------------------------------------------------------+------------+-----------+-------------+
| applicant_id | first_name | last_name | email                  | phone      | resume
         | experience | city      | state       |
+--------------+------------+-----------+------------------------+------------+----------------------------------------------------------------------------------+------------+-----------+-------------+
|            1 | Rohit      | Sharma    | rohit.sharma@gmail.com | 9876543210 | Experienced software engineer with 5+ years in development.
         |          5 | Delhi     | Delhi       |
|            2 | Virat      | Kohli     | virat.kohli@gmail.com  | 9876543211 | Data analyst with expertise in Python and SQL.
         |          7 | Mumbai    | Maharashtra |
|            3 | Shubman    | Gill      | shubman.gill@gmail.com | 9876543212 | Project manager with 2+ years of experience.
         |          2 | Kolkata   | West Bengal |
|            4 | Suryakumar | Yadav     | surya@gmail.com        | 9876543213 | System administrator with strong Linux.
         |          2 | Chennai   | Tamil Nadu  |
|            5 | Jasprit    | Bumrah    | jassi@gmail.com        | 9876543214 | Experienced full stack developer with good knowledge of both front and back end. |          5 | Ahmedabad | Gujarat     |
+--------------+------------+-----------+------------------------+------------+----------------------------------------------------------------------------------+------------+-----------+-------------+
5 rows in set (0.00 sec)

mysql> select * from applications;
+----------------+--------+--------------+---------------------+-------------------------------------------------------------------------------+
| application_id | job_id | applicant_id | application_date    | cover_letter                                                                  |
+----------------+--------+--------------+---------------------+-------------------------------------------------------------------------------+
|              1 |      1 |            1 | 2024-09-02 00:00:00 | I am excited to apply for the Software Engineer role at TCS.                  |
|              2 |      2 |            2 | 2024-09-11 00:00:00 | Looking forward to contributing as a Data Analyst at Infosys.                 |
|              3 |      3 |            3 | 2024-08-26 00:00:00 | Eager to lead projects as a Project Manager at Wipro.                         |
|              4 |      4 |            4 | 2024-08-21 00:00:00 | Passionate about IT infrastructure, applying for System Administrator at HCL. |
|              5 |      5 |            5 | 2024-09-06 00:00:00 | Excited to handle marketing campaigns at Reliance Industries.                 |
+----------------+--------+--------------+---------------------+-------------------------------------------------------------------------------+
5 rows in set (0.00 sec)

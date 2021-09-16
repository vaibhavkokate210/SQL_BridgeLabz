/*UC1*/
show databases;
create database payroll_service;
show databases;
use payroll_service; 

/*UC2*/
create table employee_payroll
(
id Int unsigned NOT NULL AUTO_INCREMENT,
name Varchar(30) NOT NULL,
salary Double NOT NULL,
start Date NOT NULL,
PRIMARY KEY (id)
);

/*UC3*/
insert into employee_payroll (name,salary,start) values
('Bill',100000.00,'2018-01-03'),
('Charlie',200000.00,'2019-03-15'),
('Anna',300000.00,'2020-04-23');

/*UC4*/
select * from employee_payroll;

/*UC5*/
select salary from employee_payroll where name = 'Bill';
select salary from employee_payroll where start between CAST('2018-01-01' as Date) AND Date(now());

/*UC6*/
Alter table employee_payroll Add gender char(1) NOT NULL;
update employee_payroll set gender = 'F' where name = 'Anna';
update employee_payroll set gender = 'M' where name != 'Anna';

/*UC7*/
select gender,sum(salary) from employee_payroll group by gender;
select gender,avg(salary) from employee_payroll group by gender;
select gender,min(salary) from employee_payroll group by gender;
select gender,max(salary) from employee_payroll group by gender;
select gender,count(salary) from employee_payroll group by gender;
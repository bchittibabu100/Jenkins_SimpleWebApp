# Jenkins_SimpleWebAp
Installation of MySQL on RHEL-7
###############################

1. wget http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm (RHEL-7)
2. wget http://dev.mysql.com/get/mysql57-community-release-el6-7.noarch.rpm (RHEL-6)

# yum localinstall mysql57-community-release-el7-7.noarch.rpm

# yum repolist enabled | grep "mysql.*-community.*"

# yum install mysql-community-server

# yum-config-manager --disable mysql57-community
# yum-config-manager --enable mysql56-community

# service mysqld start

# service mysqld status

[root@ip-172-31-0-38 ~]# grep "temporary password" /var/log/mysqld.log
2017-01-21T10:48:25.489341Z 1 [Note] A temporary password is generated for root@localhost: v>6kkItAuguy

# mysql_secure_installation

create database mytest

GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';

-- Create table
create table user_account
(
USER_NAME VARCHAR(30) not null,
GENDER    VARCHAR(1) not null,
PASSWORD  VARCHAR(30) not null,
primary key (USER_NAME)
);
 
-- Create table
create table product
(
CODE  VARCHAR(20) not null,
NAME  VARCHAR(128) not null,
PRICE FLOAT not null,
primary key (CODE)
) ;
 
-- Insert data: ---------------------------------------------------------------
 
insert into user_account (USER_NAME, GENDER, PASSWORD) values ('tom', 'M', 'tom001');
 
insert into user_account (USER_NAME, GENDER, PASSWORD) values ('jerry', 'M', 'jerry001');
 
insert into product (CODE, NAME, PRICE) values ('P001', 'Java Core', 100);
 
insert into product (CODE, NAME, PRICE) values ('P002', 'C# Core', 90);

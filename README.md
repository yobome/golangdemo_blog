# golangdemo_blog

## Introduction
It's a simple blog module based on echo framework.

## Usage

### Create database table
```mysql

create DATABASE myblog;
CREATE USER 'admin'@'localhost' IDENTIFIED WITH mysql_native_password BY 'admin';
GRANT ALL PRIVILEGES ON myblog.* To 'admin'@'localhost';

blog table
+--------------+------------+------+-----+---------+--------------+
| Field        | Type       | Null | Key | Default | Extra        |
+--------------+------------+------+-----+---------+--------------+
| id           | int(64)    | NO   | PRI | NULL    |AUTO_INCREMENT|
| title        | VARCHAR(50)| NO   |     | NULL    |              |
| author       | VARCHAR(20)| NO   |     | NULL    |              |
| timestamp    | int(11)    | NO   |     | NULL    |              |
| content      | MEDIUMTEXT | NO   |     | NULL    |              |
+--------------+------------+------+-----+---------+--------------+

comment
+--------------+------------+------+-----+---------+--------------+
| Field        | Type       | Null | Key | Default | Extra        |
+--------------+------------+------+-----+---------+--------------+
| id           | int(64)    | NO   |     | NULL    |              |
| Cid          | int(64)    | NO   | PRI | NULL    |AUTO_INCREMENT|
| fromIP       | VARCHAR(20)| NO   |     | NULL    |              |
| timestamp    | int(11)    | NO   |     | NULL    |              |
| content      | MEDIUMTEXT | NO   |     | NULL    |              |
+--------------+------------+------+-----+---------+--------------+
```

### Start testing
Using `Postman` or `"HTTP Client" in Goland` to test.

there are user and password info to login:

user:admin
password:secret

#### Router
|路径|方法|用途|
|:---|----|:---:|
|"/"           | get |index|
|"/postarticle" |post |post a new article|
|"/articles"    |get |get all articles|
|"/article/:id" |get |get a article by id|
|"/comment/:id" |get |get the comment from article by id|
|"/comment/:id" |post |post a comment to the article by id|

# golangdemo_blog_microservice

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
| id           | int(64)    | NO   |     | NULL    |			  |
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
|"/"           | get |首页|
|"/postarticle" |post |创建新博客文章|
|"/articles"    |get |请求所有文章列表|
|"/article/:id" |get |请求单独一页文章|
|"/comment/:id" |get |取得文章评论|
|"/comment/:id" |post |对当前id文章评论|
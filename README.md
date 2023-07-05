
create database bookdb;

CREATE TABLE bookdb.books (
b_id int,
title varchar(34),
year int,
price int,
primary key (b_id)
);

create table bookdb.authors(
a_id int,
name varchar(34),
age int,
b_id int,
primary key (a_id),
foreign key (b_id) references books(b_id)
);


insert into bookdb.books values
(1,'maths',1834,1924),
(2,'science',1925,1999),
(3,'social',2007,1799),
(4,'english',2015,2066),
(5,'commerce',2021,2023);


insert into bookdb.authors values
(1,'abi',40,22),
(2,'balachandran',35,89),
(3,'kaviya',56,90),
(4,'sathiyakala',46,12),
(5,'pranav',48,24);


SELECT * FROM bookdb.books;


SELECT * FROM bookdb.books where title='maths';


update bookdb.books set price=499 where title='science';


delete from bookdb.books where title='english';


select avg(price) from bookdb.books;


SELECT books.title,authors.name FROM bookdb.books
join bookdb.authors on bookdb.books.b_id=bookdb.authors.b_id;

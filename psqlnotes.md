## Create a database
	createdb mydb

## Access the database
	psql mydb

## Create a table
	create table weather(
		city varchar(50),
		temp_lo int,
		temp_hi int,
		date date
	);

## Populate the table
	insert into weather values ('San Francisco', 46, 50, 0.25, '1994-11-27')
;
#### or if you wish to omit columns
	insert into weather (date, city, temp_hi, temp_lo) values ('1994-11-29', 'Hayward', 54, 37);

#### or you can copy from a file
	copy weather FROM '/home/user/weather.txt';

## Query a table
	select city, temp_lo, temp_hi from weather;
#### or to select all columns
	select * from weather;

## where clause
	select * from weather where city= "Chennai";
## and clause
	select * from weather where temp_lo>20 and city= "Delhi";
## or clause
	select * from weather where city= "Chennai" or city= "Delhi";
## Sort the result
	select * from weather order by name;
#### Descending order
	select * from weather order by name desc;
## To remove duplicates
	select distinct city from weather;
## Joins
* Inner join	
* Right outer join
* Left outer join
* Full outer join

#### Example
	select * from cities inner join weather on (weather.city= cities.name);

## Aggregate functions
* sum
* max
* min
* avg

#### Examples
	select city from weather where temp_lo= (select max(temp_lo) from weather);
	select avg(temp_hi) from weather;

## Update a table
	update table set temp_hi= temp_hi+2 where city= "Chennai";
## Delete a table
	delete from weather where city= "Delhi";
#### or to delete all rows
	delete from weather;
## Create views
	create view myview as select city, temp_lo, temp_hi, location from weather, cities where city= name;
	select * from myview;

## Create primary key
	create table cities (
		city     varchar(80) primary key,
		location point
		);

## Create foreign key
	create table weather (
		city      varchar(80) references cities(city),
		temp_lo int,
		temp_hi   int,
		prcp      real,
		date      date
		);
## For atomic transactions
	begin;
	update accounts set balance = balance - 100.00 where name = 'Alice';
	-- etc etc
	commit;

## Save points
	savepoint my_save;
	update accounts set balance= balance- 100.00 where name= "Alice";
	rollback to my_save;

## Inherit tables
	create table person(
		name varchar(30),
		age int,
		gender varchar(1),
		address varchar(80)
		);
	create table student(
		course varchar(6),
		insti varchar(30),
		);
	



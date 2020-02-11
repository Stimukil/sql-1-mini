CREATE TABLE person(
  person_id SERIAL PRIMARY KEY,
  name TEXT,
  age INT,
  height INT,
  city TEXT,
  favorite_color TEXT
);

INSERT INTO person
(name, age, height, city, favorite_color)
VALUES
('Joe', 28, 180, 'Boise', 'green');

INSERT INTO person
(name, age, height, city, favorite_color)
VALUES
('Brian', 49, 165, 'Olympia', 'red');

INSERT INTO person
(name, age, height, city, favorite_color)
VALUES
('Chris', 32, 185, 'Newark', 'orange');

INSERT INTO person
(name, age, height, city, favorite_color)
VALUES
('Mark', 38, 167, 'Atlanta', 'yellow');

INSERT INTO person
(name, age, height, city, favorite_color)
VALUES
('Sarah', 27, 172, 'Provo', 'pink');

SELECT *
FROM person
ORDER BY height DESC;

SELECT * 
FROM person
ORDER BY height ASC;

SELECT * 
FROM person
ORDER BY age DESC;

SELECT *
FROM person
WHERE age > 20;

SELECT * 
FROM person 
WHERE age = 18;

SELECT * 
FROM person
WHERE age < 20 OR age > 30;

SELECT * 
FROM person
WHERE age != 27;

SELECT *
FROM person
WHERE favorite_color != 'red';

SELECT * 
FROM person 
WHERE favorite_color != 'red' AND favorite_color != 'blue';

SELECT *
FROM person 
WHERE favorite_color = 'orange' OR favorite_color = 'green';

SELECT * 
FROM person
WHERE favorite_color IN ('orange', 'green', 'blue');

SELECT *
FROM person 
WHERE favorite_color IN ('yellow', 'purple');

CREATE TABLE orders(
  order_id SERIAL PRIMARY KEY,
  person_id INT,
  product_name TEXT,
  product_price INT,
  quantity INT
  );

INSERT INTO orders
(person_id, product_name, product_price, quantity)
VALUES
(1, 'soap', 3.50, 5);

INSERT INTO orders
(person_id, product_name, product_price, quantity)
VALUES
(2, 'beans', 5, 2);

INSERT INTO orders
(person_id, product_name, product_price, quantity)
VALUES
(3, 'trading cards', 1, 10);

INSERT INTO orders
(person_id, product_name, product_price, quantity)
VALUES
(4, 'television', 300, 2);

INSERT INTO orders
(person_id, product_name, product_price, quantity)
VALUES
(5, 'iPhone', 125, 2);

SELECT *
FROM orders;

SELECT SUM(quantity)
FROM orders;

SELECT SUM(product_price)
FROM orders;

SELECT SUM(product_price)
FROM orders WHERE person_id = 1;

INSERT INTO artist
(name)
VALUES 
('Slipknot');

INSERT INTO artist
(name)
VALUES
('Queen');

INSERT INTO artist
(name)
VALUES
('Rage Against the Machine');

SELECT *
FROM artist 
ORDER BY name DESC LIMIT 10;

SELECT *
FROM artist
ORDER BY name LIMIT 5;

SELECT *
FROM artist
WHERE name LIKE 'Black%';

SELECT *
FROM artist
WHERE name LIKE '%Black%';

SELECT first_name, last_name
FROM employee
WHERE city = 'Calgary';

SELECT MAX(birth_date)
FROM employee;

SELECT MIN(birth_date)
FROM employee;

SELECT * FROM employee
WHERE reports_to = 2;

SELECT COUNT(*)
FROM employee
WHERE city = 'Lethbridge';

SELECT COUNT(*)
FROM invoice
WHERE billing_country = 'USA';

SELECT MAX(total)
FROM invoice;

SELECT MIN(total)
FROM invoice;

SELECT * 
FROM invoice
WHERE total > 5;

SELECT COUNT(*)
FROM invoice
WHERE total < 5;

SELECT COUNT(*)
FROM invoice
WHERE billing_state IN ('CA', 'TX', 'AZ');

SELECT AVG(total)
FROM invoice;

SELECT SUM(total)
FROM invoice;

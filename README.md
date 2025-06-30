# SQL-Joins-Inner-Left-Right-Full-

CREATE TABLE Customers (
  CustomerID INT PRIMARY KEY,
  Name VARCHAR(100),
  City VARCHAR(50)
);

CREATE TABLE Orders (
  OrderID INT PRIMARY KEY,
  CustomerID INT,
  OrderDate DATE,
  Amount DECIMAL(10,2),
  FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);

INSERT INTO Customers VALUES
(1, 'sonu', 'united kingdom'),
(2, 'labhu', 'united states'),
(3, 'mihir', 'canada'),
(4, 'tushar', 'india');

INSERT INTO Orders VALUES
(100, 1, '2025-06-10', 250.00),
(101, 2, '2025-06-11', 150.00),
(102, 2, '2025-06-15', 200.00),
(103, 4, '2025-06-16', 300.00);

SELECT c.CustomerID, c.Name, o.OrderID, o.Amount
FROM Customers c
INNER JOIN Orders o
  ON c.CustomerID = o.CustomerID;
  
SELECT c.CustomerID, c.Name, o.OrderID, o.Amount
FROM Customers c
LEFT JOIN Orders o
  ON c.CustomerID = o.CustomerID;

SELECT c.CustomerID, c.Name, o.OrderID, o.Amount
FROM Customers c
RIGHT JOIN Orders o
  ON c.CustomerID = o.CustomerID;

SELECT c.CustomerID, c.Name, o.OrderID, o.Amount
FROM Customers c
FULL JOIN Orders o
  ON c.CustomerID = o.CustomerID;


  

-- Create Authors Table
CREATE TABLE Authors (
    AuthorID INT PRIMARY KEY,
    AuthorName VARCHAR(100) NOT NULL
);

-- Create Books Table
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(255) NOT NULL,
    AuthorID INT,
    Price DECIMAL(10, 2),
    FOREIGN KEY (AuthorID) REFERENCES Authors(AuthorID)
);

-- Create Orders Table
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerName VARCHAR(100),
    BookID INT,
    Quantity INT,
    OrderDate DATE,
    FOREIGN KEY (BookID) REFERENCES Books(BookID)
);

-- Insert Sample Data
INSERT INTO Authors (AuthorID, AuthorName) VALUES (1, 'J.K. Rowling');
INSERT INTO Authors (AuthorID, AuthorName) VALUES (2, 'George R.R. Martin');

INSERT INTO Books (BookID, Title, AuthorID, Price) VALUES (1, 'Harry Potter and the Sorcerer\'s Stone', 1, 19.99);
INSERT INTO Books (BookID, Title, AuthorID, Price) VALUES (2, 'Game of Thrones', 2, 24.99);

INSERT INTO Orders (OrderID, CustomerName, BookID, Quantity, OrderDate) VALUES (1, 'Alice', 1, 2, '2025-03-20');
INSERT INTO Orders (OrderID, CustomerName, BookID, Quantity, OrderDate) VALUES (2, 'Bob', 2, 1, '2025-03-21');

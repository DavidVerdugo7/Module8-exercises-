mysql> USE exercise_3lab_8
Database changed
mysql> CREATE TABLE User (
-> ID INT PRIMARY KEY,
-> Name VARCHAR(255),
-> email VARCHAR(255),
-> Password VARCHAR(255)
-> );
Query OK, 0 rows affected (0.03 sec)

mysql> CREATE TABLE Publications (
-> postID INT PRIMARY KEY,
-> Title VARCHAR(255),
-> Description TEXT,
-> Img VARCHAR(255),
-> UserID INT,
-> FOREIGN KEY (UserID) REFERENCES User(ID)
-> );
Query OK, 0 rows affected (0.01 sec)

mysql> CREATE TABLE Coments (
-> ComentID INT PRIMARY KEY,
-> Content TEXT,
-> Date DATE,
-> UserID INT,
-> PostID INT,
-> FOREIGN KEY (UserID) REFERENCES User(ID),
-> FOREIGN KEY (PostID) REFERENCES Publications(postID)
-> );
Query OK, 0 rows affected (0.02 sec)

mysql> CREATE TABLE Likes (
-> LikeID INT PRIMARY KEY,
-> UserID INT,
-> PostID INT,
-> FOREIGN KEY (UserID) REFERENCES User(ID),
-> FOREIGN KEY (PostID) REFERENCES Publications(postID)
-> );

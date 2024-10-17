# MongoDB-Library-Management-System
## OverView:
MongoDB is a noSQL database, which means it stores data differently than traditional relational database, thus it stores data in documents instead of tables and rows

## Technologies
- MongoDB

## Project Outline
This project seeks to emphasize the use of commands to perform CRUD (CREATE, READ, UPDATE AND DELETE) operations in Mongo, it leverages both the use of creating a Database,
collections and documents along with manipulating data in the documents

## Mongosh:
Is a command-line interface that allows you to interact with MongoDB database.

#### Installations
Ensure you have MongoDB and MongoShell on your machine before proceeding or install MongoDB and MongoShell from:
* https://www.mongodb.com/try/download/community
* https://www.mongodb.com/try/download/shell

## Getting Started
* On your Windows Terminal run the following commands to start MongoDB shell by typing,This will startup your server environment:

   ```bash
      mongosh


## View Existing Databases
* On your Windows Terminal run the following commands to view existing Databases,this enables you to see how much data is stored in each database this helps in planning storage capacity and resource allocation

   ```bash
      show dbs


## Create a Database
* To create a Database named LibraryDB, run the following command, this will create and switch to LibraryDB database

   ```bash
      use LibraryDB


## Creating a Collection within LibraryDB and inserting a Document within the Document
* To create a collection within LibraryDB database named (Books) and insert a Document within it we run the following command:

   ```bash
      db.Books.insertMany([ { _id: 1, title: "1984", author_id: 1, genres: ["Dystopian", "Political Fiction"], published_year: 1949, available: true }, { _id: 2, title: "To Kill a Mockingbird", author_id: 2, genres: ["Southern Gothic", "Bildungsroman"], published_year: 1960, available: true }, { _id: 3, title: "The Great Gatsby", author_id: 3, genres: ["Tragedy"], published_year: 1925, available: true }, { _id: 4, title: "Brave New World", author_id: 4, genres: ["Dystopian", "Science Fiction"], published_year: 1932, available: true }, { _id: 5, title: "The Catcher in the Rye", author_id: 5, genres: ["Realist Novel", "Bildungsroman"], published_year: 1951, available: true }, { _id: 6, title: "Moby-Dick", author_id: 6, genres: ["Adventure Fiction"], published_year: 1851, available: true }, { _id: 7, title: "Pride and Prejudice", author_id: 7, genres: ["Romantic Novel"], published_year: 1813, available: true }, { _id: 8, title: "War and Peace", author_id: 8, genres: ["Historical Novel"], published_year: 1869, available: true }, { _id: 9, title: "Crime and Punishment", author_id: 9, genres: ["Philosophical Novel"], published_year: 1866, available: true }, { _id: 10, title: "The Hobbit", author_id: 10, genres: ["Fantasy"], published_year: 1937, available: true } ]}




# CRUD Operations On Books Collections
* To Read Document data within a Books collection we run the following command:

   ```bash
      db.Books.find()



* Finding a specific book by Title, run the following command:

   ```bash
      db.Books.find({title: "To Kill a Mockingbird"})

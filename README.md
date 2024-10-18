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


## Creating a Collection within LibraryDB and inserting a Document within the Document
* To create another collection within LibraryDB database named (Authors) and insert a Document within it we run the following command:

   ```bash
      db.Authors.insertMany([ { _id: 1, name: "George Orwell", nationality: "British", birth_year: 1903, death_year: 1950 }, { _id: 2, name: "Harper Lee", nationality: "American", birth_year: 1926, death_year: 2016 }, { _id: 3, name: "F. Scott Fitzgerald", nationality: "American", birth_year: 1896, death_year: 1940 }, { _id: 4, name: "Aldous Huxley", nationality: "British", birth_year: 1894, death_year: 1963 }, { _id: 5, name: "J.D. Salinger", nationality: "American", birth_year: 1919, death_year: 2010 }, { _id: 6, name: "Herman Melville", nationality: "American", birth_year: 1819, death_year: 1891 }, { _id: 7, name: "Jane Austen", nationality: "British", birth_year: 1775, death_year: 1817 }, { _id: 8, name: "Leo Tolstoy", nationality: "Russian", birth_year: 1828, death_year: 1910 }, { _id: 9, name: "Fyodor Dostoevsky", nationality: "Russian", birth_year: 1821, death_year: 1881 }, { _id: 10, name: "J.R.R. Tolkien", nationality: "British", birth_year: 1892, death_year: 1973 } ]


## Creating a Collection within LibraryDB and inserting a Document within the Document
* To create another collection within LibraryDB database named (Patrons) and insert a Document within it we run the following command:

   ```bash
      db.Patrons.insertMany([ { _id: 1, name: "Alice Johnson", email: "alice@example.com", borrowed_books: [] }, { _id: 2, name: "Bob Smith", email: "bob@example.com", borrowed_books: [1, 2] }, { _id: 3, name: "Carol White", email: "carol@example.com", borrowed_books: [] }, { _id: 4, name: "David Brown", email: "david@example.com", borrowed_books: [3] }, { _id: 5, name: "Eve Davis", email: "eve@example.com", borrowed_books: [] }, { _id: 6, name: "Frank Moore", email: "frank@example.com", borrowed_books: [4, 5] }, { _id: 7, name: "Grace Miller", email: "grace@example.com", borrowed_books: [] }, { _id: 8, name: "Hank Wilson", email: "hank@example.com", borrowed_books: [6] }, { _id: 9, name: "Ivy Taylor", email: "ivy@example.com", borrowed_books: [] }, { _id: 10, name: "Jack Anderson", email: "jack@example.com", borrowed_books: [7, 8] } ])



## Switch to LibraryBD to add another collection within libraryDB
* Run the follwoing commands to switch from collections to db

   ```bash
      use LibraryDB



## Finding Books by a Specific Author
* To find Books in relation to a specific Author, write this command

   ```bash
         use LibraryDB
         db.Books.find({ author_id: 5 }).pretty()




# CRUD Operations On Books Collections
* To Read Document data within a Books collection we run the following command:

   ```bash
       db.Books.find()




* Finding a specific book by Title, run the following command:

      ```bash
          db.Books.find({title: "To Kill a Mockingbird"})


* Update a specific book by _id, run the following command:

      ```bash
          db.Books.updateOne({_id:3}, {$set:{available:"booked"}})



* Adding a Genre to a Book (Using $addToSet) (_id: 8) Books collection we run the following command:

   ```bash
       db.Books.updateOne({_id:8},{$addToSet:{genres:'Fiction'}})



* Adding a borrowed book to a patron’s record (_id: 5) we run the following command:

   ```bash
       db.Patrons.updateOne({_id:5},{$addToSet:{borrowed_books:2}})




* Delete an Author by (_id: 3) we run the following command:

   ```bash
       db.Books.deleteOne({_id:3})


* Finding  Books Published After 1950 (Using $gt) we run the following command:

   ```bash
        db.Books.find({published_year:{$gt:1950}})


* Find All American Authors (Using $eq) we run the following command:

   ```bash
       db.Authors.find({nationality:{$eq:'American'}})


* Set All Books To Available (Using $set) we run the following command:

   ```bash
       db.Books.updateMany({},{$set:{available: false}})


* Find All Books That Are Available And Published After 1950 we run the following command:

   ```bash
       db.Books.find({available:false, published_year:{$gt:1950}})



* Find authors whose names contain "George" (Using $regex) we run the following command:

   ```bash
       db.Authors.find({name:{$regex:"George"}})


* Find authors whose names contain "George" (Using $regex) we run the following command:

   ```bash
       db.Authors.find({name:{$regex:"George"}})



* Increment the published year of "1869" by 1 (Using $inc) we run the following command:

   ```bash
        db.Books.updateOne({published_year:1869},{$inc:{published_year:1}})


# Contacts
Email: nhlakaniphoradebe337@gmail.com
github: AlsonAfrica

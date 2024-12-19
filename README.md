Book Management System
A RESTful API service built with Go for managing books, featuring complete CRUD operations and MySQL database integration.
Project Structure
Copy├───.dist
├───.vscode
├───cmd
│   └───main
└───pkg
    ├───config
    ├───controllers
    ├───models
    ├───routes
    └───utils
Technologies Used

Go 1.21.5
Gorilla Mux (HTTP router and URL matcher)
GORM (ORM library for MySQL)
MySQL Database

Prerequisites

Go 1.21.5 or higher
MySQL server
Git

Installation & Setup

Clone the repository:

bashCopygit clone https://github.com/Sushanta175/Book-Management-System.git
cd Book-Management-System

Install dependencies:

bashCopygo mod download

Configure MySQL connection:


Open pkg/config/app.go
Modify the database connection string according to your MySQL setup:

goCopy"root:root@mysql@tcp(localhost:3306)/simplerest?charset=utf8&parseTime=True&loc=Local"

Run the application:

bashCopygo run cmd/main/main.go
The server will start on port 9010.
API Endpoints
MethodEndpointDescriptionGET/book/Get all booksGET/book/{bookId}Get a specific book by IDPOST/book/Create a new bookPUT/book/{bookId}Update a bookDELETE/book/{bookId}Delete a book
API Usage
Create a Book
bashCopyPOST /book/
Content-Type: application/json

{
    "name": "The Go Programming Language",
    "author": "Alan A. A. Donovan",
    "publication": "Addison-Wesley"
}
Get All Books
bashCopyGET /book/
Get Book by ID
bashCopyGET /book/1
Update a Book
bashCopyPUT /book/1
Content-Type: application/json

{
    "name": "Updated Book Name",
    "author": "Updated Author Name",
    "publication": "Updated Publication"
}
Delete a Book
bashCopyDELETE /book/1
Data Model
Book model structure:
goCopytype Book struct {
    gorm.Model
    Name        string `json:"name"`
    Author      string `json:"author"`
    Publication string `json:"publication"`
}
Error Handling
The API includes basic error handling for:

Invalid book IDs
Database connection issues
JSON parsing errors

Contributing

Fork the repository
Create your feature branch (git checkout -b feature/amazing-feature)
Commit your changes (git commit -m 'Add some amazing feature')
Push to the branch (git push origin feature/amazing-feature)
Open a Pull Request

License
This project is licensed under the MIT License - see the LICENSE file for details.
Here's the raw text of the README.md file:

# Book Management System

A RESTful API service built with Go for managing books, featuring complete CRUD operations and MySQL database integration.

## Project Structure
```
├───.dist
├───.vscode
├───cmd
│   └───main
└───pkg
    ├───config
    ├───controllers
    ├───models
    ├───routes
    └───utils
```

## Technologies Used
- Go 1.21.5
- Gorilla Mux (HTTP router and URL matcher)
- GORM (ORM library for MySQL)
- MySQL Database

## Prerequisites
- Go 1.21.5 or higher
- MySQL server
- Git

## Installation & Setup

1. Clone the repository:
```bash
git clone https://github.com/Sushanta175/Book-Management-System.git
cd Book-Management-System
```

2. Install dependencies:
```bash
go mod download
```

3. Configure MySQL connection:
- Open `pkg/config/app.go`
- Modify the database connection string according to your MySQL setup:
```go
"root:root@mysql@tcp(localhost:3306)/simplerest?charset=utf8&parseTime=True&loc=Local"
```

4. Run the application:
```bash
go run cmd/main/main.go
```

The server will start on port 9010.

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/book/` | Get all books |
| GET | `/book/{bookId}` | Get a specific book by ID |
| POST | `/book/` | Create a new book |
| PUT | `/book/{bookId}` | Update a book |
| DELETE | `/book/{bookId}` | Delete a book |

## API Usage

### Create a Book
```bash
POST /book/
Content-Type: application/json

{
    "name": "The Go Programming Language",
    "author": "Alan A. A. Donovan",
    "publication": "Addison-Wesley"
}
```

### Get All Books
```bash
GET /book/
```

### Get Book by ID
```bash
GET /book/1
```

### Update a Book
```bash
PUT /book/1
Content-Type: application/json

{
    "name": "Updated Book Name",
    "author": "Updated Author Name",
    "publication": "Updated Publication"
}
```

### Delete a Book
```bash
DELETE /book/1
```

## Data Model

Book model structure:
```go
type Book struct {
    gorm.Model
    Name        string `json:"name"`
    Author      string `json:"author"`
    Publication string `json:"publication"`
}
```

## Error Handling
The API includes basic error handling for:
- Invalid book IDs
- Database connection issues
- JSON parsing errors

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.
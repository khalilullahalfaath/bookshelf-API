
# Bookshelf API

The Bookshelf API is a RESTful API that allows users to manage a collection of books. This API provides essential functionality to store, retrieve, update, and delete books using HTTP requests. Built using Node.js with Hapi framework, the API runs on port 9000.

## Features

The Bookshelf API offers the following features:

- **Book Storage**: Users can store book data by making a POST request to the API. The API expects a JSON object with the following properties:
  - `name` (string): The name of the book.
  - `year` (number): The year of publication.
  - `author` (string): The name of the book's author.
  - `summary` (string): A summary or description of the book.
  - `publisher` (string): The name of the book's publisher.
  - `pageCount` (number): The total number of pages in the book.
  - `readPage` (number): The number of pages the user has read.
  - `reading` (boolean): Indicates whether the user is currently reading the book.

- **Book Retrieval**: Users can retrieve a list of all books in the bookshelf by sending a GET request to the API. The API responds with an array of book objects, each containing the book's details. The following query parameters are supported:

  - `name` (string, optional): Filters the books by name. Case-insensitive. Example: `/books?name=dicoding` returns books with names containing "dicoding".
  - `reading` (number, optional): Filters the books by reading status. Set to `0` to retrieve books that are not being read (reading: false), and `1` to retrieve books that are being read (reading: true). If not provided, all books will be returned.
  - `finished` (number, optional): Filters the books by finished status. Set to `0` to retrieve books that are not finished (finished: false), and `1` to retrieve books that are finished (finished: true). If not provided, all books will be returned.

## Getting Started

To run the Bookshelf API, follow these steps:

1. Clone the repository to your local machine.
2. Install the required dependencies by running `npm install` in the terminal.
3. Start the API server by running `npm run start` or `node start` in the terminal.
4. The API will be accessible at `http://localhost:9000`.

Please ensure that you have Node.js and npm installed on your machine before proceeding.

## API Endpoints

The Bookshelf API provides the following endpoints for interacting with the API:

- `POST /books`: Add a new book to the bookshelf.
- `GET /books`: Retrieve a list of all books in the bookshelf. Supports query parameters for filtering.
- `GET /books/{bookId}`: Get the details of a specific book by its ID.
- `PUT /books/{bookId}`: Update the information of a book by its ID.
- `DELETE /books/{bookId}`: Delete a book from the bookshelf by its ID.

## Example Usage

Here are some examples of how to use the Bookshelf API:
- To add a new book:
  ```
  POST /books
  Body: {
    "name": "Harry Potter and the Sorcerer's Stone",
    "year": 1997,
    "author": "J.K. Rowling",
    "summary": "The first book in the Harry Potter series.",
    "publisher": "Bloomsbury Publishing",
    "pageCount": 320,
    "readPage": 120,
    "reading": true
  }
  ```
  
- To retrieve all books:
  ```
  GET /books
  ```

- To retrieve books with a specific name:
  ```
  GET /books?name=dicoding
  ```

- To retrieve books that are currently being read:
  ```
  GET /books?reading=1
  ```

- To retrieve books that are finished:
  ```
  GET /books?finished=1
  ```
  Please note that you should replace `dicoding` with the desired name and use `0` or `1` for the `reading` and `finished` parameters.
  
- To update the information of a book with ID 123:
  ```
  PUT /books/123
  Body: {
  "name": "Harry Potter and the Chamber of Secrets",
  "year": 1998,
  "author": "J.K. Rowling",
  "summary": "The second book in the Harry Potter series.",
  "publisher": "Bloomsbury Publishing",
  "pageCount": 352,
  "readPage": 200,
  "reading": true
  }
  ```
- To delete a book with ID 123:
  ```
  DELETE /books/123
  ```
  Please note that you should replace `123` with the actual ID of the book you want to interact with.

Feel free to explore and utilize the Bookshelf API according to your requirements. Enjoy managing your book collection!


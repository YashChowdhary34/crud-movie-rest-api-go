# CRUD Movie REST API in Go

This repository contains a RESTful API built with Go, enabling Create, Read, Update, and Delete (CRUD) operations for managing a collection of movies.

## Features

- **Retrieve All Movies**: Fetch a list of all movies.
- **Retrieve a Single Movie**: Fetch details of a specific movie by its ID.
- **Create a New Movie**: Add a new movie to the collection.
- **Update an Existing Movie**: Modify details of an existing movie by its ID.
- **Delete a Movie**: Remove a movie from the collection by its ID.

## Project Structure

- `main.go`: The main application file containing the API implementation.
- `go.mod` and `go.sum`: Go modules managing dependencies.
- `movies-crud.exe`: Compiled executable of the application.

## Getting Started

### Prerequisites

- [Go](https://golang.org/dl/) installed on your system.

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/YashChowdhary34/crud-movie-rest-api-go.git
   cd crud-movie-rest-api-go
   ```

2. **Install Dependencies**:
   ```bash
   go mod tidy
   ```

### Running the Application

Start the server using:
```bash
go run main.go
```
The server will run on `http://localhost:8000`.

## API Endpoints

- **Get All Movies**
  - **Endpoint**: `GET /movies`
  - **Description**: Retrieves a list of all movies.
  - **Response**:
    ```json
    [
      {
        "id": "1",
        "isbn": "438227",
        "title": "Movie One",
        "director": {
          "firstname": "John",
          "lastname": "Doe"
        }
      },
      {
        "id": "2",
        "isbn": "454555",
        "title": "Movie Two",
        "director": {
          "firstname": "Steve",
          "lastname": "Smith"
        }
      }
    ]
    ```

- **Get a Single Movie**
  - **Endpoint**: `GET /movies/{id}`
  - **Description**: Retrieves details of a specific movie by its ID.
  - **Response**:
    ```json
    {
      "id": "1",
      "isbn": "438227",
      "title": "Movie One",
      "director": {
        "firstname": "John",
        "lastname": "Doe"
      }
    }
    ```

- **Create a New Movie**
  - **Endpoint**: `POST /movies`
  - **Description**: Adds a new movie to the collection.
  - **Request Body**:
    ```json
    {
      "isbn": "438227",
      "title": "New Movie",
      "director": {
        "firstname": "Jane",
        "lastname": "Doe"
      }
    }
    ```
  - **Response**:
    ```json
    {
      "id": "3",
      "isbn": "438227",
      "title": "New Movie",
      "director": {
        "firstname": "Jane",
        "lastname": "Doe"
      }
    }
    ```

- **Update an Existing Movie**
  - **Endpoint**: `PUT /movies/{id}`
  - **Description**: Updates details of an existing movie by its ID.
  - **Request Body**:
    ```json
    {
      "isbn": "438227",
      "title": "Updated Movie",
      "director": {
        "firstname": "Jane",
        "lastname": "Doe"
      }
    }
    ```
  - **Response**:
    ```json
    {
      "id": "3",
      "isbn": "438227",
      "title": "Updated Movie",
      "director": {
        "firstname": "Jane",
        "lastname": "Doe"
      }
    }
    ```

- **Delete a Movie**
  - **Endpoint**: `DELETE /movies/{id}`
  - **Description**: Removes a movie from the collection by its ID.
  - **Response**:
    ```json
    {
      "message": "Movie deleted"
    }
    ```

## Technologies Used

- **Go**: Programming language.
- **Gorilla Mux**: HTTP router and URL matcher for building Go web servers.

## Future Work

- **Database Integration**: Add persistent data storage using a database like PostgreSQL or MongoDB.
- **Authentication**: Implement user authentication and authorization.
- **Unit Testing**: Add comprehensive unit and integration tests.
- **Advanced Querying**: Support filtering, sorting, and pagination for movie listings.
- **Deployment**: Deploy the application using Docker or a cloud service like AWS or GCP.


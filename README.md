# Go Movies CRUD API

## Project Overview

This project is a simple **CRUD (Create, Read, Update, Delete) API** built with Golang. It allows users to manage a list of movies, with the ability to add new movies, view all or specific movies, update movie details, and delete movies. The API is a practical example for beginners to understand how to build RESTful services using Go.

## Features

- **Create Movie**: Add a new movie to the list.
- **Read Movies**: Retrieve the list of all movies or a specific movie by ID.
- **Update Movie**: Modify the details of an existing movie.
- **Delete Movie**: Remove a movie from the list.

## Project Structure

The project is structured as follows:

```plaintext
├── main.go          # The main file containing the application logic
├── go.mod           # Go module file
└── README.md        # Project documentation (this file)
```
## Movie Structure

Each movie has the following attributes:

- ID: A unique identifier for the movie.
-  ISBN: A unique identifier for the movie (like a book's ISBN).
-  Title: The title of the movie.
-  Director: A nested structure containing the first and last name of the director.

The Movie and Director structures are defined as:
```bash
type Movie struct {
    ID       string    `json:"id"`
    Isbn     string    `json:"isbn"`
    Title    string    `json:"title"`
    Director *Director `json:"director"`
}

type Director struct {
    Firstname string `json:"firstname"`
    Lastname  string `json:"lastname"`
}
```
## Getting Started
### Prerequisites

To run this project, you will need:

-   Go: Install Go from the official website.
-   Git: Install Git from the official website.

#### Installation

1. Clone the Repository:
```bash
git clone https://github.com/Githaiga22/CRUD-API-with-Golang.git
cd CRUD-API-with-Golang
```
2. Install Dependencies:
The project uses the gorilla/mux package for routing. Run the following command to install it:
```bash
go get -u github.com/gorilla/mux
```
3. Run the Application:
Start the server by running:
```bash
go run main.go
```
The server will start on http://localhost:8000.
### API Endpoints

The following endpoints are available for interacting with the API:

- GET /movies: Retrieve the list of all movies.
-   GET /movies/{id}: Retrieve a specific movie by ID.
-   POST /movies: Add a new movie.
-   PUT /movies/{id}: Update an existing movie by ID.
-   DELETE /movies/{id}: Delete a movie by ID.

#### Example Requests

Here are some example cURL commands to interact with the API:

-  Get All Movies:
```bash
curl -X GET http://localhost:8000/movies
```
- Get a Specific Movie:
```bash
curl -X GET http://localhost:8000/movies/1
```
- Create a New Movie:
```bash
curl -X POST -H "Content-Type: application/json" \
-d '{"isbn":"123456","title":"New Movie","director":{"firstname":"John","lastname":"Doe"}}' \
http://localhost:8000/movies
```
- Update a Movie:
```bash
curl -X PUT -H "Content-Type: application/json" \
-d '{"isbn":"654321","title":"Updated Movie","director":{"firstname":"Jane","lastname":"Smith"}}' \
http://localhost:8000/movies/1
```
- Delete a Movie:
```bash
curl -X DELETE http://localhost:8000/movies/1
```

### Project Details

- Language: Go (Golang)
-   Framework: Gorilla Mux (for routing)
 -  Version Control: Git

### Future Enhancements

-   Authentication: Adding user authentication for more secure API access.
-  Database Integration: Replacing the in-memory storage with a database (e.g., PostgreSQL, MongoDB).
- Dockerization: Containerizing the application using Docker for easier deployment.

### Contributing

Contributions are welcome! Please open an issue or submit a pull request for any bugs or feature requests.

Thank you for using the Go Movies CRUD API! If you have any questions or need further assistance, feel free to reach out.
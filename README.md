# Project: GREENLIGHT

<details>
<summary>Intro</summary>
<br>
*Greenlight* -- a JSON API for retrieving and managing information about movies.

*Greenligh* API endpoints and actions:
|Method|URL Pattern|Handler|Action|
|---|---|---|
|GET|/v1/healthcheck|healthcheckHandler|Show application health and version information|
|GET|/v1/movies|listMoviesHandler|Show the details of all movies|
|POST|/v1/movies|createMovieHandler|Create a new movie|
|GET|/v1/movies/:id|showMovieHandler|Show the details of a specific movie|
|PUT|/v1/movies/:id|editMovieHandler|Update the details of a specific movie|
|DELETE|/v1/movies/:id|deleteMovieHandler|Delete a specific movie|
|POST|/v1/users/|---|Register a new user|
|PUT|/v1/users/activated|---|Activate a specific user|
|PUT|/v1/users/password|---|Update the password for a specific user|
|POST|/v1/tokens/authentication|---|Generate a new authentication token|
|POST|/v1/tokens/password-reset|---|Generate a new password-reset token|
|GET|/debug/vars|---|Display applicatoin metrics|

</details>

<details>
<summary>Project directory structure</summary>
<br>
.
├── bin
├── cmd
│   └── api
│       └── main.go
├── go.mod
├── internal
├── Makefile
├── migrations
└── remote

- The `bin` directory contains compiled application binaries, ready for deployment to a production server.
- The `cmd/api` directory contains the application-specific code for our *Greenlight* API application. Includes code for running the server, reading and writing HTTP requests, and managing authentication.
- The `internal` directory contains various ancillary packages used by our API: the code for interacting with our database, data validation, sending emails etc. Any code, which is not application-specific and can potentially be reused.
- The `migrations` direcory contains the SQL migration files for our database.
- The `remote` directory contains the configuration files and setup scripts for our production server.
- The `go.mod` file declares our project dependencies, version and module path.
- The `Makefile` contains *recipes* for automating common administrative tasks -- auditing Go code, building binaries, and executing database migrations.

</details>

# Simple Go Server

A minimal HTTP server written in Go that serves static files and handles a simple form submission.

## Features

- Serves static HTML files from the `static/` folder
- `/hello` — returns a greeting (404 for any other path)
- `/form` — handles POST requests from the form and prints submitted data

## Project Structure

```
your-project/
├── main.go
└── static/
    ├── index.html
    └── form.html
```

## Requirements

- [Go](https://go.dev/dl/) installed (1.16+ recommended)

## Setup

1. Clone or download this project.
2. Make sure `index.html` and `form.html` are inside the `static/` folder, next to `main.go`.
3. Initialize the Go module (only needed once):

   ```bash
   go mod init server
   ```

## Running the Server

```bash
go run main.go
```

You should see:

```
Starting Server at port 8080
```

## Usage

| URL                              | Description                          |
|-----------------------------------|---------------------------------------|
| `http://localhost:8080/`          | Serves `index.html`                  |
| `http://localhost:8080/form.html` | Serves the form page                 |
| `http://localhost:8080/form`      | Handles POST submissions from the form |
| `http://localhost:8080/hello`     | Returns a simple greeting             |

## Building a Binary

To compile the server into a standalone executable:

```bash
go build -o server main.go
./server
```

## Notes

- Run the server from the directory that contains the `static/` folder, since the file path is relative.
- If port `8080` is already in use, change `:8080` in `main.go` to another port (e.g. `:8081`).
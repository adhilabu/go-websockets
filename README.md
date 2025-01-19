# Go Pulsar Websockets

This is a sample Go project demonstrating the use of [Apache Pulsar](https://pulsar.apache.org/) with WebSockets. It includes a modular structure and provides examples of how to configure, interact with Pulsar, and set up a basic WebSocket service.

---

## Features

- Integration with Apache Pulsar for messaging.
- WebSocket-based server implementation.
- Centralized configuration using environment variables.
- Modular and extensible architecture.
- Sample configuration and schema examples included.

---

## Prerequisites

Ensure you have the following installed:

- **Go**: Version 1.20 or later ([Install Go](https://golang.org/doc/install)).
- **Apache Pulsar**: Running Pulsar instance ([Download Pulsar](https://pulsar.apache.org/download)).
- **Git**: For cloning the repository.

---

## Project Structure

```plaintext
├── src/
│   ├── cmd/              # Entry point for the application.
│   ├── core/             # Core components (config, database, etc.).
│   └── pkg/ws/           # WebSocket handlers and router.
├── go.mod                # Go module configuration.
├── go.sum                # Dependency locks.
├── README.md             # Project documentation.
└── .gitignore            # Ignored files for version control.
```

---

## Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/adhilabu/go-websockets.git
cd go-websockets
```

### Step 2: Install Dependencies

Use `go mod` to download and install required dependencies:

```bash
go mod tidy
```

### Step 3: Configure Environment

1. Create a `.env` file in the project root with the following content:

    ```env
    PULSAR_URL=pulsar://localhost:6650
    PROJECT_PORT=8080
    DB_NAME=my_database
    DB_PORT=5432
    DB_PASSWORD=your_password
    DB_USER=your_username
    DB_HOST=localhost
    DB_SSLMODE=disable
    MASTER_DB_NAME=master_db
    INIT_ONLY_THESE_CUSTOMER_DBS=db1,db2,db3
    ```

2. Adjust the values according to your setup.

---

## Core Package Details

The `core` package is responsible for managing the application’s configuration by loading environment variables. The `LoadEnv` function ensures a singleton pattern to initialize the configuration.

### Environment Variables

- **PULSAR_URL**: The URL of the Pulsar instance.
- **PROJECT_PORT**: The port the project runs on.
- **DB_NAME**: Name of the database.
- **DB_PORT**: Database port (integer).
- **DB_PASSWORD**: Password for the database.
- **DB_USER**: Database username.
- **DB_HOST**: Host address for the database.
- **DB_SSLMODE**: SSL mode for the database connection.
- **MASTER_DB_NAME**: Name of the master database.
- **INIT_ONLY_THESE_CUSTOMER_DBS**: Comma-separated list of customer databases to initialize.
---

## Step 4: Run the Application

Start the application:

```bash
go run src/cmd/main.go
```

---

## Contribution

Feel free to open issues or submit pull requests for improvements. All contributions are welcome!

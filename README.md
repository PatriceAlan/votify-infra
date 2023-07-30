# votify-infra
As a DevOps engineer, this project involves building an infrastructure to host a voting poll application. The application consists of several elements, including Poll (a Flask Python web application), a Redis queue, Worker (a Java application), PostgreSQL database, and Result (a Node.js web application).

## Application Architecture

The application architecture is as follows:

- **Poll**: A Flask Python web application that gathers votes and pushes them into a Redis queue.
- **Redis**: A Redis queue that holds the votes sent by the Poll application, waiting for them to be consumed by the Worker.
- **Worker**: A Java application that consumes votes from the Redis queue and stores them into a PostgreSQL database.
- **PostgreSQL**: A PostgreSQL database that persistently stores the votes stored by the Worker.
- **Result**: A Node.js web application that fetches votes from the database and displays the results.

## Getting Started

To set up and run the voting poll application, follow the steps below.

### Prerequisites

- Docker and Docker Compose installed on your system.

### Step 1: Clone the Repository

```bash
git clone https://github.com/PatriceAlan/votify-infra.git
cd votify-infra
```

### Step 2: Create .env File

Create a `.env` file in the root directory of the project and add the following environment variables:

```
POSTGRES_PASSWORD=???
RESTART_POLICY=???
```

Replace `your_postgres_username` and `your_postgres_password` with your desired PostgreSQL credentials.

### Step 3: Build Docker Images

```bash
docker-compose build
```

### Step 4: Start the Services

```bash
docker-compose up -d
```

The infrastructure will start running the Poll, Redis, Worker, PostgreSQL, and Result services.

### Step 5: Access the Applications

- Poll: Access the Poll application at http://localhost:5000.
- Result: Access the Result application at http://localhost:5001.

## Stopping the Application

To stop and remove the running containers, use the following command:

```bash
docker-compose down
```

## Health Checks

Each service in the infrastructure has a health check to ensure it is running correctly. The health checks are automatically configured by Docker Compose.

## Troubleshooting

If you encounter any issues during setup or while running the application, refer to the Troubleshooting section in the documentation.

## Contributing

We welcome contributions to improve the voting poll application. Feel free to open pull requests and report issues on the repository.

## License

This project is licensed under the [MIT License](LICENSE).

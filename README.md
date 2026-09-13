# ITCS6190-H3-tsonkusa
# Execution Steps

## 1. Verify Docker Installation

Make sure Docker Desktop is running.

```bash
docker --version
```

## 2. Pull the PostgreSQL Image

```bash
docker pull postgres:16
```

## 3. Start the PostgreSQL Container

```bash
docker run -d -p 5432:5432 --name postgres1 -e POSTGRES_PASSWORD=pass12345 postgres:16
```

## 4. Access the PostgreSQL Container

```bash
docker exec -it postgres1 bash
```

Connect to PostgreSQL:

```bash
psql -d postgres -U postgres
```

Exit PostgreSQL:

```bash
\q
```

Exit the container:

```bash
exit
```

## 5. Stop and Remove the PostgreSQL Container

```bash
docker stop postgres1 && docker rm postgres1
```

## 6. Build and Run the Flask and Redis Containers

From the project directory, run:

```bash
docker compose up
```

## 7. Test the Application

Open the following URL in a browser:

```text
http://localhost:8000
```

Refresh the page multiple times to verify that the visit counter increases.

## 8. Verify the Containers

Open Docker Desktop and confirm that both the Flask web container and Redis container are running.

## 9. Stop the Application

Press:

```text
CTRL+C
```

Then run:

```bash
docker compose down
```
## What I Learned

In this hands-on exercise, I learned how containers isolate an application's dependencies and runtime environment. I first used Docker commands to pull and run a PostgreSQL image and access the database inside its container. I then containerized a Flask application with a Dockerfile and used Docker Compose to run the Flask web service together with Redis. The Flask container connects to Redis using the Compose service name `redis`, and Redis keeps the visit counter increasing across browser refreshes. I also learned how to inspect container logs in Docker Desktop, troubleshoot Docker CLI and Python syntax errors, and stop the stack cleanly with `docker compose down`.

## Evidence

The evidence document contains the expanded Docker Desktop stack, browser output showing the counter increasing, and the repository URL:

[View the Hands-On 3 Screenshots PDF](H3_itcs6190-tsonkusa.pdf)


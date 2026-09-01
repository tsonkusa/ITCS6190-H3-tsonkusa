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

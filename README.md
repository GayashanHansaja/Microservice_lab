# Microservice Lab

A simple microservices demo built with multiple languages and orchestrated with Docker Compose.

## Services

- **API Gateway**: Nginx (`api-gateway/nginx.conf`) exposed on `http://localhost:8080`
- **Item Service**: Node.js + Express + PostgreSQL
- **Order Service**: Go + Gin + PostgreSQL
- **Payment Service**: Python + Flask + PostgreSQL
- **Database**: PostgreSQL with databases initialized by `db/init.sql`

## Architecture

The API Gateway routes requests to backend services:

- `/items` -> item-service
- `/orders` -> order-service
- `/payments` -> payment-service
- `/health` -> gateway health endpoint

Each service runs on port `8080` internally and uses PostgreSQL via environment variables.

## Prerequisites

- Docker
- Docker Compose

3. Start the stack:

```bash
docker compose up --build
```

4. Access the API gateway at `http://localhost:8080`.

## Example Endpoints

- `GET /items`
- `POST /items`
- `GET /orders`
- `POST /orders`
- `GET /payments`
- `POST /payments/process`

A Postman collection is included: `Microservice_Lab.postman_collection.json`.

# Microservices Docker Compose Project (Skill Test 1: Cloud and Containers)

---

## Overview

This project demonstrates a **microservices architecture** using Node.js, fully containerized with Docker and orchestrated using Docker Compose.

### Services

* User Service → `3000`
* Product Service → `3001`
* Order Service → `3002`
* Gateway Service → `3003`

---

## Architecture

```text
Client → Gateway Service → (User | Product | Order Services)
```

---

## Project Structure

```bash
skilltest1/
├── submissions/
│   ├── user-service/
│   ├── product-service/
│   ├── order-service/
│   ├── gateway-service/
├── docker-compose.yml
└── README.md
└── .gitignore
```

---

## Tech Stack

* Node.js
* Docker
* Docker Compose
* Express.js

---

## Getting Started

### Prerequisites

* Docker
* Docker Compose

Check installation:

```bash
docker --version
docker-compose --version
```

![Browser Users](./screenshots/docker-version.png)

---

### Run the Project

```bash
docker-compose up --build
```

![Docker Compose](./screenshots/docker-compose.png)

---

### Verify Running Containers

```bash
docker ps
```

---

## Service Endpoints

| Service         | URL                   |
| --------------- | --------------------- |
| User Service    | http://localhost:3000 |
| Product Service | http://localhost:3001 |
| Order Service   | http://localhost:3002 |
| Gateway Service | http://localhost:3003 |

---

## Testing

### Browser

Open:

```
http://localhost:3000
http://localhost:3001
http://localhost:3002
http://localhost:3003
```

![users](./screenshots/browser-users.png)
![orders](./screenshots/browser-orders.png)
![products](./screenshots/browser-products.png)
![api](./screenshots/browser-users-api.png)
### cURL

```bash
curl http://localhost:3000
curl http://localhost:3001
curl http://localhost:3002
curl http://localhost:3003
```

---

![users](./screenshots/curl-users.png)
![orders](./screenshots/curl-prodcts.png)
![products](./screenshots/curl-orders.png)
![api](./screenshots/curl-api.png)

## Docker Setup

### Dockerfiles

Each service:

* Uses Node.js base image
* Installs dependencies
* Exposes port
* Runs with `node app.js`

---

### Docker Compose

* Multi-container orchestration
* Shared bridge network
* Service dependency handling

---

## Screenshots

### Docker Compose Running

![Docker Compose](./screenshots/docker-compose.png)

### Running Containers

![Docker PS](./screenshots/docker-ps.png)

### Browser Output

![Browser Users](./screenshots/browser-users.png)
![Browser Products](./screenshots/browser-products.png)
![Browser Orders](./screenshots/browser-orders.png)
![Add Orders](./screenshots/add-orders.png)

### Project Structure

![Structure](./screenshots/structure.png)

### Postman Collection

![Structure](./screenshots/postman-collection.png)
---

## Troubleshooting

### Port already in use

```bash
lsof -i :3000
kill -9 <PID>
```

---

### Check logs

```bash
docker-compose logs
```

---

### Rebuild containers

```bash
docker-compose down
docker-compose up --build
```

---

## Improvements (Future Scope)

* API Gateway routing
* Authentication (JWT)
* Logging & Monitoring

---

## Author

**Avinash Sain**
GitHub: https://github.com/Avinashsain
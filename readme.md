# Microservice Event-Driven Platform
Distributed microservices architecture in Go using gRPC and RPC for inter-service communication. Integrated RabbitMQ for asynchronous message brokering and PostgreSQL/MongoDB for persistent data storage. Containerized all services with Docker and orchestrated deployments using Kubernetes for scalability and resilience. Utilized MailHog for email testing and Make for streamlined build and deployment automation.

---

## System Design Diagram

<p align="center"><img src='/files/images/system_diagram.png' alt='System Design Diagram' /></p>

---

## Features and Tools

- **JSON-based communication between frontend and backend for simple and structured API interaction**
- **Authentication and authorization service for managing users and secure access to resources**
- **Centralized broker service acting as the API gateway and router between all microservices using [Chi](https://github.com/go-chi/chi)**
- **Event-driven microservice architecture enabling independent, scalable, and modular service design**
- **[gRPC](https://github.com/grpc/grpc-go) communication for fast, type-safe inter-service messaging**
- **RPC mechanism for synchronous communication between microservices**
- **Asynchronous messaging and task handling using [RabbitMQ](https://github.com/rabbitmq/amqp091-go) as the message broker**
- **Background listener service that consumes [RabbitMQ](https://github.com/rabbitmq/amqp091-go) events and triggers business workflows**
- **Logging service for collecting and storing application logs in [MongoDB](https://github.com/mongodb/mongo-go-driver) for observability**
- **Mail service for handling transactional emails and notifications using [MailHog](https://github.com/mailhog/MailHog) in development**
- **[PostgreSQL](https://github.com/postgres/postgres) as the main relational database for authentication and persistent data storage**
- **[MongoDB](https://github.com/mongodb/mongo-go-driver) as the NoSQL database for structured logging and analytics**
- **[Docker](https://github.com/docker/compose) for containerizing all microservices ensuring isolated and reproducible environments**
- **[Kubernetes](https://github.com/kubernetes/kubernetes) for orchestration, scaling, and management of all containerized services**
- **Makefile for automating build, test, and deployment processes across services**

---

## How to run?

### Using Docker and Make

cd to the project directory and run this command:

```bash
make up_build
```

this will brings up all services, after that used this command to start the front end:

```bash
make start
```

if you want to stop the project, down all services using this command:

```bash
make down
```

after that, to stop the front end, use this command:

```bash
make stop
```

### Using Kubernetes

cd to the project directory and run this command:

```bash
kubectl apply -f kubernetes
```
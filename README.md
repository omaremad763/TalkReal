# TalkReal

> A learning-driven real-time chat application built with .NET 9, Angular 21, and PostgreSQL to explore modern backend architecture and communication technologies.

## Overview

TalkReal is a full-stack chat application developed as a hands-on learning project. It combines real-time messaging, authentication, image sharing, and several backend architecture patterns.

The project focuses on practical implementation and experimentation rather than being a production-ready messaging platform.

## Features

- User registration and login using JWT and Refresh Tokens.
- One-to-one real-time messaging with SignalR.
- Online/offline user presence.
- Image sharing using Cloudinary.
- Chat history retrieval using GraphQL.
- Background event processing using the Outbox Pattern.
- Dockerized development environment.
- Automated build and test pipeline using GitHub Actions.

## Screenshots

### Login
![Login](docs/images/Log.png)

### Sending Messages
![Sending Messages](docs/images/Sending.png)

### Profile Photo Resizing
![Photo Resizing](docs/images/PhotoResize.png)

## Technology Stack

| Area | Technologies |
|---|---|
| Backend | .NET 9, ASP.NET Core, EF Core |
| Frontend | Angular 21, TypeScript, Tailwind CSS |
| Database | PostgreSQL |
| Architecture | Clean Architecture, CQRS, MediatR |
| Real-time | SignalR |
| Querying | GraphQL, Apollo |
| Storage | Cloudinary |
| Background Jobs | Quartz.NET |
| Other | gRPC, Webhooks, Docker, GitHub Actions |

## Architecture

The backend follows Clean Architecture principles and separates responsibilities into four main layers:

- **API:** Controllers, REST endpoints, and GraphQL.
- **Application:** CQRS, use cases, DTOs, and interfaces.
- **Domain:** Entities, domain events, and value objects.
- **Infrastructure:** Database access, repositories, SignalR, and external services.

The project also uses Repository and Unit of Work patterns.

## Communication

Different technologies are used for different purposes:

| Technology | Purpose |
|---|---|
| REST | Authentication and application operations |
| SignalR | Real-time messages and presence |
| GraphQL | Retrieving chat history |
| gRPC | Experimental service communication |
| Webhooks | External service callbacks |

## Learning Experiments

Some implementations were added mainly for learning purposes:

- **CQRS:** Separating read and write operations.
- **Outbox Pattern:** Exploring reliable event processing.
- **gRPC:** Understanding service-to-service communication.
- **Webhooks:** Handling asynchronous callbacks.

These experiments helped me understand when and why these approaches are useful in larger systems.

## Getting Started

### Prerequisites

- .NET 9 SDK
- Node.js
- Angular CLI
- PostgreSQL or Docker Desktop

### 1. Clone the repository

```bash
git clone https://github.com/Omaremad763/TalkReal.git
cd TalkReal
```

### 2. Configure environment variables

Create a `.env` file using the provided example and configure:

- PostgreSQL connection string
- JWT secret
- Cloudinary credentials

### 3. Run with Docker

```bash
docker compose up --build
```

### 4. Run manually

**Backend:**

```bash
dotnet restore
dotnet ef database update
dotnet run --project API
```

**Frontend:**

```bash
cd Front
npm install
ng serve
```

## CI/CD

GitHub Actions runs the project's validation pipeline, including:

- Dependency restoration
- Backend and frontend builds
- Automated tests

## Future Improvements

- Group conversations
- Message read receipts
- Typing indicators
- Message reactions
- Push notifications
- Redis caching

## Author

**Omar Emad**  
Software Engineer | Fullstack Developer

- [Online Resume](https://omar-emad.vercel.app/)
- [LinkedIn](https://www.linkedin.com/in/omar-abusaif/)
- [GitHub](https://github.com/Omaremad763)

## License

This project is licensed under the MIT License. See [LICENSE.txt](LICENSE.txt) for details.

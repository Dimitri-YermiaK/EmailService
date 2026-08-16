# Email Service

REST API for sending emails built with Java and Spring Boot.

## About the Project

This project is a REST API developed with Java and Spring Boot, focused on email delivery through an abstraction layer that keeps the application logic independent from the email provider implementation.

The service receives email requests through an HTTP endpoint and delegates the delivery to the configured mail provider, following clean separation of responsibilities and error handling best practices.

## Table of Contents

- [Architecture](#architecture)
- [Project Structure](#project-structure)
- [Technologies](#technologies)
- [How to Run](#how-to-run)
- [API Endpoint](#api-endpoint)

## Architecture

The project is divided into independent layers:

- **Controller:** Responsible for exposing the REST endpoint and receiving email requests from clients.
- **Service:** Contains the application-level email sending logic and delegates the operation to the provider layer.
- **Domain:** Represents the data required to send an email (recipient, subject, body).
- **Infrastructure:** Implements the email gateway and provider-specific configurations.

## Project Structure

```
src/main/java/
├── controller/          # REST endpoints
├── service/             # Application business logic
├── domain/              # Email request model
└── infra/               # Provider implementations and configurations
```

## Technologies

- **Language:** Java
- **Framework:** Spring Boot / Spring Web / Spring Mail
- **Dependency Management:** Maven
- **Principles:** Clean Architecture, SOLID, Separation of Concerns

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/Dimitri-YermiaK/EmailService.git
```

2. Navigate to the project directory:

```bash
cd EmailService
```

3. Configure the mail provider credentials in `application.properties`.

4. Run the application with Maven:

```bash
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

The API will be available at:

```
http://localhost:8080
```

## API Endpoint

### Send Email

```
POST /api/email
```

Request body:

```json
{
  "to": "recipient@example.com",
  "subject": "Subject here",
  "body": "Email body content."
}
```

Successful response:

```
200 OK
Email sent successfully
```

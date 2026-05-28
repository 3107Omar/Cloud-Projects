# Refactor Monolith to Microservices — Project Overview

This project focuses on taking an existing monolithic application and breaking it into microservices, then deploying those services using cloud-native tooling.

## What this project is about

In a monolith, all parts of the application are packaged and deployed together. That can make development, scaling, and maintenance harder as the app grows.

In this project, the goal is to refactor that architecture into smaller, independent services. Each service should handle a specific responsibility and be easier to build, deploy, and scale on its own.

## Main learning goals

By completing this project, you practice:

- understanding the difference between monolithic and microservice architectures
- separating application responsibilities into smaller services
- containerizing services
- deploying services in a cloud environment
- working with orchestration and deployment workflows
- applying production-style microservice practices

## What you are expected to do

At a high level, this project asks you to:

- start from an existing monolithic application
- identify logical boundaries in the app
- split the app into microservices
- package the services for deployment
- deploy them using the tools covered in the course
- verify that the services run correctly after deployment

## Why this matters

Microservices can improve:

- scalability, because services can scale independently
- maintainability, because smaller codebases are easier to manage
- deployment flexibility, because updates can be made to one service without redeploying everything
- team productivity, because different teams can work on different services

## Skills reinforced in this project

This project brings together topics from the course, including:

- microservices design principles
- Docker and containers
- automation in the development lifecycle
- Kubernetes orchestration
- production best practices for cloud-native apps

## What to keep in mind

When working through the project, pay attention to:

- clear separation of service responsibilities
- correct communication between services
- consistent deployment configuration
- reliability and reproducibility of the deployment process
- whether the final architecture is actually more modular than the original monolith

## Suggested approach

A good way to work through the project is:

1. Understand how the original monolith works.
2. Identify components that can be separated.
3. Refactor one responsibility at a time.
4. Containerize each service.
5. Configure deployment and orchestration.
6. Test the deployed system carefully.

## Final note

This project is meant to demonstrate that you can move from a tightly coupled monolithic system to a more flexible microservices-based deployment. The emphasis is not just on making it work, but on applying the architectural and deployment practices introduced throughout the course.

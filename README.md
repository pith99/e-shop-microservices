# EshopMicroservices

A .NET-based microservices solution for an e-commerce system.  
This repository currently contains the foundation for a **Catalog API** and a small **BuildingBlocks** library that implements CQRS abstractions using MediatR. :contentReference[oaicite:0]{index=0} :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2} :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4}

## Project Structure

### `BuildingBlocks`
Shared infrastructure components for cross-cutting patterns.

This project currently provides CQRS contracts:

- `ICommand` and `ICommand<TResponse>` for commands
- `ICommandHandler<TCommand>` and `ICommandHandler<TCommand, TResponse>` for command handlers
- `IQuery<TResponse>` for queries
- `IQueryHandler<TQuery, TResponse>` for query handlers :contentReference[oaicite:5]{index=5} :contentReference[oaicite:6]{index=6} :contentReference[oaicite:7]{index=7} :contentReference[oaicite:8]{index=8}

### `Catalog.API`
An ASP.NET Core API intended to manage catalog products.

The current domain model includes a `Product` entity with:

- `Id`
- `Name`
- `Category`
- `Description`
- `ImageFile`
- `Price` :contentReference[oaicite:9]{index=9}

The solution also includes an initial create-product flow:

- `CreateProductRequest`
- `CreateProductResponse`
- `CreateProductCommand`
- `CreateProductResult`
- `CreateProductCommandHandler` :contentReference[oaicite:10]{index=10} :contentReference[oaicite:11]{index=11}

## Current Status

This repository is an early-stage scaffold and is not yet fully implemented.

At the moment:

- the API startup is minimal
- DI/service registration is not wired up
- the HTTP request pipeline is only stubbed
- the create-product endpoint is not implemented
- persistence logic in the command handler is still a placeholder :contentReference[oaicite:12]{index=12} :contentReference[oaicite:13]{index=13} :contentReference[oaicite:14]{index=14}

## Tech Stack

- .NET / ASP.NET Core
- MediatR
- Carter
- Docker support :contentReference[oaicite:15]{index=15} :contentReference[oaicite:16]{index=16} :contentReference[oaicite:17]{index=17}

## Running the Project

### Prerequisites

- .NET SDK
- Docker (optional, for containerized execution)

### Local Run

The launch settings define local endpoints for development:

- HTTP: `http://localhost:5000`
- HTTPS: `https://localhost:5050` :contentReference[oaicite:18]{index=18}

Run the API with:

```bash
dotnet run --project Catalog.API

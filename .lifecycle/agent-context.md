# Agent Context — 40Seas/serverless-express

## What This Repo Is

A fork of [`@vendia/serverless-express`](https://github.com/vendia/serverless-express) maintained by 40Seas. It allows running Node.js web applications (Express, Koa, Hapi, NestJS, etc.) on AWS Lambda behind API Gateway, ALB, or Azure Functions.

40Seas forked this to add a custom AWS Lambda event source type and re-publish the package under `@40seas/serverless-express` for use in the main platform monorepo.

## What the Product Does

This library bridges the gap between traditional HTTP frameworks and serverless compute. It translates incoming AWS Lambda/API Gateway events into standard HTTP request objects, routes them through the application framework, and converts the response back into the Lambda-compatible format. It supports API Gateway v1 (REST), v2 (HTTP), ALB, Lambda@Edge, SQS, SNS, EventBridge, Kinesis, and Azure Functions.

## Who Uses It

- **40Seas backend engineers** — all NestJS microservices in the main monorepo (`40Seas/40Seas`) use this package to run on AWS Lambda behind API Gateway.
- **CI/CD pipelines** — the package is pulled as a dependency during builds of backend services.

## Key Personas

| Persona | Role |
|---------|------|
| Platform Engineer | Maintains the fork, applies upstream patches, and ensures compatibility with the monorepo's NestJS services |
| Backend Developer | Consumes the package implicitly when building and deploying microservices |

## Current Strategic Direction

- **Minimal divergence from upstream** — the fork carries only a small number of changes (Lambda event type support, repository URL update). The goal is to stay as close to upstream as possible to reduce maintenance burden.
- **Stability over features** — this library is a foundational dependency for all backend services. Changes should be infrequent and well-tested.

## Constraints Worth Knowing

- **Published as `@40seas/serverless-express`** — the main monorepo references this scoped package. Version bumps here require corresponding updates in `40Seas/40Seas`.
- **No active upstream** — the original Vendia repo is largely unmaintained (last meaningful activity ~2022). 40Seas carries forward any needed fixes independently.
- **Last updated Dec 2022** — this repo sees very infrequent changes. Most work happens in the main monorepo.

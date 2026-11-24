# Zoo — NestJS basics

A small NestJS 11 REST API I built to learn the framework's building blocks: modules, controllers, services and dependency injection, plus reading route params, query strings and request bodies.

## Endpoints
| Method | Path | Returns |
|---|---|---|
| GET | `/` | `Hello World!` |
| GET | `/cat` | `MYEOW` |
| GET | `/cat/greet` | `My name is TOM!` |
| GET | `/dog` | `WOW-WOW` |
| GET | `/dog/greet/:id?name=...` | `My name is REX!` — logs the route param and query string |
| POST | `/dog/edit` | `Successfully modified` — logs the JSON body |

## Structure
```
src/
├── app.module.ts      # root module, imports CatModule and DogModule
├── cat/               # cat.module · cat.controller · cat.service
└── dog/               # dog.module · dog.controller · dog.service
```
Each feature is its own module; the controller handles HTTP and the service, injected through the constructor, holds the logic.

## Run
```bash
npm install
npm run start:dev      # http://localhost:3000
```

## Tech
TypeScript · NestJS 11 · Node.js · Jest (e2e test scaffold)

These patterns grew into my production NestJS + GraphQL backend: [chaindepo](https://github.com/mirzayv/chaindepo).

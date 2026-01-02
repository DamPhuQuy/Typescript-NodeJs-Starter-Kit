# Typescript NodeJs Starter Kit

A production-ready Node.js + TypeScript starter kit with Express, following MVC architecture pattern with service layer.

<img src="./img/Screenshot 2026-01-01 090138.png">
<img src="./img/Screenshot 2026-01-01 090204.png">

- [Typescript NodeJs Starter Kit](#typescript-nodejs-starter-kit)
  - [Installation](#installation)
  - [Libraries Used](#libraries-used)
    - [Production Dependencies](#production-dependencies)
    - [Development Dependencies](#development-dependencies)
      - [TypeScript \& Type Definitions](#typescript--type-definitions)
      - [Code Quality \& Linting](#code-quality--linting)
      - [Code Formatting](#code-formatting)
      - [Development Tools](#development-tools)
  - [Quick Start](#quick-start)
  - [Available Scripts](#available-scripts)
  - [Folder Structure](#folder-structure)
  - [Summary](#summary)
    - [database/](#database)
    - [routes/](#routes)
    - [controllers/](#controllers)
    - [services/](#services)
    - [repositories/](#repositories)
    - [middlewares/](#middlewares)
    - [config/](#config)
    - [Workflow](#workflow)
  - [Misunderstood concepts](#misunderstood-concepts)
    - [`controllers/` and `services/`](#controllers-and-services)
    - [`services/` and `repositories/`](#services-and-repositories)
    - [`database/` and `repositories/`](#database-and-repositories)


## Installation

```bash
git clone https://github.com/DamPhuQuy/Typescript-NodeJs-Starter-Kit.git
cd Typescript-NodeJs-Starter-Kit
npm install
```

## Libraries Used

### Production Dependencies

| Library | Version | Description |
|---------|---------|-------------|
| [express](https://expressjs.com/) | ^5.2.1 | Fast, unopinionated web framework for Node.js |
| [dotenv](https://github.com/motdotla/dotenv) | ^17.2.3 | Loads environment variables from .env file |
| [@prisma/client](https://www.prisma.io/) | ^7.2.0 | Auto-generated and type-safe database client |
| [pg](https://node-postgres.com/) | ^8.16.3 | PostgreSQL client for Node.js |
| [@types/pg](https://www.npmjs.com/package/@types/pg) | ^8.16.0 | Type definitions for pg |

### Development Dependencies

#### TypeScript & Type Definitions
| Library | Version | Description |
|---------|---------|-------------|
| [typescript](https://www.typescriptlang.org/) | ^5.9.3 | TypeScript language compiler |
| [@types/node](https://www.npmjs.com/package/@types/node) | ^25.0.3 | Type definitions for Node.js |
| [@types/express](https://www.npmjs.com/package/@types/express) | ^5.0.6 | Type definitions for Express |
| [ts-node](https://typestrong.org/ts-node/) | ^10.9.2 | TypeScript execution engine for Node.js |
| [tsx](https://github.com/privatenumber/tsx) | ^4.21.0 | Fast TypeScript executor with hot reload |
| [tsc-alias](https://github.com/justkey007/tsc-alias) | ^1.8.16 | Replace path aliases in compiled output |

#### Code Quality & Linting
| Library | Version | Description |
|---------|---------|-------------|
| [eslint](https://eslint.org/) | ^9.39.2 | Pluggable linting utility for JavaScript and TypeScript |
| [@eslint/js](https://www.npmjs.com/package/@eslint/js) | ^9.39.2 | ESLint JavaScript rules |
| [@eslint/eslintrc](https://www.npmjs.com/package/@eslint/eslintrc) | ^3.3.3 | ESLint configuration file support |
| [typescript-eslint](https://typescript-eslint.io/) | ^8.50.1 | ESLint and TypeScript integration |
| [@typescript-eslint/parser](https://typescript-eslint.io/) | ^8.50.1 | ESLint parser for TypeScript |
| [@typescript-eslint/eslint-plugin](https://typescript-eslint.io/) | ^8.50.1 | ESLint plugin for TypeScript |
| [globals](https://github.com/sindresorhus/globals) | ^16.5.0 | Global identifiers from different JavaScript environments |

#### Code Formatting
| Library | Version | Description |
|---------|---------|-------------|
| [prettier](https://prettier.io/) | ^3.7.4 | Opinionated code formatter |
| [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) | ^10.1.8 | Turns off ESLint rules that conflict with Prettier |
| [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) | ^5.5.4 | Runs Prettier as an ESLint rule |

#### Development Tools
| Library | Version | Description |
|---------|---------|-------------|
| [nodemon](https://nodemon.io/) | ^3.1.11 | Automatically restarts node application on file changes |
| [rimraf](https://github.com/isaacs/rimraf) | ^6.1.2 | Deep deletion module for node (cross-platform rm -rf) |
| [prisma](https://www.prisma.io/) | ^7.2.0 | Next-generation ORM for Node.js and TypeScript |

## Quick Start

1. **Setup environment variables:**
```bash
cp .env.example .env
# Edit .env with your configuration
```

2. **Run development server:**
```bash
npm run dev
```

3. **Build for production:**
```bash
npm run build
npm start
```

## Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server with hot reload |
| `npm run build` | Build TypeScript to JavaScript |
| `npm start` | Run production build |
| `npm run lint` | Check code for linting errors |
| `npm run lint:fix` | Fix linting errors automatically |
| `npm run prettier` | Check code formatting |
| `npm run prettier:fix` | Fix code formatting automatically |

## Folder Structure

```
Project_Root/
 ┣ 📂prisma/
 ┃ ┗ 📜schema.prisma      # Single source of truth for DB models
 ┣ 📂src/
 ┃ ┣ 📂config/            # Environment variables & 3rd party configs (env.ts)
 ┃ ┣ 📂controllers/       # Request handling, response formatting (user.controller.ts)
 ┃ ┣ 📂database/          # Prisma Client initialization (connection.ts)
 ┃ ┣ 📂middlewares/       # Auth, Error handling, Logger (error.middleware.ts)
 ┃ ┣ 📂repositories/      # Direct DB operations only (user.repository.ts)
 ┃ ┣ 📂routes/            # Route definitions & entry points (user.route.ts)
 ┃ ┣ 📂services/          # Business logic & orchestration (user.service.ts)
 ┃ ┣ 📂types/             # Shared TS interfaces/types (request.type.ts)
 ┃ ┣ 📂utils/             # Shared helper functions (password.util.ts)
 ┃ ┣ 📂validations/       # Schema validation - Zod/Joi (user.validation.ts)
 ┃ ┣ 📜app.ts             # Express setup (Middlewares, Routes)
 ┃ ┗ 📜server.ts          # Entry point (DB connect -> App listen)
 ┣ 📜.env                 # Private secrets
 ┣ 📜package.json
 ┗ 📜tsconfig.json
```

## Summary

### database/
- Role: Manage connection to database, define how database looks like, no sql query
-

### routes/
- Role: Declare route URL and HTTP method
- Notice: No logic, No database

```ts
router.post("/users", userController.create); // .create for post method
```

### controllers/
- Role: Receive `request`, call `services/`, send back `response` (HTTP adapter)

```ts
export const create = async (request, response) => {
  const user = await userService.createUser(request.body);
  response.status(201).json(user); // response.json(): response method for sending json response
}
```

### services/
- Role: Business logic, coordinate repositories
```ts
export const createUser = async (data) => {
  if (await userRepo.existByEmail(data.email)) {
    throw new Error("Emai exists");
  }
  return userRepo.create(data);
}
```

### repositories/
- Role: query DB, only CRUD, no business logic, manipulate with database, no True/False logic
```ts
export const create = (data) => {
  prisma.user.create({ data });
}
```

### middlewares/
- Role: handle cross-cutting concerns, auth, error handler, logging
- In middle between request and response, not depend on business
```ts
// middlewares/error.middleware.ts
export const errorHandler = (err, req, res, next) => {
  res.status(500).json({ message: err.message });
};
```
### config/
- Role: read env, external configuration
```ts
export const env = {
  PORT: process.env.PORT!,
};
```

### Workflow
```markdown
Client
 ↓
Express App
 ↓
Global Middleware
 ↓
Route
 ↓
Validation
 ↓
Controller
 ↓
Service  ← BUSINESS LOGIC
 ↓
Repository
 ↓
Database
 ↑
Response
```
## Misunderstood concepts
### `controllers/` and `services/`

| Controller   | Service            |
| ------------ | ------------------ |
| HTTP layer   | Business layer     |
| Know req/res | Don't know HTTP    |
| Parse input  | Check business logic |
| Send response | Send data           |

Rule: if we take away Express but code still works -> service

### `services/` and `repositories/`
| Service        | Repository      |
| -------------- | --------------- |
| Logic          | Query (only CRUD)       |
| Decision     | Execute        |
| Call repos | 1 repo / 1 table |

### `database/` and `repositories/`


| Feature | `database/` | `repositories/` |
| --- | --- | --- |
| **Layer** | **Infrastructure** (Physical) | **Data Access** (Abstraction) |
| **Main Focus** | How data is **stored** and structured. | How data is **accessed** and managed. |
| **Typical Content** | Migrations, Seeds, Schemas, SQL files. | Classes/Interfaces with methods like `find()`, `save()`. |
| **Responsibility** | Creating tables, indexes, and constraints. | Fetching and mapping DB rows into Code Objects. |

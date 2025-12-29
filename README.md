# Typescript NodeJs Starter Kit

A production-ready Node.js + TypeScript starter kit with Express, following MVC architecture pattern with service layer.

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
src/
├── app.ts                 # Express app configuration
├── index.ts              # Application entry point
├── config/
│   └── env.ts           # Environment configuration
├── controllers/
│   └── user.controller.ts  # HTTP request handlers
├── middlewares/
│   └── error.middleware.ts # Error handling
├── models/
│   └── user.model.ts       # Data models & types
├── routes/
│   └── user.route.ts       # API route definitions
├── services/
│   └── user.service.ts     # Business logic
└── utils/
    ├── logger.ts           # Logging utility
    ├── response.ts         # Response helpers
    └── validation.ts       # Validation helpers
```

# NestJs REST API tutorial for FreeCodeCamp

### Run the API in development mode

```javascript
yarn // install
yarn db:dev:restart // start postgres in docker and push migrations
yarn start:dev // start api in dev mode
```

# NestJS

## Install CLI

```
npm i -g @nestjs/cli
```

## Create NEST project

```
nest new LearningNestWithPostgreSQL
```

choose `yarn`

Delete `app.service` and `app.controller`

Fix the imports in `app.module.ts`

## What is a Module ?

A **module** in NestJS is a way to group related code (like controllers and services) together.

It helps organize the app into small, manageable parts.

Every Nest app starts with a main module called `AppModule`.

### Example:

```javascript
@Module({
  controllers: [CatsController],
  providers: [CatsService],
})
export class CatsModule {}
```

- A module is a class

## What is a Decorator ?

A **decorator** is a special function in NestJS that adds **extra behavior** to classes, methods, or properties.
It starts with `@` and is placed **above** the thing it decorates.

### Example:

```tsx
@Controller('cats')
export class CatsController {
  @Get()
  findAll() {
    return 'This returns all cats';
  }
}
```

Here:

- `@Controller('cats')` tells Nest this class handles `/cats` routes.
- `@Get()` tells Nest this method handles GET requests.

## What is Controller

A **controller** handles incoming requests and sends responses.
It maps routes like GET, POST, etc.

### Example:

```tsx
@Controller('cats')
export class CatsController {
  @Get()
  findAll() {
    return 'All cats';
  }
}
```

## What is Provider

A **provider** is a class that contains logic or data access (like a service).
It can be injected into other classes.

### Example:

```tsx
@Injectable()
export class CatsService {
  getCats() {
    return ['Cat1', 'Cat2'];
  }
}
```

## Create Module CLI Command

To create a module using NestJS CLI, run:

```tsx
nest generate module <module-name>
```

**Shortcut:**

```tsx
nest g mo <module-name>
```

**Example:**

```tsx
nest g mo cats
```

This will create `cats.module.ts`.

# Task

1. Create a nest project. create module, controller, service manuall. set them up. return text output

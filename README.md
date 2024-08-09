
# OnlineBookStore

## Project Overview

The *OnlineBookStore* is a web application designed for an online bookstore that sells physical books, e-books, and audiobooks. Customers can browse the catalog, make purchases, and leave reviews. Authors and publishers are also part of the system. This project implements full CRUD (Create, Read, Update, Delete) functionality for the main entities involved: Authors, Books, Customers, and Reviews. The project also includes unit and integration tests to ensure the reliability and robustness of the operations.

## Features

- *Authors*: Manage authors and their associated books.
- *Books*: CRUD operations on books, including searching and filtering by genre, rating, etc.
- *Customers*: Manage customer profiles and their purchasing history.
- *Reviews*: Customers can leave and manage reviews on books they have purchased.

## Technology Stack

- *Backend*: Node.js, Express, TypeScript
- *Database*: PostgreSQL, TypeORM
- *Testing*: Jest, Supertest
- *Containerization*: Docker

## Project Structure


OnlineBookStore/
│
├── src/
│   ├── entities/
│   │   ├── Author.ts
│   │   ├── Book.ts
│   │   ├── Customer.ts
│   │   ├── Review.ts
│   │
│   ├── controllers/
│   │   ├── authorController.ts
│   │   ├── bookController.ts
│   │   ├── customerController.ts
│   │   ├── reviewController.ts
│   │
│   ├── services/
│   │   ├── authorService.ts
│   │   ├── bookService.ts
│   │   ├── customerService.ts
│   │   ├── reviewService.ts
│   │
│   ├── configroutes.ts
│   │  
│   │
│   ├── tests/
│   │   ├── unit.ts
│   │   ├── integration.ts
│   │  
│   │
│   ├── index.ts
│   └── ormconfig.ts
│
├── Dockerfile
├── docker-compose.yml
├── jest.config.js
├── package.json
├── tsconfig.json
└── README.md


## Setup and Installation

### Prerequisites

- Node.js
- PostgreSQL
- Docker (for containerization)

### Steps

1. *Clone the Repository*

   bash
   cd OnlineBookStore
   

2. *Install Dependencies*

   bash
   npm install
   

3. *Database Setup*

   - Create a PostgreSQL database.
   - Configure your ormconfig.ts with your database credentials.

4. *Run Migrations*

   bash
   npm run typeorm migration:run
   

5. *Start the Application*

   bash
   npm run dev
   

6. *Run Tests*

   - Unit Tests:

     bash
     npm run test:unit
     

   - Integration Tests:

     bash
     npm run test:integration
     

7. *Containerization (Optional)*

   To run the project in a Docker container:

   bash
   docker-compose up --build
   

## API Endpoints

### Authors

- *GET* /api/authors: Get all authors
- *POST* /api/authors: Create a new author
- *PUT* /api/authors/:id: Update an author by ID
- *DELETE* /api/authors/:id: Delete an author by ID

### Books

- *GET* /api/books: Get all books
- *POST* /api/books: Create a new book
- *PUT* /api/books/:id: Update a book by ID
- *DELETE* /api/books/:id: Delete a book by ID

### Customers

- *GET* /api/customers: Get all customers
- *POST* /api/customers: Create a new customer
- *PUT* /api/customers/:id: Update a customer by ID
- *DELETE* /api/customers/:id: Delete a customer by ID

### Reviews

- *GET* /api/reviews: Get all reviews
- *POST* /api/reviews: Create a new review
- *PUT* /api/reviews/:id: Update a review by ID
- *DELETE* /api/reviews/:id: Delete a review by ID

## Entity Relationships

- *Author* 1 - n *Book*
- *Book* n - 1 *Author*
- *Customer* n - n *Book*
- *Book* 1 - n *Review*
- *Customer* 1 - n *Review*



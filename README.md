# Event Management System (EMS)

A basic FullStack Event Management System where users can create, view, edit, and delete events. Includes a simple recommendation algorithm and integration with PostgreSQL.

---

## Technologies Used

- **Frontend:** Next.js, React, Material UI  
- **Backend:** NestJS, Prisma  
- **Database:** PostgreSQL  
- **Tools:** Postman for API testing

---

## Quick Setup (Frontend + Backend)

1. **Clone the [backend](https://github.com/tasiya1/backend) repository**  

```bash
git clone https://github.com/tasiya1/backend.git
```
Install dependencies

```bash
npm install
```
Configure the PostgreSQL connection in prisma/schema.prisma:

```bash
datasource db {
  provider = "postgresql"
  url      = "postgresql://USER:PASSWORD@localhost:5432/yourdb?schema=public"
}
```
Run database migrations:
```bash
npx prisma migrate dev --name init
```
Start the backend server:
```bash
npm run start:dev
```
Backend API will be available at: http://localhost:3001

2. **Clone the [frontend](https://github.com/tasiya1/frontend) repository**  

```bash
git clone https://github.com/tasiya1/frontend.git
```
Install dependencies and start
```bash
npm install
npm run dev
```

## Test Data

The database includes some sample events to test the system:

|        Title       |    Category   | Location |    Date    |
|:------------------:|:-------------:|:--------:|:----------:|
| React Workshop     | Workshop      | Kyiv     | 2026-04-01 |
| NextJS Masterclass | Workshop      | Lviv     | 2026-04-03 |
| Music Festival     | Entertainment | Odesa    | 2026-04-05 |
| Art Exhibition     | Entertainment | Kyiv     | 2026-04-06 |
| Startup Meetup     | Networking    | Lviv     | 2026-04-07 |
| Tech Talks         | Networking    | Kyiv     | 2026-04-08 |


## API Endpoints

| Method |             URL             |               Description              |
|:------:|:---------------------------:|:--------------------------------------:|
| GET    | /events                     | Get all events                         |
| GET    | /events/:id                 | Get details of a specific event        |
| POST   | /events                     | Create a new event                     |
| PUT    | /events/:id                 | Update an existing event               |
| DELETE | /events/:id                 | Delete an event                        |
| GET    | /events/:id/recommendations | Get recommended events (same category) |

## Frontend Pages

| Page                    |             Description                               |
|:-----------------------:|:-----------------------------------------------------:|
| Event List Page         | Displays list of all events.                          |
| Event Details Page      | Shows detailed information and recommended events.    |
| Event Create/Edit Page  | Form for adding or editing events.                    |
| Event Deletion          | Option to delete an event with confirmation.          |

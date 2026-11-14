# Learnova Database

Learnova stores its data in PostgreSQL and uses Prisma 7 as the ORM, with the `@prisma/adapter-pg` driver and a `pg` connection pool.

The Prisma schema, migrations and seed script are in [`backend/prisma/`](../backend/prisma/).

## Contents

| Folder | Description |
| :--- | :--- |
| [`diagrams/`](diagrams/) | Conceptual, logical and physical data models (draw.io) |
| [`backups/`](backups/) | Backup and restore scripts for Linux, macOS and Windows |

## Data model highlights

- 18 Prisma models covering users and roles, courses, sessions, videos, enrollments, progress, quizzes, exams, certificates and gamification
- Foreign keys with cascade deletes, composite indexes and unique constraints
- Migrations managed with Prisma Migrate

## Seed data

`npx prisma db seed` creates the demo accounts and loads the catalog: 108 courses across 14 domains, 142 sessions, 568 videos with lecture notes, 142 practice quizzes and 108 final exams.

## Common commands

Run these from `backend/`:

```bash
npx prisma validate          # Check the schema
npx prisma generate          # Generate the typed client
npx prisma migrate status    # Check migration state
npx prisma migrate deploy    # Apply migrations
npx prisma db seed           # Load seed data
```

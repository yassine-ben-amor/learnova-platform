# Learnova API

REST API of the Learnova platform, built with NestJS 11, TypeScript and Prisma 7 on PostgreSQL.

## Setup

```bash
npm install
cp .env.example .env
npx prisma migrate deploy
npx prisma db seed
npm run start:dev
```

The API is served under `http://localhost:3000/api`.

## Modules

| Module | Responsibility |
| :--- | :--- |
| `auth` | Registration, login, JWT strategy, password reset |
| `users` | Profile, settings, statistics, account management |
| `courses`, `sessions`, `videos`, `course-content` | Course catalog and learning material |
| `enrollments`, `learning-path`, `progress` | Enrollment, sequential unlocking and progress tracking |
| `quiz`, `questions`, `exams` | Practice quizzes and timed final exams |
| `certificates` | Certificate issuance and public QR verification |
| `gamification`, `dashboard` | Streaks, XP, badges and learner statistics |
| `ai` | Tutor chatbot, recommendations, quiz generator, performance analysis |
| `payments` | Checkout for paid courses |

## Scripts

| Command | Description |
| :--- | :--- |
| `npm run start:dev` | Start in watch mode |
| `npm run build` | Compile to `dist/` |
| `npm run start:prod` | Run the compiled build |
| `npm run test` | Run unit tests |
| `npm run lint` | Lint and fix the code |

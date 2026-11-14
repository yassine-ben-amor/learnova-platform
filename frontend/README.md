# Learnova Web App

Single-page application of the Learnova platform, built with React 19, React Router 7 and Vite.

## Setup

```bash
npm install
npm run dev
```

The app runs on `http://localhost:5173` and expects the API on `http://localhost:3000/api` (see [`backend/`](../backend/)).

## Structure

```text
src/
├── components/   Navbar, video player, certificate, progress and badge components
├── context/      Authentication context
├── pages/        Home, Courses, Course details, Learning path, Quiz, Exam,
│                 Certificates, Dashboard, Profile, Admin and support pages
└── services/     Axios API clients
```

## Scripts

| Command | Description |
| :--- | :--- |
| `npm run dev` | Start the development server |
| `npm run build` | Build for production into `dist/` |
| `npm run preview` | Preview the production build |

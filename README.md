# ClassMates: Smart Productivity Tool

Clean, minimal, and production-ready app for students and mentors. Includes React + Tailwind frontend, Node.js + Express backend, and MySQL database with security and fraud detection.

## Quick Start

1) MySQL setup (uses your provided DB name and password)

```sql
-- in MySQL
SOURCE db/schema.sql;
SOURCE db/seed.sql;
```

2) Backend

```bash
cd backend
npm i
# set env
setx PORT 5000
setx CORS_ORIGIN http://localhost:5173
setx DB_HOST localhost
setx DB_USER root
setx DB_PASSWORD "ikigai#123"
setx DB_NAME classmates
setx JWT_SECRET "replace_me"
setx JWT_EXPIRES "7d"
npm run dev
```

3) Frontend

```bash
cd frontend
npm i
npm run dev
```

Open `http://localhost:5173` and sign in with `student1@classmates.com / student123`.

## Features

- Dashboard with quick stats and links
- Tasks: CRUD + filters + Pomodoro
- Forum: posts, comments, likes
- Connect: profile search and collaboration requests
- Auth: JWT + bcrypt, protected routes
- Admin: users and security alerts
- Fraud detection crons (login failures, IP reuse, high posting)

## API Endpoints (base: /api)

- Auth: `POST /auth/login`, `POST /auth/signup`
- Tasks: `GET/POST /tasks`, `PUT/DELETE /tasks/:id`
- Forum: `GET /forum/posts`, `POST /forum/posts`, `GET /forum/posts/:id/comments`, `POST /forum/posts/:id/comments`, `POST /forum/posts/:id/like`
- Connect: `GET /connect/profiles`, `POST /connect/requests`, `POST /connect/requests/:id/respond`
- Admin: `GET /admin/users`, `GET /admin/security/alerts`, `POST /admin/security/alerts/:id/action`

## Deployment

- Frontend: `npm run build` (Vercel/Netlify)
- Backend: Deploy to Render/Railway. Set env vars accordingly.
- Update `CORS_ORIGIN` to deployed frontend URL.

## Notes

- Environment variables can be set via `.env` as well (PORT, DB_*, JWT_*).
- Windows PowerShell users can use `setx` as shown above for local dev.



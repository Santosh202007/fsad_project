# Gym Workout Tracker

## Overview

A full-stack gym workout tracking application with JWT authentication, workout logging, progress analytics, and a polished dark-mode UI.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite + Tailwind CSS + shadcn/ui + Recharts
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Auth**: JWT (jsonwebtoken) + bcryptjs for password hashing
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Application Features

- **Authentication**: JWT-based login/register with bcrypt password hashing
- **Dashboard**: Stats cards (streak, workouts, exercises), recent activity, exercise stats
- **Workout Tracker**: CRUD workouts with search/filter, pagination
- **Progress Analytics**: Weekly progress entries with Recharts bar/line charts
- **Profile**: View/edit user profile with weight, age, goals
- **Dark/Light Mode**: Toggle with next-themes

## Artifacts

- `artifacts/gym-tracker` — React + Vite frontend (preview path: `/`)
- `artifacts/api-server` — Express 5 backend (preview path: `/api`)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

## Database Schema

- `users` — id, name, email, password (hashed), age, weight, goals, timestamps
- `workouts` — id, user_id (FK), exercise_name, sets, reps, weight, date, notes, timestamps
- `progress` — id, user_id (FK), calories_burned, weight_change, week, notes, timestamps

## API Routes

- `POST /api/auth/register` — register new user
- `POST /api/auth/login` — login
- `GET/PATCH /api/users/profile` — user profile
- `GET/POST /api/workouts` — list/create workouts (with search, filter, pagination)
- `GET/PATCH/DELETE /api/workouts/:id` — workout CRUD
- `GET/POST /api/progress` — list/create progress
- `PATCH/DELETE /api/progress/:id` — progress CRUD
- `GET /api/dashboard/summary` — stats overview
- `GET /api/dashboard/recent-workouts` — recent 5 workouts
- `GET /api/dashboard/exercise-stats` — per-exercise aggregates

## Auth Flow

JWT token stored in localStorage as `jwt_token`. The API client uses `setAuthTokenGetter` to attach `Authorization: Bearer <token>` to every request automatically.

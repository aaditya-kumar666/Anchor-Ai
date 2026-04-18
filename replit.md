# PEWS - Placement Early Warning System

## Overview

AI-powered Placement Early Warning System (PEWS) built as a React + Vite web app with dark glassmorphism theme. Features student and admin dashboards with simulated AI analysis engine.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite + Tailwind CSS + Recharts
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM (available but not used yet - using localStorage)
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)
- **PDF Parsing**: pdfjs-dist (client-side)

## App Structure

### Login System
- Student login: username/password (sample: aravind/pass123, priya/pass123, rahul/pass123)
- Admin login: admin/admin123
- Sign up for new students
- Data stored in localStorage

### Student Dashboard Pages
- `/` - Login page (animated gradient, glassmorphism)
- `/dashboard` - Main dashboard with risk score, skill score, charts, suggestions, company recommendations
- `/analysis` - Detailed analysis with radar chart and skill breakdown
- `/applications` - Manage company applications
- `/recommendations` - Company recommendations and improvement suggestions
- `/profile` - Profile management, resume upload, GitHub link, skills, companies

### Admin Dashboard Pages
- `/admin` - Placement Control Center with overview cards, student table, AI intelligence panel, risk distribution chart
- `/admin/students` - Full student list with sorting and filtering
- `/admin/skillgaps` - Skill gap analysis with bar charts
- `/admin/alerts` - Alerts and notifications
- `/admin/history` - Timeline of student events

### AI Analysis Engine (Simulated)
- Resume text extraction from PDF using pdfjs-dist
- Keyword-based skill detection
- Risk calculation: `risk = 0.4*(1-skill) + 0.3*(1-activity) + 0.3*(1-apps_normalized)`
- Personalized suggestions based on skill/activity/application levels
- Company recommendations based on skill level (beginner→startups, intermediate→mid-level, advanced→top tech)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.

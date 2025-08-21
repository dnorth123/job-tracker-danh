# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Development
- `npm run dev` - Start the Next.js development server with Turbopack
- `npm run dev:server` - Alternative development server without Turbopack
- `npm run build` - Build the production application
- `npm start` - Start the production server
- `npm run lint` - Run ESLint for code linting

## Architecture Overview

### Tech Stack
- **Framework**: Next.js 15 with App Router
- **Language**: TypeScript with strict mode enabled
- **Styling**: Tailwind CSS v4
- **Database**: Supabase (PostgreSQL) via Neon serverless
- **Authentication**: Supabase Auth with auth-ui-react
- **Icons**: Lucide React

### Project Structure
- `/src/app/` - Next.js App Router pages and layouts
- `/src/components/` - React components for jobs, contacts, interactions, and reporting
- `/src/lib/` - Database utilities, Supabase client, and business logic
- `/hooks/` - Custom React hooks (e.g., useDatabase)
- `/documentation/` - Project documentation including user stories, migration plans, and journey maps

### Database Schema
The application uses three main tables:
- **jobs**: Tracks job applications with statuses (interested, applied, interviewing, onhold, offered, rejected)
- **contacts**: Manages professional network contacts with experience and education tracking
- **interactions**: Records communication history with contacts

### Key Components
- **JobList/JobForm**: Job pipeline management with status tracking
- **ContactList/ContactForm**: Network management with LinkedIn integration
- **Reporting**: Analytics dashboard for application insights
- **CSVManager**: Import/export functionality for data migration
- **LoginForm**: Supabase authentication interface

### Environment Variables
Required in `.env.local`:
- `NEXT_PUBLIC_SUPABASE_URL`
- `NEXT_PUBLIC_SUPABASE_ANON_KEY`

### Path Aliases
The project uses `@/` as an alias for `./src/` directory in imports.
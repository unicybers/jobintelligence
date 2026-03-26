# UniCybers Job Intelligence

Cybersecurity job intelligence platform that aggregates real hiring data across India, Middle East, Asia Pacific, and Africa.

Built for [UniCybers](https://www.unicybers.online)

## Features

- **Live Job Fetching** — Pulls real cybersecurity jobs from Google for Jobs, LinkedIn, Indeed, Glassdoor via JSearch API
- **Dashboard** — Overview with stats by region, experience level, in-demand skills
- **Job Listings** — Filterable by region, experience, category, job type, with search
- **Analytics** — Visual breakdown of the cybersecurity job market
- **Job Alerts** — Email alert subscriptions for specific criteria
- **Admin Panel** — Protected panel to fetch jobs from API, add/edit/delete jobs manually

## Tech Stack

- **Frontend**: React, Tailwind CSS, shadcn/ui, Recharts
- **Backend**: Express.js, Node.js
- **Database**: SQLite (via Drizzle ORM + better-sqlite3)
- **API**: JSearch (RapidAPI) for live job data

## Setup

### 1. Install Dependencies
```bash
npm install
```

### 2. Set Environment Variables
```bash
export JSEARCH_API_KEY=your_rapidapi_key_here
export ADMIN_KEY=your_secret_admin_key
```

Get your free JSearch API key at: https://rapidapi.com/letscrape-6bRBa3QguO5/api/jsearch

### 3. Initialize Database
```bash
npm run db:push
```

### 4. Build & Run
```bash
npm run build
npm start
```

The app runs on port 5000 (or the PORT environment variable).

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `JSEARCH_API_KEY` | Yes | RapidAPI key for JSearch (free tier: 100 req/month) |
| `ADMIN_KEY` | No | Admin panel access key (default: `unicybers-admin-2026`) |
| `PORT` | No | Server port (default: `5000`) |

## Admin Panel

Navigate to `/#/admin` and enter your admin key. From there you can:
- **Fetch Jobs** — Pull live jobs from JSearch API (5, 10, or 15 queries)
- **Add Jobs** — Manually create job listings
- **Edit/Delete** — Manage existing jobs
- **Clear All** — Remove all jobs and start fresh

## Railway Deployment

1. Push this repo to GitHub
2. Connect Railway to your GitHub repo
3. Set environment variables in Railway dashboard
4. Railway auto-detects Node.js and runs `npm run build` then `npm start`

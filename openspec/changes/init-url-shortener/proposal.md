# Change: Init URL Shortener MVP

## Why
We need to launch the initial version of the "Javly" URL shortener. This project aims to provide a simple interface for users to shorten URLs and a redirection service to handle those links.

## What Changes
We will initialize the project with the following Tech Stack to satisfy the Frontend + Backend + Database requirements in a cohesive way:

### Tech Stack Proposal
- **Framework**: [Next.js](https://nextjs.org/) (React). 
  - *Why*: Handles both Frontend (UI) and Backend (API Routes) in a single project. deeply integrated, easy to deploy.
- **Styling**: Vanilla CSS (modern, variables, responsive).
- **Database**: [SQLite](https://www.sqlite.org/).
  - *Why*: Simple, file-based, zero-configuration. Perfect for MVPs. Can be easily swapped for PostgreSQL later using an ORM like Prisma.
- **ORM**: [Prisma](https://www.prisma.io/).
  - *Why*: Type-safe database access, easy schema management.

### Key Features (MVP)
1.  **Landing Page**: Input form to submit a URL.
2.  **API Endpoint**: `POST /api/shorten` to generate a code (e.g., 6 chars).
3.  **Redirection**: `GET /:code` looks up the URL and redirects.
4.  **Database Schema**: Table `Link` (id, originalUrl, shortCode, createdAt).

## Impact
- **New Capabilities**:
  - `shortener`: Core domain logic for managing links.
- **New Files**:
  - `package.json`, `next.config.js`, `prisma/schema.prisma`.
  - `src/` directory for code.

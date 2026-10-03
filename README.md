# Scratch Demon List

The **Scratch Demon List (SDL)** is a community ranking site for challenging Geometry Dash levels.

## Owner

The configured owner is **zeroGD**. The owner account has access to `/admin` and owner-only moderation tools.

Default owner password for this build: `rightpeice5u!`

**Change this password before deploying publicly.**

## Requirements

- Node.js 18+
- PostgreSQL database

The application uses PostgreSQL for users, levels, records, submissions, and moderation data. A database schema/data source is required; this package does not create a fresh empty schema automatically.

## Configuration

Create `.env` with at least:

```env
DATABASE_URL=YOUR_POSTGRES_CONNECTION_STRING
OWNER_USERNAME=zeroGD
OWNER_PASSWORD=rightpeice5u!
OWNER_EMAIL=zeroGD@local.invalid
SESSION_SECRET=CHANGE_THIS_TO_A_LONG_RANDOM_SECRET
```

`DATABASE_URL` is required for login, the admin panel, and database-backed site features.

## Running

```bash
npm install
npm start
```

The server listens on `PORT` if provided, otherwise `3000`.

## Health check

Open `/api/health`. A healthy deployment returns `{ "ok": true, "database": true }`. If PostgreSQL is missing or unreachable, the endpoint returns HTTP 503 with a useful configuration error.

## Level requirement

Levels submitted to the list must be at least **25 seconds** long. End screens and long auto sections do not count toward the required time.

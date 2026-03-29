# Multiplayer Sudoku

A real-time multiplayer Sudoku game where players compete to solve the same puzzle simultaneously.

## Project Structure

This is a monorepo containing both the frontend and backend:

```
├── frontend/    # React app (Redux, Socket.io-client)
├── backend/     # Node.js server (Express, Socket.io)
└── package.json # Root scripts to run both
```

## Tech Stack

**Frontend**
- React 17 + Redux Toolkit
- Socket.io-client
- React Router DOM
- SCSS Modules

**Backend**
- Node.js + Express
- Socket.io
- Child processes for parallel Sudoku validation

## Getting Started

### Prerequisites
- Node.js 12+
- npm

### Install dependencies

```bash
npm run install:all
```

### Run locally

```bash
npm start
```

This runs the frontend (port 3000) and backend (port 3001) concurrently.

Or run them separately:

```bash
npm run frontend   # React dev server on port 3000
npm run backend    # Node server on port 3001
```

## How It Works

1. Players enter their name to join a game room
2. A countdown starts once the first player joins (30s in production, 5s in development)
3. All players receive the same Sudoku puzzle when the game starts
4. Players race to fill in the correct numbers
5. Live progress bars show competitors' completion in real-time
6. Finished players and their completion times are displayed on the side

## Deployment

The frontend expects the backend URL to be set in `frontend/src/features/board/boardSlice.js`:
- Development: `http://localhost:3001`
- Production: update to your deployed backend URL

**Recommended hosting:**
- Backend: [Render](https://render.com) or [Railway](https://railway.app)
- Frontend: [Vercel](https://vercel.com) or [Netlify](https://netlify.com)

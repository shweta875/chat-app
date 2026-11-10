# Chat App

A real-time chat application with a React/Vite frontend and an Express/Socket.IO backend. It includes account registration and login, user profiles, real-time messaging, online-user presence, and image uploads through Cloudinary.

## Requirements

- **Node.js and npm** (use a current Node.js LTS release)
- **MongoDB**: a local instance or a MongoDB Atlas connection string
- **Cloudinary account**: needed for profile image uploads

## Configuration

Create `backend/.env` with the following values:

```env
PORT=5001
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=replace_with_a_long_random_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
NODE_ENV=development
```

The frontend defaults to the backend at `http://localhost:5001` in development. If your backend runs at a different address, create `frontend/.env.local` and set:

```env
VITE_BACKEND_URL=http://localhost:5001
```

Do not commit environment files or secrets.

## Install and run in development

From the repository root, install the backend and frontend dependencies:

```bash
npm install --prefix backend
npm install --prefix frontend
```

Start the backend in one terminal:

```bash
npm run dev --prefix backend
```

Start the frontend in a second terminal:

```bash
npm run dev --prefix frontend
```

Open the local URL printed by Vite (by default, `http://localhost:5173`). The backend defaults to port `5001`.

## Production build and start

From the repository root:

```bash
npm run build
npm start
```

The build script installs both applications' dependencies and builds the frontend. The start script starts the backend.

## Useful commands

| Command | Description |
| --- | --- |
| `npm run dev --prefix backend` | Start the backend with automatic restarts |
| `npm run start --prefix backend` | Start the backend normally |
| `npm run dev --prefix frontend` | Start the Vite development server |
| `npm run build` | Install dependencies and build the frontend |
| `npm run build --prefix frontend` | Build only the frontend |
| `npm run lint --prefix frontend` | Run frontend linting |

## Tech stack

- **Frontend:** React, Vite, Tailwind CSS, DaisyUI, Zustand, Socket.IO client
- **Backend:** Node.js, Express, MongoDB/Mongoose, Socket.IO, JWT authentication
- **Image storage:** Cloudinary

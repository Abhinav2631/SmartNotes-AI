# SmartNotes-AI

SmartNotes-AI is a full-stack study workspace that uses AI to generate study notes and question sets. The interface supports visual explanations, revision history, and PDF export.

## Features in the application

- Generate structured notes and question sets with Gemini.
- Render Markdown and Mermaid diagrams.
- Display charts and visualizations.
- Sign in and browse saved note history.
- Manage usage credits and Stripe Checkout flows.
- Export study material to PDF.
- Use a React/Vite client with a Node.js/Express API.

## Technology stack

- **Frontend:** React, Vite, React Router, Redux Toolkit, Tailwind CSS
- **Backend:** Node.js, Express, Mongoose
- **Data and authentication:** MongoDB, Firebase Authentication
- **AI and payments:** Gemini API, Stripe

## Run locally

### Requirements

- Node.js and npm
- MongoDB
- Firebase project with Authentication enabled
- Gemini API key
- Stripe credentials only if testing credit purchases

### Configure the server

1. Open `server/` and run `npm install`.
2. Copy `server/.env.example` to `server/.env`.
3. Set `MONGO_URL`, `JWT_SECRET`, `GEMINI_API_KEY`, the Stripe variables if needed, `CLIENT_URL`, and `CLIENT_ORIGIN`.
4. Start the server with `npm run dev`.

### Configure the client

1. Open `client/` and run `npm install`.
2. Copy `client/.env.example` to `client/.env`.
3. Set the `VITE_API_URL` and the required `VITE_FIREBASE_*` values.
4. Start the client with `npm run dev`.

Do not commit real secrets. Variables prefixed with `VITE_` are bundled into client-side code and must never be treated as private server secrets.

## Repository-specific configuration work

This copy makes several setup/configuration changes around the existing application:

- Firebase settings are read from `VITE_FIREBASE_*` environment variables rather than hard-coded project IDs.
- The client API base URL is configurable through `VITE_API_URL`, with a local-development fallback.
- The server's allowed client origin is configurable with `CLIENT_ORIGIN`.
- The footer copy is adjusted for this learning/portfolio instance.

These are configuration and presentation changes; the core application implementation remains substantially based on the upstream project.

## Attribution and reuse

This repository is an authorised learning/adaptation copy of [SmartNotes-AI by Naresh Chary](https://github.com/NareshChary0430/SmartNotes-AI). The upstream project and its original implementation remain credited to the original creator. This repository should not be described as an independently written application from scratch.

# SmartNotes-AI

An AI-assisted study platform for generating exam-focused notes and learning material, visualizing concepts, managing revision history, and handling credit-based usage.

This repository contains a React/Vite frontend and a Node.js/Express API. The app also integrates Firebase Authentication, MongoDB, Gemini, and Stripe; each service must be configured with your own credentials before the related features can work.

## Features

- Generate structured study notes and question sets with Gemini.
- Render Markdown and Mermaid diagrams; display charts and visualizations.
- Sign in, browse note history, and manage usage credits.
- Support credit purchases with Stripe Checkout and webhook handling.
- Export learning material to PDF.
- Responsive React interface using Redux Toolkit and Tailwind CSS.

## Technology stack

- **Frontend:** React, Vite, React Router, Redux Toolkit, Tailwind CSS, Mermaid, Recharts
- **Backend:** Node.js, Express, Mongoose, JWT/cookie-based authentication
- **Services:** Firebase Authentication, Gemini API, Stripe

## Repository layout

```text
SmartNotes-AI/
├── client/       # React/Vite frontend
├── server/       # Express API
├── .gitignore
└── README.md
```

## Prerequisites

- Node.js and npm
- A MongoDB instance
- A Firebase project with Authentication configured
- A Google AI Studio/Gemini API key
- Stripe keys if you intend to use credit purchases and webhooks

## Local setup

### 1. Clone the repository

```bash
git clone https://github.com/Abhinav2631/SmartNotes-AI.git
cd SmartNotes-AI
```

### 2. Configure the backend

```bash
cd server
npm install
```

Copy `server/.env.example` to `server/.env` and fill in your own values for `MONGO_URL`, `JWT_SECRET`, `GEMINI_API_KEY`, `STRIPE_SECRET_KEY`, `STRIPE_WEBHOOK_SECRET`, `CLIENT_URL`, and `CLIENT_ORIGIN`. Do not put real credentials in a committed file.

Start the API in a terminal from `server/`:

```bash
npm run dev
```

### 3. Configure the frontend

In a second terminal, from the repository root:

```bash
cd client
npm install
```

Copy `client/.env.example` to `client/.env`. Configure `VITE_API_URL` and all Firebase values for your own Firebase project. Vite variables are compiled into client-side code, so Firebase web configuration is not a substitute for Firebase security rules.

Start the frontend:

```bash
npm run dev
```

### 4. Build and lint the frontend

From `client/`:

```bash
npm run build
npm run lint
```

## Environment files

- `client/.env.example` documents the frontend environment variables.
- `server/.env.example` documents backend environment variables.
- Keep real `.env` files private; they are excluded by `.gitignore`.

## Security notes

- Never commit API keys, database URLs, JWT secrets, or Stripe secrets.
- Use your own Firebase, MongoDB, Gemini, and Stripe configuration.
- Keep privileged API keys on the server and use provider-side restrictions for browser-visible Firebase configuration.
- Configure Firebase rules, authentication settings, payment webhooks, and allowed frontend origins before deployment.

## Attribution and reuse

This repository is an authorized learning/adaptation copy of [SmartNotes-AI by Naresh Chary](https://github.com/NareshChary0430/SmartNotes-AI). The upstream project and its original implementation remain credited to the original creator. This copy has been prepared for personal learning and portfolio practice with permission.

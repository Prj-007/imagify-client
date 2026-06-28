# Imagify — AI Image SaaS

A full-stack AI SaaS application for text-to-image generation. Features credit-based usage, JWT authentication, and payment integration.

**Live Demo:** https://client-kappa-sepia-85.vercel.app

## Tech Stack

- **Frontend:** React.js, Tailwind CSS, Vite
- **Backend:** Node.js, Express.js ([imagify-server](https://github.com/Prj-007/imagify-server))
- **Auth:** JWT
- **Image Generation:** Pollinations.ai (free, no API key required)

## Features

- Text-to-image generation
- Credit-based usage tracking (5 free credits on signup)
- Secure JWT authentication
- Buy more credits (demo mode)

## Getting Started

```bash
npm install
npm run dev
```

Set `VITE_BACKEND_URL` in `.env` to point to your backend.

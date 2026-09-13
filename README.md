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
- Buy more credits via Razorpay (real order creation + payment signature verification)

## Getting Started

```bash
npm install
npm run dev
```

Set `VITE_BACKEND_URL` and `VITE_RAZORPAY_KEY_ID` in `.env` to point to your backend and Razorpay test key.

## Testing the App

The backend uses in-memory storage (no persistent database), so there's no fixed demo login — accounts don't survive a server restart/redeploy. To test:

**1. Create an account**
Go to the live app and register with any name/email/password (e.g. `test@example.com` / `test1234`) — no real email needed, nothing gets sent. You'll start with 5 free credits.

**2. Test image generation**
Enter any prompt on the home page — it calls the free Pollinations.ai API, no payment required.

**3. Test the Razorpay payment flow**
Click "Buy Credits" → pick a plan → click the Razorpay button. The checkout is in **Test Mode**, so:
- **Authorize phone:** this is Razorpay's own contact verification (separate from test-mode payments) and sends a real SMS OTP — use your actual number here, or use the "skip"/"continue as guest" option if shown.
- **Test card:** Card number `4111 1111 1111 1111`, any future expiry date, any 3-digit CVV, any name.
- **Test UPI:** VPA `success@razorpay` simulates an instant successful payment.
- No real money is charged in Test Mode. On success, credits are added only after the backend verifies the payment signature with Razorpay.

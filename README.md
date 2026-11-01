# Kisii Meet Hub — Full Stack

Real dating / social discovery platform for Kisii & Nyamira.

## Features

- Member Registration & Login (JWT + secure cookies)
- User Profiles with **Photo Upload**
- Discover / Swipe interface
- **Real Paystack Integration** (M-Pesa + Cards)
- Unlock phone numbers after payment
- Unlocked numbers list with WhatsApp & Call
- Backend API (Next.js App Router)
- Simple JSON file database (easy to upgrade to PostgreSQL later)

---

## Quick Start (Local)

```bash
# 1. Go into the project
cd kisii-meet-hub-fullstack

# 2. Install dependencies
npm install

# 3. Create environment file
cp .env.example .env

# 4. Edit .env and add your keys
#    - JWT_SECRET (any long random string)
#    - PAYSTACK_SECRET_KEY (from Paystack dashboard)
#    - PAYSTACK_PUBLIC_KEY
#    - NEXT_PUBLIC_APP_URL=http://localhost:3000

# 5. Run
npm run dev
```

Open http://localhost:3000

---

## Paystack Setup (Kenya)

1. Create account at https://paystack.com
2. Go to Settings → API Keys & Webhooks
3. Copy **Test Secret Key** and **Test Public Key**
4. Paste into `.env`
5. For live mode later: switch to Live keys and complete business verification (KRA PIN, etc.)

### Webhook (important for production)

In Paystack Dashboard → Settings → API Keys & Webhooks:

Set Webhook URL to:
```
https://your-domain.com/api/paystack/webhook
```

---

## Deploy to Vercel (Recommended)

1. Push this folder to GitHub
2. Go to https://vercel.com → New Project → Import
3. Add the environment variables from `.env`
4. Deploy

Your site will be live in under 2 minutes.

---

## Photo Upload

- Users can upload profile photos from the Profile page
- Photos are saved in `/public/uploads`
- For production scale, switch to Cloudinary (code is ready to extend)

---

## Project Structure

```
app/
  api/
    auth/          → register, login, me
    profile/       → get & update profile
    upload/        → photo upload
    paystack/      → initialize payment + webhook
    unlock/        → list unlocked numbers
    profiles/      → list people to swipe
  login/
  register/
  discover/        → main swipe screen
  profile/
  unlocked/
lib/
  db.js            → simple JSON database
  auth.js          → JWT + password hashing
```

---

## Next Improvements (optional)

- Real database (PostgreSQL / MongoDB)
- Cloudinary for photos
- SMS OTP login
- Push notifications
- Admin dashboard

---

Built for Kisii Meet Hub.

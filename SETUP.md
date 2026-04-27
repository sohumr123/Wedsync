# Wedding Day — Setup Guide

All code changes are done. Follow these steps to go live.

---

## Step 1 — Get a Resend API key (2 min)

1. Go to https://resend.com and sign up (free)
2. In the dashboard, go to **API Keys** → **Create API Key**
3. Copy the key (starts with `re_...`)

---

## Step 2 — Push code to GitHub (2 min)

1. Go to https://github.com/new and create a new **private** repository
2. In your terminal, from the project root:
   ```bash
   git init
   git add .
   git commit -m "Initial commit - migrated from Vibecode"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

---

## Step 3 — Deploy backend to Railway (5 min)

1. Go to https://railway.app and sign up with GitHub
2. Click **New Project** → **Deploy from GitHub repo**
3. Select your repository, then select the **`backend`** folder as the root
4. Go to **Variables** and add these:

   | Variable | Value |
   |----------|-------|
   | `DATABASE_URL` | `file:./prisma/dev.db` |
   | `BETTER_AUTH_SECRET` | `xivSppM32164rBc2MECqBpfCjfORa6uKmat9b5Mh3ZM=` |
   | `BACKEND_URL` | *(your Railway URL — set this after deploy)* |
   | `RESEND_API_KEY` | `re_8R5WJeic_MMgu8oiPanty7srhVctZpZnv` |
   | `PORT` | `3000` |

5. Railway will give you a URL like `https://your-app.up.railway.app`
6. Go back to Variables and set `BACKEND_URL` to that URL

---

## Step 4 — Update mobile app

Open `mobile/.env.production` and replace `YOUR_RAILWAY_URL` with your actual Railway URL:
```
EXPO_PUBLIC_BACKEND_URL=https://your-app.up.railway.app
```

---

## Step 5 — Run the app locally

**Backend:**
```bash
cd backend
bun install
bun run dev
```

**Mobile:**
```bash
cd mobile
bun install
bunx expo start
```

Scan the QR code with the **Expo Go** app on your phone.

---

## Need to build for App Store / Play Store?

Install EAS CLI:
```bash
npm install -g eas-cli
eas build --platform ios
eas build --platform android
```

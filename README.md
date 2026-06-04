# 🎯 ULTRA BINGO

Telegram Mini App + Web App ሙሉ የሚሰራ Bingo game (Amharic/English UI)።

## ✨ Features

- ✅ **Real-time multiplayer** (Socket.IO)
- ✅ **4 stake tiers** (5 / 10 / 50 / 100 ETB)
- ✅ **2-line Bingo** (host phone ላይ 80% ሽልማት)
- ✅ **Server-side card generation** (deterministic per day)
- ✅ **JWT-like auth tokens** (in-memory sessions)
- ✅ **Deposit/Withdraw** (Telebirr integration ready)
- ✅ **Admin panel** (verify pending deposits)
- ✅ **Referral system** (+5 ETB per invite)
- ✅ **Voice callout** (Amharic TTS)
- ✅ **Auto-mark & manual** modes
- ✅ **Telegram WebApp** integration

## 🚀 Quick Start

```bash
cd ultra-bingo
npm install
npm start
```

Server runs on `http://localhost:3000`

## 📁 Structure

```
ultra-bingo/
├── server.js           # Express + Socket.IO backend
├── package.json
└── public/
    └── index.html      # Frontend (single file)
```

## 🔑 Admin Access

- Admin key: `8084877485`
- Wallet page → "Admin Panel" → paste key → see pending deposits
- Withdraw PIN: `1234`

## 🎮 How to Play (2+ players)

1. User A opens 10 ETB room → picks card → waits in waiting room
2. User B opens 10 ETB room → picks card → countdown 30s starts
3. Host (first player) clicks "▶️ ጨዋታ ጀምር" OR auto-start
4. Numbers called every 3s (75 total)
5. First player to complete 2 lines = winner
6. Winner gets 80% of total pool

## 🧪 Test Flow

1. Open `http://localhost:3000` in **two browser tabs**
2. Register user A in tab 1, user B in tab 2
3. Tab 1: open 10 ETB room → pick card
4. Tab 2: open 10 ETB room → pick card → countdown starts
5. Tab 1: click start → game runs
6. Whoever gets 2 lines first wins

## 🌐 Telegram Deploy

1. Create bot via @BotFather
2. Set menu button URL: `https://your-domain.com`
3. Add HTTPS via Cloudflare / ngrok
4. Done!

## 🔒 Security Notes (for production)

- Replace in-memory `Map` with Redis/PostgreSQL
- Add bcrypt for passwords
- Use real JWT with expiry
- Add rate limiting on `/api/*`
- Move admin key to env variable
- Use real Telebirr API for deposits

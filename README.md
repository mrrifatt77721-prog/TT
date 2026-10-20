# EarnZone Telegram Login Starter

## Files
- `index.html`: polished mobile-first Telegram sign-in screen and app UI.
- `server.js`: Node.js endpoint that verifies Telegram Mini App raw `initData` HMAC and freshness.
- `admin.html`: local admin-interface starter; not connected to users.
- `package.json`: start command.

## Preview
Open `index.html` in a browser. Outside Telegram, Continue with Telegram starts a clearly labelled **local preview session only**. It is not a real login.

## Backend setup
1. Deploy to a Node.js host with HTTPS.
2. Set `BOT_TOKEN` as a private environment variable in the hosting dashboard; never place the token in HTML or commit it.
3. Run `npm start`.
4. Configure the bot's Mini App URL in BotFather to your HTTPS URL.
5. Open the app inside Telegram. The frontend posts raw `Telegram.WebApp.initData` to `/api/auth/telegram`.

## Important production limits
The included server verifies Telegram initData, but it is only an authentication starter. It does not issue persistent sessions, connect a database, or provide a secure admin login. Before real launch, implement secure session cookies, database-backed users, role-based admin access, rate limits, CSRF/origin controls, audit logs, server-side task verification, immutable reward ledger, referral anti-fraud and compliant payout processing. Frontend points and withdrawal forms are only local samples; no real money is paid or transferred. Do not collect real payment details until the full system is built and tested.

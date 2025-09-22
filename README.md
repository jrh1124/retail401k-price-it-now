# Retail401k – Price It Now (Ready to Deploy)

This repo includes:
- Frontend (Vite + React + Tailwind) with the full calculator component
- Serverless API (Vercel Edge) for verification codes + emailing the cost sheet and team notice

## Run locally

```bash
npm i
npm run dev
# open http://localhost:5173
```

## Deploy (Vercel)

```bash
npm i -g vercel
vercel
vercel env add SENDGRID_API_KEY
vercel env add FROM_EMAIL
vercel env add TEAM_EMAIL
vercel --prod
```

Then embed in Squarespace with an iframe pointing to your deployed URL.

## Notes
- Verification codes are stored in-memory in the Edge function for demo purposes. Use Redis/Upstash/Vercel KV for production and add rate limiting + CAPTCHA validation.
- Emails are sent via SendGrid.
# Magic G-Ball — Vercel Deployment

## Files
- `index.html` — the app
- `api/ask.js` — serverless function (keeps API key private)
- `vercel.json` — routing config

## Steps

### 1. Create a GitHub repo
Name it `magic-g-ball` (private is fine).
Drop these three files in exactly as structured:
```
index.html
vercel.json
api/
  ask.js
```

### 2. Connect to Vercel
- Go to vercel.com → Add New Project
- Import your GitHub repo
- Vercel will detect it automatically

### 3. Add your API key
In Vercel project settings → Environment Variables:
```
Name:  ANTHROPIC_API_KEY
Value: your-key-here
```

### 4. Deploy
Vercel deploys automatically on every GitHub push.
Your URL will be: `https://magic-g-ball.vercel.app` (or similar)

## Security
- API key lives only in Vercel environment variables
- Browser never sees the key
- Persona prompts travel server-side only
- Consider adding rate limiting in api/ask.js before public launch

## Substack
Embed with:
```html
<iframe src="https://your-vercel-url.vercel.app" width="100%" height="800px" frameborder="0"></iframe>
```

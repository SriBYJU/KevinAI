# DevAI — AI Coding Agent

A local/deployable AI coding agent powered by Claude, with a Node.js proxy so the API key stays safe on the server.

---

## Setup

### 1. Install Node.js
Download from https://nodejs.org (v18+ recommended)

### 2. Get your Anthropic API key
Sign up at https://console.anthropic.com and create an API key.

### 3. Add your API key
Open `.env` and replace `your_api_key_here` with your actual key:
```
ANTHROPIC_API_KEY=sk-ant-...
```

### 4. Install dependencies
```bash
npm install
```

### 5. Run the server
```bash
npm start
```

Then open your browser to **http://localhost:3000**

---

## Project structure

```
devai-server/
├── server.js        ← Express proxy server (keeps API key secret)
├── .env             ← Your API key goes here (never share this file)
├── package.json
└── public/
    └── index.html   ← The DevAI frontend
```

---

## Deploying online (optional)

You can deploy this to any Node.js host:

- **Railway**: https://railway.app — connect your GitHub repo, set the `ANTHROPIC_API_KEY` environment variable in the dashboard
- **Render**: https://render.com — same process
- **Fly.io**: `fly launch` then set secrets with `fly secrets set ANTHROPIC_API_KEY=sk-ant-...`

Make sure to set `ANTHROPIC_API_KEY` as an environment variable on your host — never commit your `.env` file.

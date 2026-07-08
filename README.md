# ABDULLAH BOTZ

A WhatsApp automation bot built on Baileys, paired and controlled through a Telegram control bot.

## Owner

- **Name:** ABDULLAH
- **Number:** 923041956023

## Features

- `.menu` — Shows all available commands (owner view vs. public view)
- `.public` / `.private` — Toggle whether the bot responds to non-owner chats
- `.antilink` — Remove messages containing group invite links
- `.antidelete` — Re-send messages that were deleted by the sender
- `.anticall` — Auto-reject incoming calls
- `.autoreacts` — Auto-react to incoming messages
- `.status` — Auto-view/like/download WhatsApp statuses
- `.welcome` — Welcome/goodbye messages for group joins/leaves
- `.kick` — Remove a group member (admin only, reply to their message)
- `.dp` — Fetch a user's profile picture
- `.song [name]` / `.video [name]` — Search and send audio/video
- `.ytmp3 [url]` / `.ytmp4 [url]` — Download audio/video from a YouTube URL
- `.vv` — Resend a "view once" message (reply to it)

## Setup

### Prerequisites
- Node.js 16+
- pnpm (or npm)

### Install

```bash
pnpm install
```

### Configure

Edit `.env`:

```
PORT=20664
NODE_ENV=production
OPENAI_API_KEY=your-groq-or-openrouter-key
AI_BASE_URL=https://api.groq.com/openai/v1
AI_MODEL=llama-3.3-70b-versatile
```

> ⚠️ The `.env` in this project currently contains a live-looking Groq API key. Treat it as compromised, rotate/regenerate it from the Groq console, and never commit real keys to a shared or public repository.

Edit `settings.js` for owner details:

```js
module.exports = {
    ownerNumber: '923041956023',
    botName: 'ABDULLAH BOTZ',
    ownerName: 'ABDULLAH'
};
```

### Run

```bash
npm start
```

The bot is controlled through a paired Telegram bot: message it `/start`, then follow the prompts to enter your WhatsApp number and generate a pairing code, which you enter under WhatsApp → Linked Devices → Link with phone number.

## Project Structure

```
├── index.js              # Core bot + Telegram control panel
├── settings.js            # Owner/brand configuration
├── commands/              # One file per command
├── lib/                   # Shared helpers (auth checks, converters, etc.)
└── .env                    # Environment/API configuration
```

## Notes

- Session credentials are stored locally (auth folder created on first pairing).
- This project automates a personal WhatsApp account via an unofficial library (Baileys). Using it is against WhatsApp's Terms of Service and numbers used this way can be banned — use at your own risk, and only on accounts/groups you own or have permission to automate.

## License

For ABDULLAH BOTZ use only.

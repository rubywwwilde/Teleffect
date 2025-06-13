# Teleffect

🦆 Type-safe Telegram Bot API client built with [Effect-TS](https://github.com/Effect-TS/effect) inspired by [GramJS](https://github.com/gram-js/gramjs) and [Telethon](https://github.com/LonamiWebs/Telethon/).

## Important

This library uses Telegram's MTProto protocol. As with any third-party library for Telegram, be careful not to break [Telegram's ToS](https://telegram.org/tos) or Telegram may ban your account.

## Raison d'être

Teleffect is a tool that allows you to write applications that run in browser/server environments and interact with Telegram API. This library handles all the low-level concerns allowing you to focus on app development instead.

Why another Telegram library? GramJS is excellent but bundles Node.js modules making it heavy for certain environments. I wanted a cleaner alternative that leverages Effect-TS for functional programming patterns, better error handling, and schema validation out of the box.

## Installing

```bash
npm install teleffect
```
## Basic usage
⚠️ Never commit API credentials to version control. Add .env to your .gitignore.

### Node.js
```typescript
import { TelegramClient } from "teleffect/node"

const client = TelegramClient.create({
  apiId: Number(process.env.TELEGRAM_API_ID),
  apiHash: process.env.TELEGRAM_API_HASH
})

await client.sendMessage("username", "Hello!")
```

### Browser
```typescript
import { TelegramClient } from "teleffect/browser"

const client = TelegramClient.create({
  apiId: Number(import.meta.env.VITE_TELEGRAM_API_ID), // Vite
  apiHash: import.meta.env.VITE_TELEGRAM_API_HASH // or your bundler's env syntax
})

await client.sendMessage("username", "Hello!")
```

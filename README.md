# Desktop-electron-pet-2.0

A desktop pet built with Electron and powered by a separate Node.js/Express backend that checks Gmail unread mail using OAuth 2.0.

It shows a floating anime-style girl character with a speech bubble that updates with the unread mail count.

## Features

- Transparent draggable floating window
- Custom anime-style SVG character
- Gmail unread count check via OAuth2
- Separate backend to keep secrets off the client
- Polling every 2 minutes

## Prerequisites

- Node.js 18+
- npm
- Google Cloud project with Gmail API enabled
- A Google OAuth 2.0 Client ID and Secret

## Setup Google Gmail OAuth

1. Go to Google Cloud Console: https://console.cloud.google.com/
2. Create a new project or select an existing one
3. Enable the Gmail API
4. Go to APIs & Services → Credentials → Create Credentials → OAuth client ID
5. Choose Application type: Web application
6. Add redirect URI:
   - http://localhost:3000/oauth2callback
7. Save the generated Client ID and Client Secret

## Server setup

Create a file at `server/.env` based on `server/.env.example`:

```env
GOOGLE_CLIENT_ID=your-client-id.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=your-client-secret
SERVER_ROOT_URL=http://localhost:3000
PORT=3000
SESSION_SECRET=replace-with-random-string

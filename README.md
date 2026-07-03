# Standalone ClearKey Downloader Bot (Lite)

This is a simple, standalone Pyrogram bot that downloads ClearKey encrypted streams using `yt-dlp`, decrypts them using `mp4decrypt` (bento4), and merges/uploads them to Telegram.

## Input Format
Send the link to the bot in the following format:
`https://example.com/manifest.mpd*KID:KEY`

Example:
`https://licensing.bitmovin.com/v1/licensing/wrm/manifest.mpd*10000000000000000000000000000001:20000000000000000000000000000002`

## Deployment (Docker)

1. Clone or copy this folder.
2. Edit the `.env` or set environment variables:
   - `BOT_TOKEN`: Your Telegram Bot Token
   - `API_ID`: Your API ID
   - `API_HASH`: Your API Hash

3. Build and Run:
   ```bash
   docker build -t clearkey-downloader .
   docker run -d --name clearkey-bot --env-file .env clearkey-downloader
   ```

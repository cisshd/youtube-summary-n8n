# YouTube Summary (n8n + Gemini + Lovable)

A lightweight tool that turns any YouTube link into a clean structured summary.  
The UI (Lovable) sends a YouTube URL to an n8n webhook. n8n fetches the transcript, summarizes it using Google Gemini, and returns a JSON response.  
(Optional) It can also send the summary to Telegram.

## Features
- ✅ Paste a YouTube URL → get a summary instantly
- ✅ Works via n8n Webhook API (POST)
- ✅ Transcript fetching via RapidAPI
- ✅ Summarization via Gemini (free tier if available)
- ✅ Optional Telegram delivery
- ✅ Returns clean JSON for any frontend (Lovable / React / etc.)

## Architecture
Lovable (Frontend)
→ n8n Webhook (/webhook/ytube)
→ Transcript API (RapidAPI)
→ Gemini summarize
→ JSON response { ok, summary }
→ (Optional) Telegram message

## API (Webhook)
**POST** `/webhook/ytube`

### Request Body
```json
{
  "youtubeUrl": "https://www.youtube.com/watch?v=VIDEO_ID"
}

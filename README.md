# ♟️ AI-Powered Chess Puzzle Shorts Automation

A fully automated system that creates and publishes YouTube Shorts featuring chess puzzles — built using no-code tools, APIs, and AI integrations.

This project demonstrates end-to-end automation for content creation using **n8n**, **Shotstack**, **Google Sheets**, and the **YouTube API**.

---

## 🚀 Overview

**Goal:** Automatically generate and upload a chess puzzle Short every day with:
- Puzzle image from FEN notation
- Caption (e.g., "White to play & mate in 2")
- Random background music
- Auto-upload to YouTube
- Status update in Google Sheet

---

## 🧰 Tech Stack

| Tool/Service     | Purpose                                      |
|------------------|----------------------------------------------|
| `n8n` (cloud)    | No-code workflow orchestration               |
| `Google Sheets`  | Source of chess puzzles and status updates   |
| `Lichess API`    | FEN-based chessboard image generation        |
| `Shotstack`      | Video creation using dynamic templates       |
| `Netlify`        | Hosting background audio clips (.mp3)        |
| `YouTube API`    | Video publishing with title & tags           |

---

## 🎬 Workflow Summary

1. **Trigger**: Manual or scheduled in n8n
2. **Read Sheet**: Find next puzzle where `status != done`
3. **Generate Board**: Use Lichess API to render image from FEN
4. **Pick Audio**: Randomly select a hosted `.mp3` file
5. **Create Video**: Merge `IMAGE`, `CAPTION`, and `AUDIO` into Shotstack template
6. **Wait**: Loop until video render completes
7. **Upload**: Publish video to YouTube
8. **Update Sheet**: Set `status = done`, `date_used = today`

---

## 📊 Google Sheet Structure

| Title                | FEN                                    | Status | Date Used   |
|----------------------|-----------------------------------------|--------|-------------|
| White to mate in 2   | r1bqkbnr/pppp1ppp/2n5/4p3/...           |        |             |
| Black to mate in 1   | 6k1/5ppp/8/8/8/8/5PPP/6K1 w - - 0 1     | done   | 2025-06-06  |

---

## 🖼️ Shotstack Template

- **9:16** mobile format (1080x1920)
- Text overlay (top): puzzle caption
- Chessboard image (center)
- Background audio (Netlify URL)
- Export format: `.mp4`, 25 fps

---

## 🔊 Audio Hosting with Netlify

- Store `.mp3` clips in a public GitHub repo
- Deploy using Netlify for static hosting
- Example: `https://chess-audio.netlify.app/pzaudio2.mp3`
- Audio is randomly selected using `Set` node in n8n

---

## 📺 Sample Output

> Coming soon — [YouTube Channel](https://youtube.com/@yourchannel)  
> Add screenshots or Shorts links here

---

## 🧠 Key Learnings

- API integration across Shotstack, YouTube, and Lichess
- Dynamic content injection with merge fields
- Reusable no-code automation workflows in `n8n`
- Handling video render queues, delays, and retries
- Cloud-based audio hosting and asset management

---

## 🛣️ Potential Improvements

- Puzzle difficulty filtering (Easy/Medium/Hard)
- Daily scheduler trigger (CRON)
- Auto-post to Twitter/Instagram
- Multilingual captions
- Use Whisper for subtitles
- Auto-generate thumbnails with branding

---

## 👤 Author

**Ronak Mehta**  
📍 Montreal, Canada  
💼 Applied AI & Automation Engineering Enthusiast  
📬 [LinkedIn](https://linkedin.com/in/ronakmehta)  
🧠 Building intelligent automation workflows

---


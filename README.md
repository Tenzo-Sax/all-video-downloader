
# AllDL API

A  universal downloader API for social media platforms. Download videos from YouTube, Facebook, TikTok, and Instagram with a simple API call.

## Features

- 🎥 **Multi-Platform Support**: YouTube, Facebook, TikTok, Instagram
- 🔄 **Universal Endpoint**: Auto-detect platform from URL
- 📱 **Mobile Optimized**: Works seamlessly on all devices
- ⚡ **Fast & Reliable**: Direct video download links
- 🎵 **Audio Support**: Extract audio from videos
- 🔧 **Easy to Use**: Simple REST API

## Platforms Supported

- ✅ YouTube (with quality selection)
- ✅ Facebook (all video formats)
- ✅ TikTok (HD quality)
- ✅ Instagram (reels, posts, videos)

## Installation

```bash
git clone https://github.com/tenzo-sax/alldl-api.git
cd alldl-api
npm install
```

Configuration

Edit config.json to enable/disable platforms:

```json
{
    "dev": "Tenzo",
    "version": "1.0.0",
    "api_name": "alldl",
    "platforms": {
        "youtube": true,
        "facebook": true,
        "tiktok": true,
        "instagram": true
    }
}
```

Usage

Start Server

```bash
npm start
# or with auto-reload
npm run dev
```

API Endpoints

YouTube Downloader

```http
GET /ytb?url=YOUTUBE_URL&format=720
```

Facebook Downloader

```http
GET /facebook?url=FACEBOOK_URL
```

TikTok Downloader

```http
GET /tiktok?url=TIKTOK_URL
```

Instagram Downloader

```http
GET /instagram?url=INSTAGRAM_URL
```

Universal Downloader (Auto-Detect)

```http
GET /alldl?url=ANY_URL
```

Response Format

```json
{
    "success": true,
    "url": "https://example.com/video.mp4",
    "type": "video",
    "dev": "Tenzo"
}
```

Error Response

```json
{
    "success": false,
    "message": "No video found"
}
```

Examples

YouTube with Quality Selection

```javascript
fetch('https://your-api.com/ytb?url=https://youtu.be/VIDEO_ID&format=1080')
    .then(res => res.json())
    .then(data => console.log(data.url));
```

Universal Downloader

```javascript
fetch('https://your-api.com/alldl?url=https://www.tiktok.com/@user/video/123')
    .then(res => res.json())
    .then(data => console.log(data.url));
```

Facebook Video

```javascript
fetch('https://your-api.com/facebook?url=https://www.facebook.com/watch?v=123')
    .then(res => res.json())
    .then(data => console.log(data.url));
```

Instagram Reel

```javascript
fetch('https://your-api.com/instagram?url=https://www.instagram.com/reel/ABC123')
    .then(res => res.json())
    .then(data => console.log(data.url));
```

Supported URL Formats

YouTube

· https://youtube.com/watch?v=VIDEO_ID
· https://youtu.be/VIDEO_ID
· https://www.youtube.com/watch?v=VIDEO_ID
· https://m.youtube.com/watch?v=VIDEO_ID

Facebook

· https://facebook.com/watch?v=VIDEO_ID
· https://fb.com/VIDEO_ID
· https://fb.watch/VIDEO_ID
· https://m.facebook.com/watch?v=VIDEO_ID
· https://www.facebook.com/share/r/VIDEO_ID

TikTok

· https://tiktok.com/@user/video/VIDEO_ID
· https://vm.tiktok.com/VIDEO_ID
· https://vt.tiktok.com/VIDEO_ID
· https://www.tiktok.com/@user/video/VIDEO_ID

Instagram

· https://instagram.com/p/VIDEO_ID
· https://instagr.am/p/VIDEO_ID
· https://www.instagram.com/reel/VIDEO_ID
· https://www.instagram.com/tv/VIDEO_ID

Project Structure

```
alldl-api/
├── index.js          # Main server file
├── config.json       # Configuration
├── package.json      # Dependencies
├── README.md         # Documentation
└── lib/
    ├── alldl.js      # Main handler
    ├── ytb.js        # YouTube downloader
    ├── facebook.js   # Facebook downloader
    ├── tiktok.js     # TikTok downloader
    └── instagram.js  # Instagram downloader
```

Deployment

Deploy to Render

1. Fork this repository
2. Create a new Web Service on Render
3. Connect your GitHub repository
4. Use the following settings:
   · Build Command: npm install
   · Start Command: npm start
   · Environment: Node.js

Deploy to Vercel

```bash
vercel
```

Deploy to Heroku

```bash
heroku create
git push heroku main
```

Dependencies

· Express - Web framework
· Axios - HTTP client
· Cheerio - HTML parsing

License

MIT License - Free to use and modify.

Credits

Developed with ❤️ by Tenzo

---

⭐ Star this repo if you find it useful!

```

## **.gitignore**
```

node_modules/
cache/
config.json
.env
.DS_Store
*.log

```

## **package.json**
```json
{
    "name": "alldl-api",
    "version": "1.0.0",
    "description": "All download API for social media platforms",
    "main": "index.js",
    "scripts": {
        "start": "node index.js",
        "dev": "nodemon index.js"
    },
    "dependencies": {
        "express": "^4.18.2",
        "axios": "^1.6.0",
        "cheerio": "^1.0.0-rc.12"
    },
    "devDependencies": {
        "nodemon": "^3.0.1"
    },
    "author": "Tenzo",
    "license": "MIT",
    "repository": {
        "type": "git",
        "url": "https://github.com/tenzo-sax/alldl-api"
    }
}
```

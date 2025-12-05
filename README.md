# 🎮 Soundipity Stream Overlay System

A complete, production-ready interactive overlay system for Twitch/YouTube streams with community voting widgets, AI-powered trivia, and real-time control dashboard.

## ✨ Features

### 🎨 Interactive Widgets
- **Feelings Jars** (12 emotions) - Community votes on vibes with colored balls
- **Zodiac Jars** (12 signs) - Astrological identity voting with stars
- **Creative Roles** (6 roles) - Community role identification with orbs
- **AI Trivia Game** - Claude-powered trivia with leaderboards

### 🎛️ Control Dashboard
- Real-time control of all widgets
- Simulate chat activity for testing
- Manual controls for each widget
- localStorage-based communication

### 📺 Stream Grid Overlay
- 3x3 grid layout (1920x1080)
- 4 widget cells + 5 transparent cells for custom content
- Toggle clean mode for production
- OBS-ready with proper transparency

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/ibrahimmort/soundipity.git
cd soundipity
```

### 2. Test Everything Works
Open `connection-test.html` in your browser to verify localStorage communication works.

### 3. For Streaming

Open TWO browser windows:

1. **Control Dashboard** (Second Monitor) - `control-dashboard.html`
2. **Stream Overlay** (OBS Browser Source) - `stream-grid-overlay.html` (1920x1080)

## 📁 Project Structure

```
soundipity/
├── widgets/
│   ├── feelings-jars.html & feelings-jars-compact.html
│   ├── zodiac-jars.html & zodiac-jars-compact.html
│   ├── creative-roles.html & creative-roles-compact.html
│   └── trivia-game.html & trivia-game-compact.html
├── stream-grid-overlay.html   # Main 3x3 grid overlay
├── control-dashboard.html     # Master control panel
├── connection-test.html       # Test localStorage
├── README.md                  # This file
└── SETUP-GUIDE.md            # Detailed instructions
```

## 🎮 Widget Commands

### 💭 Feelings Jars
`!uplifting`, `!melancholic`, `!energetic`, `!chill`, `!nostalgic`, `!dark`, `!romantic`, `!playful`, `!epic`, `!dreamy`, `!rebellious`, `!empowering`

### ⭐ Zodiac Jars
`!aries`, `!taurus`, `!gemini`, `!cancer`, `!leo`, `!virgo`, `!libra`, `!scorpio`, `!sagittarius`, `!capricorn`, `!aquarius`, `!pisces`

### 🎨 Creative Roles
`!hitmaker`, `!listener`, `!author`, `!voiceartist`, `!reader`, `!artist`

### 🎯 Trivia Game
`!vote [1-8]` - Vote for trivia topic
`!a`, `!b`, `!c`, `!d` - Answer questions

## 🔧 Technical Details

### localStorage Communication
Dashboard sends commands via localStorage, widgets listen and respond in real-time.

### Chat Integration
Each widget exposes:
```javascript
window.processChatCommand(username, message);
```

### AI Integration
Trivia uses Claude API (no key required):
- Auto-generates 8 topics on load
- Creates 10 questions when START is clicked
- **Critical fix:** START button properly waits for async generation

## 📺 OBS Setup

1. Add Browser Source
2. URL: `file:///path/to/soundipity/stream-grid-overlay.html`
3. Size: 1920x1080
4. Place webcam/visualizers over empty cells

## 🐛 Troubleshooting

**Dashboard not working?**
- Make sure grid overlay is open in another tab
- Both files must be from same folder
- Try connection-test.html first

**Widgets not loading?**
- Check browser console for 404 errors
- Verify /widgets/ folder exists
- Try opening widgets individually

**localStorage issues?**
- Use a local web server (recommended):
```bash
python -m http.server 8000
# Then open http://localhost:8000
```

## 🎨 Customization

All colors, commands, and layouts can be customized by editing the HTML/CSS/JS files directly. Each widget has clearly commented sections.

## 📊 Performance

- Max 50-60 items per jar (auto-cleanup)
- Smooth animations (~0.5s)
- Grid: 1920x1080, Cells: ~640x360
- Chrome/Firefox/Edge compatible

## 📄 License

MIT License - Free to use and modify!

## 🙏 Credits

- Built with Claude Code by Anthropic
- Designed for Soundipity Creations
- AI trivia powered by Claude API

---

**Made with 💜 for the Soundipity community**

For detailed setup instructions, see [SETUP-GUIDE.md](SETUP-GUIDE.md)

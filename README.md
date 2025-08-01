# 🤖 Shopee Live Assistant

Advanced multi-account automation tool for Shopee Live streaming platform with real-time monitoring and comprehensive action capabilities.

## ✨ Features

### 🎯 Core Automation
- **Multi-Account Management** - Upload and manage multiple Shopee accounts via cookie files
- **Live Chat Automation** - Send custom messages automatically
- **Social Actions** - Auto like, follow, and buy actions
- **Real-time Monitoring** - Live stream screenshot capture with FFmpeg

### 🚀 Advanced Capabilities
- **Concurrent/Sequential Execution** - Choose how accounts execute tasks
- **Rate Limiting** - Built-in protection against API abuse
- **Session Monitoring** - Auto-detect when live streams end
- **Comprehensive Logging** - Full audit trail of all activities
- **Responsive UI** - Mobile-friendly web interface

### 🔧 Technical Features
- Real-time WebSocket communication
- SQLite database for persistence
- Token bucket rate limiting
- Automatic screenshot cleanup
- Cookie format validation

## 📋 Prerequisites

### System Requirements
- Python 3.8+
- FFmpeg (for screenshot capture)
- Modern web browser

### Python Dependencies
```bash
Flask==2.3.3
Flask-SocketIO==5.3.6
requests==2.31.0
Pillow==10.0.1
```

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/classyid/shopee-live-assistant.git
cd shopee-live-assistant
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Install FFmpeg
**Windows:**
```bash
# Download from https://ffmpeg.org/download.html
# Add to PATH
```

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install ffmpeg
```

**macOS:**
```bash
brew install ffmpeg
```

### 4. Run Application
```bash
python app.py
```

### 5. Access Interface
Open browser and navigate to `http://localhost:7722`

## 📖 Usage Guide

### Step 1: Prepare Cookie Files
1. Login to Shopee in browser
2. Export cookies in Netscape format
3. Save as `.txt` files

### Step 2: Upload Accounts
1. Click upload area in web interface
2. Select multiple cookie `.txt` files
3. Verify accounts are loaded successfully

### Step 3: Configure Session
1. Get Shopee Live session ID from URL
2. Paste session ID in configuration
3. Click "Get Info" to fetch stream details

### Step 4: Setup Actions
1. Select desired actions (Message/Like/Follow/Buy)
2. Configure action-specific parameters
3. Set execution mode and timing

### Step 5: Start Automation
1. Review configuration
2. Click "Start Task"
3. Monitor real-time logs and screenshot

## 🔧 Configuration

### Message Configuration
- **UUID & UserSig**: Required for chat functionality
- **Custom Messages**: Multi-line text input
- **Random Selection**: Messages chosen randomly

### Like Configuration
- **Like Count**: Number of likes per action (1-100)
- **Timing**: Controlled by global delay setting

### Follow Configuration
- **Shop ID**: Auto-filled from session info
- **One-time Action**: Follow executed once per account

### Execution Settings
- **Delay**: Time between actions (seconds)
- **Mode**: Concurrent vs Sequential
- **Loop**: Limited iterations or unlimited

## 🛡️ Safety Features

### Rate Limiting
- Token bucket algorithm prevents API abuse
- Automatic backoff on rate limits
- Configurable request rates

### Session Monitoring
- Real-time stream status checking
- Auto-stop when stream ends
- Offline detection with notifications

### Error Handling
- Comprehensive exception catching
- Detailed error logging
- Graceful degradation

## 📊 Monitoring & Logging

### Real-time Dashboard
- Live stream screenshot updates
- Viewer count and engagement metrics
- Session duration and status

### Activity Logs
- Color-coded status messages
- Account-specific action tracking
- Timestamp for all events

### Database Persistence
- Session history storage
- Task execution audit trail
- Performance analytics

## ⚖️ Legal Disclaimer

This tool is for educational purposes only. Users are responsible for:
- Complying with Shopee Terms of Service
- Respecting rate limits and platform rules
- Using automation responsibly
- Understanding legal implications

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Issues**: GitHub Issues for bug reports
- **Discussions**: GitHub Discussions for questions
- **Wiki**: Detailed documentation and guides

## 🔄 Changelog

### Version 1.0.0
- Initial release
- Multi-account cookie management
- Real-time automation actions
- Screenshot monitoring
- Database logging
- Web-based interface

---

⭐ **Star this repository if it helped you!**
```

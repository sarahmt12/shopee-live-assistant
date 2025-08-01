## 🚀 Cara Deploy

### 1. Local Development
```bash
# Clone repository
git clone https://github.com/classyid/shopee-live-assistant.git
cd shopee-live-assistant

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# atau venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Install FFmpeg
# Windows: Download dari https://ffmpeg.org/
# Linux: sudo apt install ffmpeg
# Mac: brew install ffmpeg

# Run aplikasi
python app.py
```

### 2. Docker Deployment
```dockerfile
FROM python:3.9-slim

# Install FFmpeg
RUN apt-get update && apt-get install -y ffmpeg && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

EXPOSE 7722

CMD ["python", "app.py"]
```

```bash
# Build dan run
docker build -t shopee-live-assistant .
docker run -p 7722:7722 shopee-live-assistant
```

### 3. VPS Deployment (Ubuntu)
```bash
# Update sistem
sudo apt update && sudo apt upgrade -y

# Install Python dan dependencies
sudo apt install python3 python3-pip python3-venv ffmpeg -y

# Clone dan setup
git clone https://github.com/username/shopee-live-assistant.git
cd shopee-live-assistant
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Install PM2 untuk process management
sudo npm install -g pm2

# Create ecosystem file
echo "module.exports = {
  apps: [{
    name: 'shopee-live-assistant',
    script: 'app.py',
    interpreter: './venv/bin/python',
    env: {
      PORT: 7722
    }
  }]
}" > ecosystem.config.js

# Start dengan PM2
pm2 start ecosystem.config.js
pm2 save
pm2 startup
```

### 4. Heroku Deployment
```bash
# Install Heroku CLI
# Create Procfile
echo "web: python app.py" > Procfile

# Create requirements.txt dengan versions
echo "Flask==2.3.3
Flask-SocketIO==5.3.6
requests==2.31.0
gunicorn==21.2.0" > requirements.txt

# Create runtime.txt
echo "python-3.9.16" > runtime.txt

# Deploy
heroku create shopee-live-assistant
git add .
git commit -m "Initial commit"
git push heroku main
```

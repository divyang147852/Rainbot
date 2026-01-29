# Rain Alert Telegram Bot

Bot that monitors rain alerts from RainsAlertss channel and forwards formatted messages with INR conversion.

## Features
- Monitors India, Pakistan, and Nigeria rain alerts
- Converts USD to INR with live exchange rates
- BIG RAIN alerts for amounts > ₹500 INR
- Country detection with flags 🇮🇳 🇵🇰 🇳🇬

## Setup

### Local Testing
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Set environment variables:
   ```powershell
   $env:API_ID="31561349"
   $env:API_HASH="your_hash"
   $env:SOURCE_CHANNEL="RainsAlertss"
   $env:TARGET_CHANNEL="divurainalerts"
   ```

3. Run the bot:
   ```bash
   python telethon_nigeria_monitor.py
   ```

### AWS EC2 Deployment

1. Launch Amazon Linux EC2 instance

2. Connect and install dependencies:
   ```bash
   sudo yum update -y
   sudo yum install python3 python3-pip git -y
   ```

3. Clone repository:
   ```bash
   git clone https://github.com/divyang139/Rainsalert.git
   cd Rainsalert
   pip3 install -r requirements.txt
   ```

4. Create .env file:
   ```bash
   nano .env
   ```
   Add your credentials:
   ```
   API_ID=31561349
   API_HASH=your_hash
   SOURCE_CHANNEL=RainsAlertss
   TARGET_CHANNEL=divurainalerts
   ```

5. First run (authentication):
   ```bash
   python3 telethon_nigeria_monitor.py
   ```
   Enter phone number and OTP when prompted

6. Run in background:
   ```bash
   nohup python3 telethon_nigeria_monitor.py > bot.log 2>&1 &
   ```

7. Check logs:
   ```bash
   tail -f bot.log
   ```

## Environment Variables
- `API_ID`: Telegram API ID
- `API_HASH`: Telegram API Hash
- `SOURCE_CHANNEL`: Channel to monitor (RainsAlertss)
- `TARGET_CHANNEL`: Your target channel

# How to Get Your Discord User ID

## Method 1: Desktop Discord
1. Open Discord desktop app
2. Go to Settings (gear icon)
3. Go to "Advanced" in the left sidebar
4. Enable "Developer Mode"
5. Close settings
6. Right-click on your own profile picture
7. Click "Copy User ID"

## Method 2: Web Discord
1. Go to discord.com and log in
2. Press F12 (open Developer Tools)
3. Go to Console tab
4. Type: `document.querySelector('[data-user-id]').getAttribute('data-user-id')`
5. Press Enter
6. Copy the number that appears

## Method 3: From a Message
1. Enable Developer Mode (Settings > Advanced > Developer Mode)
2. Send a message in any channel
3. Right-click on your message
4. Click "Copy Message ID" 
5. Go to: https://discord.id/
6. Paste the Message ID and it will show your User ID

## Your User ID Format
Should be a long number like: `123456789012345678`

## Test Your ID
Once you have it, you can test at:
https://lanyard.cnrad.dev/api/v1/users/YOUR_USER_ID

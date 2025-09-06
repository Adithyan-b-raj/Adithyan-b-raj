# Working Spotify Widget Setup

## The Problem
Most public Spotify widgets on GitHub don't work because:
1. They require YOUR Spotify authentication
2. Public services get rate-limited
3. They need your specific Spotify credentials

## Solution: Deploy Your Own Widget

### Step 1: Fork & Deploy
1. Go to: https://github.com/kittinan/spotify-github-profile
2. Click "Fork" to your account
3. Go to https://vercel.com/ and sign in with GitHub
4. Click "New Project" → Import your forked repo

### Step 2: Spotify Developer Setup
1. Go to https://developer.spotify.com/dashboard/
2. Click "Create an App"
3. Fill in:
   - App name: `GitHub Profile Spotify`
   - App description: `Shows current song on GitHub`
   - Redirect URI: `http://localhost:3000/callback`
4. Save your Client ID and Client Secret

### Step 3: Environment Variables in Vercel
Add these in your Vercel project settings → Environment Variables:

```
SPOTIFY_CLIENT_ID=your_client_id_here
SPOTIFY_SECRET_KEY=your_client_secret_here  
SPOTIFY_REFRESH_TOKEN=leave_empty_for_now
```

### Step 4: Get Your Refresh Token
1. Deploy the app (it will work partially)
2. Visit your app: `https://your-app.vercel.app/`
3. It will redirect to Spotify for authorization
4. After authorizing, you'll see your refresh token
5. Copy that token back to Vercel environment variables
6. Redeploy

### Step 5: Update Your README
Replace the widget URL with:
```markdown
<img src="https://your-app.vercel.app/api/spotify" alt="Current Spotify Song" width="400"/>
```

## Alternative: Working Public Services

### Option 1: Lanyard (Discord Required)
If you use Discord, Lanyard can show Spotify activity:
1. Join Lanyard Discord: https://discord.gg/WScAm7vNUF  
2. Enable Spotify in Discord
3. Use: `https://lanyard.cnrad.dev/api/v1/users/YOUR_DISCORD_ID`

### Option 2: Last.fm Integration  
1. Create Last.fm account
2. Connect Spotify to Last.fm
3. Use Last.fm widgets (more reliable)

## Quick Test
Your current widget URL: 
`https://spotify-github-profile.vercel.app/api/spotify?background_color=0d1117&border_color=ffffff`

This might work if the public instance is running, but for guaranteed functionality, deploy your own.

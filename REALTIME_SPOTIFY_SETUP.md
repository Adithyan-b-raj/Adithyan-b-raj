# 🎵 Real-time Spotify Widget Setup Guide

## Step 1: Spotify Developer App Setup

### 1.1 Create Spotify App
1. Visit: https://developer.spotify.com/dashboard/
2. Click "Create App"
3. Fill in details:
   - **App name**: `GitHub Profile Spotify`
   - **App description**: `Real-time current song display for GitHub profile`
   - **Website**: `https://github.com/Adithyan-b-raj`
   - **Redirect URIs**: `http://localhost:3000/callback`
4. Accept terms and click "Create"
5. **SAVE**: Client ID and Client Secret

### 1.2 Configure App Settings
1. Click on your created app
2. Go to "Settings"
3. Add redirect URI: `https://YOUR_VERCEL_APP.vercel.app/api/callback`
4. Save settings

## Step 2: Deploy to Vercel

### 2.1 Fork Repository
1. Go to: https://github.com/kittinan/spotify-github-profile
2. Click "Fork" to your account
3. Wait for fork to complete

### 2.2 Deploy to Vercel
1. Go to: https://vercel.com/
2. Sign in with GitHub
3. Click "New Project"
4. Import your forked `spotify-github-profile` repository
5. **DON'T DEPLOY YET** - Add environment variables first

### 2.3 Add Environment Variables
In Vercel project settings, add these:

```env
SPOTIFY_CLIENT_ID=your_client_id_from_step_1
SPOTIFY_SECRET_KEY=your_client_secret_from_step_1
SPOTIFY_REFRESH_TOKEN=leave_empty_for_now
```

### 2.4 Deploy
1. Click "Deploy" 
2. Wait for deployment to complete
3. Copy your Vercel app URL (e.g., `https://your-app.vercel.app`)

## Step 3: Get Refresh Token

### 3.1 Initial Authorization
1. Visit your deployed app: `https://your-app.vercel.app`
2. You'll see a "Login with Spotify" button
3. Click it and authorize the app
4. You'll be redirected and see your refresh token
5. **COPY THIS TOKEN** - you'll need it

### 3.2 Update Environment Variables
1. Go back to Vercel project settings
2. Update the `SPOTIFY_REFRESH_TOKEN` with the token from step 3.1
3. Redeploy the application

## Step 4: Update GitHub Profile

### 4.1 Test Your Widget
Visit: `https://your-app.vercel.app/api/spotify`
- If working: You'll see an SVG with your current song
- If not working: Check environment variables and redeploy

### 4.2 Add to README
Replace the static music section with:

```markdown
### 🎵 **Currently Vibing To**

<div align="center">

<a href="https://open.spotify.com/user/31qf4aaodpi4nb6iluyfdvozsmyu">
  <img src="https://YOUR_VERCEL_APP.vercel.app/api/spotify?background_color=0d1117&border_color=ffffff" alt="Current Spotify Song" width="400"/>
</a>

*Updates in real-time when I'm listening to music on Spotify* 🎧

</div>
```

## Step 5: Customization Options

### Available Parameters:
- `background_color` - Background color (hex without #)
- `border_color` - Border color (hex without #)  
- `text_color` - Text color (hex without #)
- `bar_color` - Progress bar color (hex without #)
- `hide_explicit` - Hide explicit tracks (true/false)

### Example Customizations:
```markdown
<!-- Dark theme matching your profile -->
<img src="https://your-app.vercel.app/api/spotify?background_color=0d1117&border_color=FF6B9D&text_color=ffffff&bar_color=1DB954" />

<!-- Compact version -->
<img src="https://your-app.vercel.app/api/spotify?background_color=0d1117&border_color=ffffff&hide_explicit=true" width="300"/>
```

## Troubleshooting

### Widget Not Updating?
1. Check if Spotify is playing music
2. Verify refresh token is correct
3. Check Vercel deployment logs
4. Ensure app has proper permissions

### "Not Playing" Message?
1. Make sure Spotify is actually playing
2. Try playing a song and wait 30 seconds
3. Refresh the widget URL directly

### Token Expired?
1. Revisit your app URL to get new token
2. Update environment variable in Vercel
3. Redeploy the application

## Security Notes
- Never share your Client Secret publicly
- Keep your refresh token private
- The service only reads your currently playing track
- No personal data is stored or shared

## Success Indicators
✅ Spotify app created and configured
✅ Vercel deployment successful  
✅ Refresh token obtained and configured
✅ Widget shows current song when music is playing
✅ GitHub README updated with working widget

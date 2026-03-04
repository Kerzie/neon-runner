# Neon Runner - MIT App Inventor Integration Guide

## Overview
Neon Runner is a mobile-optimized endless runner game built with HTML5, CSS3, and JavaScript. This guide shows how to integrate it into MIT App Inventor using the WebViewer component.

## Files Required
- `index.html` - Main game file (self-contained)

## MIT App Inventor Setup

### 1. Components Needed
- **WebViewer** (1)
  - Set `Width` to `Fill Parent`
  - Set `Height` to `Fill Parent`
  - Set `HomeUrl` to file path or URL
- **Button** (optional for testing)
  - For loading/reloading the game

### 2. Loading the Game

#### Option A: Local File (Testing)
1. Upload `index.html` to MIT App Inventor assets
2. Set WebViewer `HomeUrl` to: `index.html`
3. Or use blocks: `WebViewer1.GoToUrl("index.html")`

#### Option B: Web Hosting (Production)
1. Host `index.html` on a web server (GitHub Pages, Netlify, etc.)
2. Set WebViewer `HomeUrl` to your hosted URL
3. Example: `https://yourusername.github.io/NeonRunner/index.html`

### 3. Mobile Optimization Features
- **Touch Controls**: Single tap to jump
- **Responsive Design**: Adapts to any screen size
- **Performance**: Optimized for mobile browsers
- **No Scrolling**: Game locks viewport during gameplay
- **Local Storage**: Saves high scores between sessions

### 4. Game Features
- **Endless Running**: Procedurally generated obstacles
- **Jump Physics**: Realistic gravity and velocity
- **Collision Detection**: Obstacle and coin collection
- **Score System**: Points + coin bonuses
- **Lives System**: 3 lives with visual feedback
- **Difficulty Scaling**: Speed increases every 500 points
- **High Score**: Persistent storage using localStorage
- **Visual Effects**: Neon aesthetic with animations

### 5. Controls
- **Single Tap**: Jump (anywhere on screen)
- **Auto-run**: Character runs automatically
- **Responsive**: Works on all mobile devices

### 6. Game States
- **Main Menu**: Start screen with high score
- **Playing**: Active gameplay
- **Game Over**: Score display with retry/menu options

## Technical Specifications

### Performance
- **60 FPS Target**: RequestAnimationFrame for smooth animation
- **Optimized Rendering**: CSS transforms and animations
- **Memory Efficient**: Object pooling for game elements
- **Battery Friendly**: Pauses when not visible

### Compatibility
- **iOS Safari**: Full support
- **Android Chrome**: Full support
- **WebView**: Compatible with MIT App Inventor WebViewer
- **Screen Sizes**: Responsive from 320px to 4K+

### File Size
- **Single File**: ~15KB (HTML, CSS, JS combined)
- **No External Dependencies**: Self-contained
- **Fast Loading**: Optimized for mobile networks

## MIT App Inventor Blocks (Optional Enhancements)

### Basic Loading
```
when Screen1.Initialize
do
    WebViewer1.GoToUrl("index.html")
```

### Reload Function
```
when ButtonReload.Click
do
    WebViewer1.Reload
```

### Fullscreen Toggle (Advanced)
```
when ButtonFullscreen.Click
do
    call WebViewer1.RunJavaScript("document.documentElement.requestFullscreen()")
```

### Get Score Data (Advanced)
```
when ButtonGetScore.Click
do
    call WebViewer1.RunJavaScript("localStorage.getItem('neonRunnerHighScore')")
    set LabelScore.Text to WebViewer1.StringFromJsResponse
```

## Troubleshooting

### Common Issues
1. **Game Not Loading**: Check file path in WebViewer URL
2. **Touch Not Working**: Ensure `touch-action: none` in CSS
3. **Performance Issues**: Close other apps on device
4. **Score Not Saving**: Check localStorage permissions

### Testing Tips
- Test on actual mobile device (not just emulator)
- Check both iOS and Android if possible
- Test in both portrait and landscape
- Verify touch responsiveness

## Deployment

### For Distribution
1. Host on a reliable web server
2. Use HTTPS for secure loading
3. Consider CDN for faster loading
4. Test on target devices before release

### For Classroom Use
- Pre-load HTML file in app assets
- Use local file path for offline capability
- Consider adding reset/clear functionality

## Support
This game is designed to work seamlessly with MIT App Inventor's WebViewer component. The responsive design ensures compatibility across all mobile devices and screen sizes.

## License
Free for educational and commercial use. No attribution required.

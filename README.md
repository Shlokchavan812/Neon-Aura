# 🌈 Neon Aura AR - Advanced Hand Tracking Experience

A cutting-edge **Augmented Reality hand tracking application** that transforms your hands into an interactive neon-powered visual and audio experience. Built with MediaPipe, Canvas 2D, and Web Audio API.

## ✨ Features

### Core Functionality
- **Real-time Hand Detection** - Tracks up to 2 hands with 21 landmarks using MediaPipe
- **Gesture Recognition**
  - Pinch Detection (thumb + index finger proximity)
  - Hand Spread Analysis (fist vs. open hand detection)
- **Multi-Theme Visual Engine**
  - Rainbow (HSL-based gradient animation)
  - Cyberpunk (High-contrast alternating colors)
  - Lava (Warm orange/red with pulsing effects)
  - Ocean (Blue/cyan palette)
  - Galaxy (Purple/pink cosmic theme)

### Visual Effects
- **Dual-Canvas Rendering System**
  - Background: Dynamic matrix rain/starfield that responds to hand velocity
  - Foreground: Hand skeleton, particles, ripples, and interactive effects
- **Interactive Effects**
  - Particle emission from fingertips with gravity physics
  - Radial shockwaves triggered by pinch gestures
  - Lightning arcs between hands (when closer than 150px)
  - Flowing gradient lines connecting corresponding fingertips
  - Animated mandala pattern from all 10 fingertips
- **Motion Blur** - Trailing effect on main canvas for smooth motion visualization

### Audio Integration
- **Continuous Hum** - Sine wave synthesizer modulated by:
  - Hand presence (mutes when no hands detected)
  - Distance between hands (frequency: 100-400 Hz, volume: 0.05-0.2)
- **Zap Sound** - Sawtooth oscillator triggered on pinch detection
- **Web Audio API** - Full control over oscillators, gains, and frequency envelopes

### UI & UX
- **Start Overlay** - Triggers AudioContext initialization (required for Web Audio)
- **HUD Panel** - Real-time display of:
  - Hands detected count
  - Frames per second (FPS)
  - Current gesture
  - Hand spread percentage
- **Theme Switcher** - Bottom-center button bar for live theme switching
- **Glass-morphism Design** - Frosted glass effect with backdrop blur

## 🚀 Quick Start

### Requirements
- **Modern Browser** - Chrome 90+, Firefox 88+, Safari 14.1+, Edge 90+
- **Webcam** - Camera permission required
- **HTTPS or Localhost** - Required for camera access

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd HandConnect-main
```

2. Serve the application (HTTPS required):
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (http-server)
npx http-server

# Using Live Server (VS Code Extension)
# Right-click index.html → Open with Live Server
```

3. Open in browser:
```
https://localhost:8000
```

4. **Grant Camera Permission** and click "Enter Experience"

## 📚 Code Architecture

### Global State Management
```javascript
currentHands[]        // Array of 2 hands max, each with 21 landmarks
handVelocities        // Float: average movement speed
currentTheme          // String: active color theme
particles[]           // Array: active particle objects
ripples[]             // Array: active shockwave objects
```

### Main Rendering Pipeline (60 FPS target)
1. **Background Pass** - Matrix rain effect with velocity-based speed modulation
2. **Physics Update** - Particle gravity, ripple expansion, fade-out
3. **Hand Detection** - Skeleton rendering, landmark drawing
4. **Cross-Hand Interactions** - Lightning, gradients, mandala
5. **Gesture Processing** - Pinch detection, spread calculation

### Key Functions

| Function | Purpose |
|----------|---------|
| `initMediaPipe()` | Initializes hand detection with MediaPipe |
| `initAudio()` | Creates Web Audio oscillators and gainNodes |
| `renderLoop()` | Main animation frame handler |
| `detectGestures()` | Processes pinch and spread recognition |
| `createParticles()` | Spawns physics-enabled particle objects |
| `createShockwave()` | Generates expanding ripple effects |
| `updateHum()` | Modulates audio frequency/volume based on hand distance |
| `drawBackground()` | Renders matrix rain with velocity mapping |
| `updatePhysics()` | Updates particle/ripple positions and life |

### Canvas Compositing Modes
- **Background Canvas**: Uses `destination-out` for fade trails
- **Main Canvas**: Uses `screen` blend mode for additive light effects (neon bloom)

## 🎮 How to Interact

### Gestures
1. **Pinch** - Bring thumb and index finger together
   - Creates shockwave effect
   - Triggers "zap" audio sound
   
2. **Hand Spread** - Open/close hand
   - Displays spread percentage
   - Updates gesture status

3. **Two-Hand Interactions** - Move hands close together
   - Lightning arcs appear between hands
   - Hum modulates by hand distance
   - Mandala pattern rotates

### Controls
- **Click theme buttons** to switch visual themes
- **Move hands** to trigger particle effects
- **Close/open hands** to see spread analysis

## 📊 Performance Considerations

### Optimizations Already Implemented
- Matrix rain rendered sparsely (only 5% of columns per frame)
- Particle/ripple limits (auto-remove when life reaches 0)
- Canvas double-buffering (bgCanvas + mainCanvas)
- RequestAnimationFrame for efficient scheduling

### Current Limitations
- MediaPipe hand detection: ~100-150ms latency
- Canvas rendering: CPU-bound (no GPU acceleration)
- Web Audio: Single audio context (browser limit)

## 🔧 Technology Stack

| Technology | Purpose |
|-----------|---------|
| **MediaPipe** | Hand detection & landmark tracking |
| **Canvas 2D API** | Real-time graphics rendering |
| **Web Audio API** | Audio synthesis & effects |
| **HTML5 Video** | Camera input stream |
| **CSS3 Backdrop Filter** | Glass-morphism UI effects |

## 📖 API Reference

### MediaPipe Results Structure
```javascript
results.multiHandLandmarks[handIndex][landmarkIndex]
// Returns: { x: 0-1, y: 0-1, z: -1 to 1 }
// 21 landmarks per hand (0=wrist, 4-8-12-16-20=fingertips)
```

### Particle Object
```javascript
{
  x, y,           // Position
  vx, vy,         // Velocity
  life: 0-1,      // Fade value
  color: string,  // CSS color
  size: number    // Radius in px
}
```

### Ripple Object
```javascript
{
  x, y,                    // Center position
  radius: number,          // Current radius
  maxRadius: number,       // Max expand distance
  life: 0-1,              // Fade value
  color: string           // CSS color
}
```

## 🎨 Customization

### Change Default Theme
```javascript
// In renderLoop(), find:
const glowColor = themes[currentTheme](time, handIndex, 2);
// currentTheme = 'Rainbow' (change to 'Cyberpunk', 'Lava', etc.)
```

### Modify Audio Parameters
```javascript
// Hum frequency range
const targetFreq = 100 + (1 - Math.min(dist, 1)) * 300;
// Change 100 = min frequency, 300 = max frequency

// Pinch detection threshold
const isPinching = dist < 0.05; // 5% of screen - make more/less sensitive
```

### Adjust Particle Physics
```javascript
// In updatePhysics():
p.vy += 0.1;        // Gravity strength (increase = faster fall)
p.life -= 0.02;     // Fade speed (increase = faster disappear)
```

## 🐛 Known Issues & Limitations

1. **Camera Permission** - Must reload page after granting permission on some browsers
2. **Audio Lag** - Web Audio API has inherent latency (~20-100ms)
3. **Mobile Performance** - Canvas rendering is CPU-intensive on mobile devices
4. **Hand Occlusion** - MediaPipe loses tracking when hands overlap significantly
5. **Low-Light Conditions** - Detection quality degrades in poor lighting

## 📝 Browser Compatibility

| Browser | Status | Notes |
|---------|--------|-------|
| Chrome 90+ | ✅ Fully Supported | Best performance |
| Firefox 88+ | ✅ Fully Supported | Slightly lower FPS |
| Safari 14.1+ | ⚠️ Partial Support | webkitAudioContext required |
| Edge 90+ | ✅ Fully Supported | Chromium-based |
| Mobile Browsers | ⚠️ Limited | Camera access may be restricted |

## 🚀 Deployment

### HTTPS Requirement
Camera and AudioContext require secure context (HTTPS):

```bash
# Deploy to Vercel (recommended)
vercel deploy

# Deploy to Netlify
netlify deploy

# Deploy to GitHub Pages
# Must enable GitHub Pages in repo settings
```

### Self-Hosted HTTPS
```bash
# Using Let's Encrypt + Node
npm install -g http-server
npx local-ssl-proxy --source 8443 --target 8000
```

## 📞 Support & Contributing

For issues or feature requests, please open an issue in the repository.

## 📄 License

MIT License - Feel free to use and modify this project

---

**Created with ✨ for hand tracking enthusiasts**

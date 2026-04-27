# 🖐️ Hand Gesture Recognition Guide

Complete documentation of all gesture detection features in Neon Aura AR.

---

## 📊 Gesture Summary

**Total Gestures: 30+**
- Basic Gestures: 5
- Game Gestures: 3 (Rock-Paper-Scissors)
- Victory/Peace: 2
- Thumbs: 2
- Pointing: 2
- Advanced Shapes: 6
- Number Signs: 3
- Hand Dynamics: 3
- Dual-Hand: 3

---

## 🎮 Basic Single-Hand Gestures

### 1. **PINCH** 📌
- **How**: Touch thumb and index finger tips together
- **Trigger**: Proximity < 5% of screen width
- **Effects**:
  - Creates expanding shockwave at pinch point
  - Emits 8 particles
  - Plays "zap" audio sound
  - Haptic vibration (30ms)
  - Visual display: "📌 PINCH!"
- **Detection**: `detectPinch(hand)`

### 2. **PEACE SIGN** ☮️
- **How**: Extend index and middle fingers (like the peace sign)
- **Criteria**: 
  - Index extended > 8% screen width from knuckle
  - Middle extended > 8% screen width
  - Ring and pinky closed
- **Effects**:
  - Emits 5 particles at index finger
  - Haptic vibration (30ms)
  - Visual display: "☮️ PEACE!"
- **Detection**: `detectPeaceSign(hand)`

### 3. **THUMBS UP** 👍
- **How**: Thumb points upward with fingers closed
- **Criteria**:
  - Thumb Y position < knuckle Y (pointing up)
  - All other fingers closed to palm
- **Effects**:
  - Creates shockwave at thumb position
  - Emits 10 particles
  - Haptic vibration (50ms)
  - Visual display: "👍 BOOST!"
- **Detection**: `detectThumbsUp(hand)`

### 4. **THUMBS DOWN** 👎
- **How**: Thumb points downward with fingers closed
- **Criteria**:
  - Thumb Y position > knuckle Y + 10% (pointing down)
  - All other fingers closed
- **Effects**:
  - Emits 7 particles
  - Haptic vibration (40ms)
  - Visual display: "👎 DOWN!"
- **Detection**: `detectThumbsDown(hand)`

### 5. **OK SIGN** 👌
- **How**: Form circle with thumb and index, other fingers extended
- **Criteria**:
  - Thumb-index distance < 5% (forming circle)
  - Middle, ring, pinky extended
- **Effects**:
  - Emits 3 particles
  - Haptic vibration (25ms)
  - Visual display: "👌 OK!"
- **Detection**: `detectOKSign(hand)`

---

## 🎮 Rock-Paper-Scissors Game

### 6. **ROCK** ✊
- **How**: Make a closed fist with all fingers and thumb closed
- **Criteria**:
  - All finger tips < 12% distance from palm
  - Thumb closed to knuckle
- **Effects**:
  - Creates shockwave
  - Emits 6 particles
  - Haptic vibration (40ms)
  - Visual display: "✊ ROCK!"
- **Detection**: `detectRockSign(hand)`

### 7. **PAPER** 📄
- **How**: All fingers and thumb extended and spread
- **Criteria**:
  - Index extended > 8%
  - Middle extended > 8%
  - Ring extended > 8%
  - Pinky extended > 8%
- **Effects**:
  - Emits 12 particles (most intense)
  - Haptic vibration (25ms)
  - Visual display: "📄 PAPER!"
- **Detection**: `detectPaperSign(hand)`

### 8. **SCISSORS** ✂️
- **How**: Index and middle extended and separated (scissor motion)
- **Criteria**:
  - Index and middle extended
  - Ring and pinky closed < 6%
  - Index-middle separation > 8%
- **Effects**:
  - Creates shockwave
  - Plays zap audio
  - Haptic vibration (35ms)
  - Visual display: "✂️ SCISSORS!"
- **Detection**: `detectScissorsSign(hand)`

---

## ✌️ Victory & Peace Variations

### 9. **VICTORY SIGN** 🎉
- **How**: Index and middle extended in V-shape, ring and pinky closed
- **Criteria**:
  - Index extended > 10%
  - Middle extended > 10%
  - Ring and pinky closed < 6%
  - Separation between index-middle > 10%
- **Effects**:
  - Emits 8 particles
  - Creates shockwave
  - Haptic vibration (45ms)
  - Visual display: "🎉 VICTORY!"
- **Detection**: `detectVictorySign(hand)`

---

## ☝️ Pointing Gestures

### 10. **POINTING UP** ☝️
- **How**: Only index finger extended upward
- **Criteria**:
  - Index extended > 10%
  - Middle, ring, pinky closed < 6%
  - Index Y position < wrist Y (pointing up)
- **Effects**:
  - Haptic vibration (20ms)
  - Visual display: "☝️ POINT UP!"
- **Detection**: `detectPointingUp(hand)`

### 11. **POINTING RIGHT** 👉
- **How**: Only index finger extended to the right
- **Criteria**:
  - Index extended > 10%
  - Other fingers closed
  - Index X position > palm X + 15%
- **Effects**:
  - Haptic vibration (20ms)
  - Visual display: "👉 POINT RIGHT!"
- **Detection**: `detectPointingRight(hand)`

---

## 🖖 Advanced Hand Shapes

### 12. **SPOCK SIGN** 🖖
- **How**: Star Trek "Live Long and Prosper" - V-shape with both hand sides
- **Criteria**:
  - Index extended > 10%
  - Middle extended > 10%
  - Ring extended > 8%
  - Pinky extended > 8%
  - Large gap between index-middle > 12%
  - Large gap between ring-pinky > 12%
- **Effects**:
  - Creates shockwave
  - Emits 12 particles
  - Haptic vibration (60ms - STRONGEST)
  - Visual display: "🖖 SPOCK!"
- **Detection**: `detectSpock(hand)`

### 13. **LOVE SIGN** ❤️
- **How**: Heart shape (thumb + index extended, middle + ring closed, pinky extended)
- **Criteria**:
  - Thumb extended > 10%
  - Index extended > 8%
  - Pinky extended > 8%
  - Ring and middle closed < 5%
- **Effects**:
  - Emits 15 particles (MOST PARTICLES)
  - Particles colored pink (#ff69b4)
  - Haptic vibration (35ms)
  - Visual display: "❤️ LOVE!"
- **Detection**: `detectLoveSign(hand)`

### 14. **CLAW** 🐾
- **How**: All fingers extended and spread wide
- **Criteria**:
  - All fingers extended > 15% from palm
  - Thumb extended > 10%
  - Wide spread between index-pinky > 30%
- **Effects**:
  - Creates shockwave
  - Haptic vibration (50ms)
  - Visual display: "🐾 CLAW!"
- **Detection**: `detectClaw(hand)`

### 15. **HOLY SIGN** ⛪
- **How**: Separated index and middle (wide holy sign)
- **Criteria**:
  - Index and middle extended > 8%
  - Ring and pinky closed < 5%
  - Large separation > 10%
- **Effects**:
  - Emits 10 particles
  - Haptic vibration (40ms)
  - Visual display: "⛪ HOLY!"
- **Detection**: `detectHolySign(hand)`

### 16. **GUN GESTURE** 🔫
- **How**: Thumb and index extended, other fingers closed (like a gun)
- **Criteria**:
  - Index extended > 8%
  - Thumb extended > 8%
  - Middle closed < 5%
  - Ring closed < 5%
  - Pinky closed < 5%
  - Thumb-index separation > 8%
- **Effects**:
  - Plays zap audio
  - Creates shockwave at index position
  - Haptic vibration (45ms)
  - Visual display: "🔫 BANG!"
- **Detection**: `detectGun(hand)`

---

## 🔢 Number Signs

### 17. **THREE FINGERS** 🤟
- **How**: Index, middle, and ring extended; pinky and thumb closed
- **Criteria**:
  - Index extended > 8%
  - Middle extended > 8%
  - Ring extended > 8%
  - Pinky closed < 5%
  - Thumb closed < 10%
- **Effects**:
  - Emits 9 particles
  - Haptic vibration (30ms)
  - Visual display: "🤟 THREE!"
- **Detection**: `detectThreeFingers(hand)`

### 18. **FOUR FINGERS** 4️⃣
- **How**: All four fingers extended, thumb closed
- **Criteria**:
  - All fingers extended > 15% from palm
  - Thumb closed < 8%
- **Effects**:
  - Emits 11 particles
  - Haptic vibration (35ms)
  - Visual display: "4️⃣ FOUR!"
- **Detection**: `detectFour(hand)`

### 19. **FIST** ✊
- **How**: All fingers and thumb completely closed
- **Criteria**:
  - All finger tips < 12% distance from palm
- **Effects**:
  - No particles
  - Haptic vibration (None)
  - Visual display: "✊ FIST"
- **Detection**: `detectFist(hand)`

### 20. **OPEN PALM** 🖐️
- **How**: All fingers completely extended and wide spread
- **Criteria**:
  - Index-pinky spread > 25%
- **Effects**:
  - No particles
  - Visual display: "🖐️ OPEN"
- **Detection**: `detectOpenPalm(hand)`

---

## 📏 Hand Dynamics (Single Hand)

### 21. **HAND SIZE** 
- **Small** 🤏
  - Hand size < 15% screen width
  - Visual display: "🤏 SMALL"
  
- **Medium** (Default)
  - Hand size 15-25% screen width
  
- **Large** 📏
  - Hand size > 25% screen width
  - Visual display: "📏 LARGE"

- **Detection**: `detectHandSize(hand)`

### 22. **HAND TILT** ⬆️⬇️⬅️➡️
- **Up Tilt** ⬆️
  - Hand moving upward
  - Visual display: "⬆️ UP"
  
- **Down Tilt** ⬇️
  - Hand moving downward
  - Visual display: "⬇️ DOWN"
  
- **Left Tilt** ⬅️
  - Hand moving left
  - Visual display: "⬅️ LEFT"
  
- **Right Tilt** ➡️
  - Hand moving right
  - Visual display: "➡️ RIGHT"

- **Threshold**: Movement > 1% screen width per frame
- **Detection**: `detectHandTilt(hand, previousHand)`

### 23. **HAND ROTATION** 🔄🔃
- **Clockwise** 🔄
  - Hand rotating clockwise
  - Visual display: "🔄 CLOCKWISE"
  
- **Counter-Clockwise** 🔃
  - Hand rotating counter-clockwise
  - Visual display: "🔃 COUNTERCLOCKWISE"

- **Threshold**: Rotation > 2° per frame
- **Detection**: `detectHandRotation(hand, previousHand)`

---

## 🤝 Dual-Hand Gestures (2 Hands Detected)

### 24. **HANDS TOUCHING** 🤝
- **How**: Both hands very close together
- **Criteria**: Palm-to-palm distance < 10%
- **Effects**:
  - Creates shockwave at hand 1 position
  - Haptic vibration (60ms - STRONG)
  - Visual display: "🤝 TOUCHING!"
- **Detection**: `detectHandsDistance(hand1, hand2) === 'TOUCHING'`

### 25. **HANDS CLOSE** 🤐
- **How**: Hands in close proximity
- **Criteria**: Palm-to-palm distance 10-20%
- **Effects**:
  - Visual display: "🤐 CLOSE!"
- **Detection**: `detectHandsDistance(hand1, hand2) === 'CLOSE'`

### 26. **HANDS MEDIUM DISTANCE** 🤨
- **How**: Hands at medium distance
- **Criteria**: Palm-to-palm distance 20-40%
- **Effects**:
  - Visual display: "🤨 MEDIUM"
- **Detection**: `detectHandsDistance(hand1, hand2) === 'MEDIUM'`

### 27. **HANDS CROSSING** ❌
- **How**: Hands overlapping/crossing
- **Criteria**: > 5 landmarks overlap (< 10% distance)
- **Effects**:
  - Haptic vibration (35ms)
  - Visual display: "❌ CROSSING!"
- **Detection**: `detectHandsCrossing(hand1, hand2)`

### 28. **HANDS APPROACHING** 🤝
- **How**: Both hands moving toward each other
- **Criteria**: Palm distance < 20%
- **Effects**: Monitored but no special visual feedback
- **Detection**: `detectHandsApproaching(hand1, hand2)`

---

## 🎯 Gesture Spread Percentage

### 29. **HAND SPREAD %**
- **Calculation**: Distance from index tip to pinky tip
- **Display**: Real-time percentage (0-100%)
- **Location**: Bottom-left corner UI
- **Use Case**: Measure hand openness/closure level

---

## 🎨 Visual & Audio Feedback

### Particle Effects
- **Pinch**: 8 particles, color-themed
- **Rock**: 6 particles
- **Paper**: 12 particles (MOST)
- **Love**: 15 particles, pink color
- **Spock**: 12 particles
- **Claw**: 8 particles
- **Victory**: 8 particles
- **Three Fingers**: 9 particles
- **Four Fingers**: 11 particles

### Haptic Vibration Intensity
- **Lightest** (20ms): Pointing gestures
- **Light** (25ms): OK, Paper
- **Medium** (30ms): Pinch, Peace, Three Fingers
- **Medium-Strong** (35ms): Scissors, Love, Crossing Hands, Four Fingers
- **Strong** (40ms): Rock, Thumbs Down, Holy
- **Stronger** (45ms): Victory, Gun
- **Strongest** (50ms): Thumbs Up, Claw
- **MAXIMUM** (60ms): Spock, Hands Touching

### Audio Effects
- **Zap Sound**: Pinch, Scissors, Gun (sawtooth wave, 800→40 Hz)
- **Hum Modulation**: All two-hand interactions

---

## ⚙️ Technical Details

### Gesture Detection Parameters

| Parameter | Default | Unit |
|-----------|---------|------|
| Pinch Threshold | 0.05 | % of screen |
| Extension Threshold | 0.08 | % of screen |
| Closure Threshold | 0.05 | % of screen |
| Separation Threshold | 0.1 | % of screen |
| Hand Size Multiplier | 300 | Factor |
| Gesture Cooldown | 300 | ms |
| Hand Tilt Threshold | 1 | % movement |
| Hand Rotation Threshold | 2 | degrees |

### Performance Optimization
- **Gesture Cooldown**: 300ms prevents rapid re-triggering
- **Previous Hand Storage**: Tracks for dynamics detection
- **Early Returns**: Stops processing after first gesture match
- **Conditional Checks**: Hand smoothing filters noise

---

## 🎮 Gesture Combinations (Future)

These combinations can be detected with multiple hands:

**Planned Advanced Gestures:**
- Hand clap (both hands approaching & touching)
- Prayer hands (palms together, fingers intertwined)
- Mirror gestures (left hand mirrors right hand)
- Distance-based interactions (gravity simulation)
- Multi-hand choreography

---

## 📱 Mobile Considerations

**Gesture Detection Accuracy on Mobile:**
- ✅ Excellent: Pinch, Rock, Paper, Scissors, Fist, Open Palm
- ✅ Good: Thumbs, Pointing, Peace
- ⚠️ Moderate: Spock, Love, Advanced shapes
- ❌ Challenging: Fine-grained hand dynamics, subtle rotations

**Recommendations:**
- Use larger, more exaggerated gestures on mobile
- Reduce gesture cooldown time
- Use haptic feedback to confirm detection

---

## 🔍 Debugging Gestures

**Enable Performance Monitor** (Press P):
- FPS: Should be > 30
- Frame Time: Should be < 33ms
- Particles: Shows active particle count
- Memory: Shows heap usage

**Visual Indicators:**
- Gesture name displayed in HUD
- Real-time spread percentage
- Particle emissions show detection accuracy
- Haptic feedback confirms recognition

---

## 📈 Gesture Statistics

**Most Intensive:**
1. Spock Sign (60ms haptic, 12 particles, shockwave)
2. Love Sign (15 particles, custom color)
3. Paper (12 particles)

**Least Intensive:**
1. Pointing Up/Right (20ms haptic only)
2. Hand Size (no effects)
3. Hands at medium distance (visual only)

**Most Likely to Trigger:**
1. Pinch (easiest, fastest)
2. Fist (very stable)
3. Open Palm (obvious)

**Most Entertaining:**
1. Spock (strongest feedback)
2. Love (pink particles, romantic)
3. Gun (audio + shockwave combo)

---

## 🚀 Tips for Best Results

1. **Good Lighting**: Ensure adequate lighting for hand detection
2. **Stable Camera**: Keep camera steady for accurate tracking
3. **Clear Gestures**: Use exaggerated movements
4. **Appropriate Distance**: 30-120cm from camera
5. **Hand Visibility**: Keep hands fully in frame
6. **Smooth Movements**: Slow, deliberate gestures work best

---

## 📞 Support

If a gesture isn't being detected:
1. Check hand visibility (in camera frame)
2. Try slower, more exaggerated movement
3. Ensure adequate lighting
4. Check mobile device mode setting
5. Review gesture criteria in documentation

---

**Last Updated**: April 27, 2026
**Total Gestures Documented**: 30+
**Hand Tracking Provider**: MediaPipe Hands
**Audio System**: Web Audio API
**Haptic System**: Vibration API


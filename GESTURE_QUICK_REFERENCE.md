# 🖐️ GESTURE QUICK REFERENCE CARD

## ⚡ QUICKEST GESTURES TO TRY

```
🤚 OPEN PALM     👊 ROCK/FIST      ✂️ SCISSORS
📌 PINCH         📄 PAPER          ☮️ PEACE
👍 THUMBS UP     👎 THUMBS DOWN    🎉 VICTORY
```

---

## 📱 BY HAND POSITION

### THUMB GESTURES
- **Thumb Up** ↑ → `👍` Boost!
- **Thumb Down** ↓ → `👎` Down!
- **Thumb + Index Circle** → `👌` OK!
- **Thumb + Index Touch** → `📌` Pinch!
- **Thumb + Index Gun** → `🔫` Bang!
- **Thumb + Pinky + Index** → `❤️` Love!

### INDEX FINGER GESTURES
- **Index Only Up** ↑ → `☝️` Point Up!
- **Index Only Right** → → `👉` Point Right!
- **Index + Middle (V)** → `✌️` Peace!
- **Index + Middle (Wide V)** → `🎉` Victory!
- **Index + Middle + Ring** → `🤟` Three!

### HAND STATES
- **All Closed** ✊ → `✊` Rock!
- **All Open** 🖐️ → `📄` Paper!
- **Fist** 👊 → `✊` Fist!
- **Open Hand** → `🖐️` Open!

### ADVANCED SHAPES
- **Spock V** → `🖖` Spock! (60ms haptic)
- **Claw** → `🐾` Claw!
- **Holy Sign** → `⛪` Holy!
- **Gun Gesture** → `🔫` Bang!

---

## 🎮 GAME-READY GESTURES

### Rock-Paper-Scissors
```
✊ ROCK       vs        📄 PAPER     vs      ✂️ SCISSORS
Closed Fist             All Open            Index+Middle
```

### Celebration Gestures
```
🎉 VICTORY    🤟 THREE FINGERS    4️⃣ FOUR FINGERS
V-Shape           3 Extended             4 Extended
```

---

## 🤝 TWO-HAND GESTURES

| Gesture | Emoji | How | Haptic |
|---------|-------|-----|--------|
| Touching | 🤝 | Palms < 10% | 60ms ⭐ |
| Close | 🤐 | 10-20% apart | None |
| Crossing | ❌ | Hands overlap | 35ms |

---

## 📊 FEEDBACK CHART

```
HAPTIC (Vibration Intensity)
┌─────────────────────────────────────┐
│ 20ms ▮▮▮ Point                      │
│ 25ms ▮▮▮▮ OK, Paper                 │
│ 30ms ▮▮▮▮▮ Pinch, Peace, Three     │
│ 35ms ▮▮▮▮▮▮ Scissors, Love, Four   │
│ 40ms ▮▮▮▮▮▮▮ Rock, Holy, Down      │
│ 45ms ▮▮▮▮▮▮▮▮ Victory, Gun         │
│ 50ms ▮▮▮▮▮▮▮▮▮ Up, Claw            │
│ 60ms ▮▮▮▮▮▮▮▮▮▮ SPOCK, TOUCHING    │
└─────────────────────────────────────┘

PARTICLE COUNT
┌─────────────────────────────────────┐
│ 0  ────── Fist, Open                │
│ 3  ▮ OK                             │
│ 5  ▮▮ Peace                         │
│ 6  ▮▮▮ Rock                         │
│ 7  ▮▮▮▮ Down                        │
│ 8  ▮▮▮▮▮ Victory, Pinch             │
│ 9  ▮▮▮▮▮▮ Three                     │
│ 10 ▮▮▮▮▮▮▮ Holy, Up                 │
│ 11 ▮▮▮▮▮▮▮▮ Four                    │
│ 12 ▮▮▮▮▮▮▮▮▮ Paper, Spock           │
│ 15 ▮▮▮▮▮▮▮▮▮▮▮ LOVE (PINK)          │
└─────────────────────────────────────┘
```

---

## ⌨️ KEYBOARD SHORTCUTS

| Key | Action |
|-----|--------|
| **F** | 🖥️ Fullscreen |
| **S** | ⚙️ Settings |
| **P** | 📊 Performance Monitor |
| **H** | ❓ Help (This) |
| **R** | 🔄 Reset Effects |
| **T** | 👁️ Toggle HUD |
| **M** | 📱 Mobile Mode |

---

## 🎨 GESTURE COLORS

| Gesture | Particle Color |
|---------|---|
| Theme-based | Most gestures use current theme color |
| Love | 💗 Special Pink (#ff69b4) |
| Two-Hand | 🌈 Rainbow themed |

---

## 📏 DETECTION ZONES

```
HIGH ACCURACY (> 95%)
├─ Pinch
├─ Rock/Paper
├─ Scissors
├─ Open/Fist
├─ Thumbs
└─ Pointing

MEDIUM ACCURACY (80-95%)
├─ Peace/Victory
├─ Three/Four Fingers
├─ OK Sign
├─ Claw
└─ Hand Size

LOW ACCURACY (50-80%) ⚠️
├─ Spock
├─ Love
├─ Holy
├─ Hand Rotation
└─ Hand Dynamics
```

---

## 💡 DETECTION TIPS

✅ **DO**
- Use clear, exaggerated gestures
- Keep hands in good lighting
- Make gestures slowly and deliberately
- Use whole hand movements
- Ensure both hands fully visible (2-hand)

❌ **DON'T**
- Use very quick/sudden movements
- Obscure fingers with other objects
- Point fingers at camera (too close)
- Use multiple gestures simultaneously
- Mix with other hand movements

---

## 🎯 GESTURE DISTANCES (Screen Width %)

```
Pinch Detection:        < 5%
Extension Required:     > 8%
Closure Required:       < 5-6%
Large Separation:       > 10%
Touching (2-Hand):      < 10%
Close (2-Hand):         10-20%
Spread Detection:       > 25%
Far (2-Hand):           > 40%
```

---

## ⏱️ TIMING NOTES

| Parameter | Time |
|-----------|------|
| Gesture Cooldown | 300ms (prevent re-trigger) |
| Haptic Duration | 20-60ms |
| Particle Lifetime | ~1 second |
| Trail Persistence | 30 points |
| Hand Smoothing | 0.7 alpha (adjustable) |

---

## 🎮 GAME USES

**Selection Menu**
- Use: `Pinch` to select
- Navigate: `Point Up/Right`

**Rock-Paper-Scissors**
- Show: `Rock` ✊, `Paper` 📄, `Scissors` ✂️
- Win/Lose: `Thumbs Up/Down`

**Action Game**
- Jump: `Thumbs Up`
- Attack: `Gun` 🔫
- Dodge: `Point` ☝️
- Special: `Spock` 🖖

**Music/Rhythm**
- Each finger plays note (1-5)
- Hand height = volume
- Hand position = pitch

---

## 🎓 LEARNING PATH

**Beginner (Easiest)**
1. Pinch
2. Rock/Paper/Scissors
3. Thumbs Up/Down
4. Open/Fist

**Intermediate**
5. Peace/Victory
6. Pointing
7. OK Sign
8. Three/Four Fingers

**Advanced (Hardest)**
9. Spock
10. Love
11. Hand Rotation
12. Dual-Hand

---

## 🚀 PERFORMANCE TARGETS

| Device | FPS | Particles | Gestures |
|--------|-----|-----------|----------|
| Desktop | 60 | 200 | All ✅ |
| Laptop | 45-60 | 100 | Most ✅ |
| Mobile | 30-45 | 30-50 | Basic ✅ |
| Low-End | 20-30 | 10 | Basic ⚠️ |

---

## 🔍 TROUBLESHOOTING

**Gesture Not Detecting?**
- ❌ Fingers too close/far
- ✅ Use slower, clearer gestures
- ✅ Check hand is in frame
- ✅ Verify lighting is good
- ✅ Ensure fingers fully extended/closed

**Haptic Not Working?**
- ✅ Check device supports vibration
- ✅ Check system notifications volume
- ✅ Try reloading page
- ✅ Check mobile mode setting

**Lag/Performance Issues?**
- ✅ Press P for performance monitor
- ✅ Reduce particle count in settings
- ✅ Disable trails in settings
- ✅ Press M for mobile mode
- ✅ Check browser tab is active

---

## 📱 MOBILE DEVICE SUPPORT

| Feature | Desktop | Tablet | Phone |
|---------|---------|--------|-------|
| Gesture Detection | ✅ 95% | ✅ 90% | ✅ 80% |
| Haptic Feedback | ✅ Yes | ✅ Yes | ✅ Yes |
| Fullscreen | ✅ Yes | ✅ Yes | ✅ Yes |
| Trail Effects | ✅ Yes | ⚠️ Limited | ❌ No |
| Audio | ✅ Yes | ✅ Yes | ✅ Yes |

---

## 🎵 AUDIO FEATURES

**Hum Sound**
- Frequency: 100-400 Hz
- Based on: Distance between hands
- Volume: 0.05-0.2

**Zap Sound**
- Triggered: Pinch, Scissors, Gun
- Sound: Sawtooth wave 800→40Hz
- Duration: 150ms

**Finger Notes**
- Wrist (C3): 130.81 Hz
- Thumb (E3): 164.81 Hz
- Index (G3): 196.00 Hz
- Middle (B3): 246.94 Hz
- Ring (E4): 329.63 Hz
- Pinky (G4): 392.00 Hz

---

## 🎨 VISUAL EFFECTS

**Shockwaves**
- Expanding circles
- Color-themed
- Fade-out effect

**Particles**
- Physics-based
- Gravity enabled
- Color variations
- Life decay

**Trails**
- Index finger tracking
- Gradient fade
- Configurable length

---

## 💾 DATA STORED

**Per Frame**
- Current hand positions (21 × 2 hands)
- Previous hand positions (21 × 2 hands)
- Active particles (count varies)
- Active ripples (count varies)

**Settings**
- Gesture thresholds
- Particle limits
- Audio volumes
- Smoothing factors

---

## 🏆 TIPS FOR BEST RESULTS

1. **Start Simple** - Master pinch before complex shapes
2. **Use Both Hands** - More gestures available
3. **Exaggerate** - Larger movements are easier to detect
4. **Keep Lighting** - Well-lit hands = better accuracy
5. **Practice** - Gestures improve with familiarity
6. **Use Feedback** - Watch haptics & particles for confirmation
7. **Check HUD** - Real-time gesture display helps learning

---

**Version**: 1.0
**Last Updated**: April 27, 2026
**Total Gestures**: 30+


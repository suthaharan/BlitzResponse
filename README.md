# Blitz Response - Utility Dodge & Clear

A fast-paced VALORANT-themed reflex game designed for arcade-style booth fun at Cloud 9 and JetBrains events.

## Project Description

**Blitz Response** is an intuitive, mouse-only reflex game where players must quickly identify and clear enemy utility (smokes, mollies, trips, flashes) while avoiding friendly utility. The game features increasing difficulty, combo multipliers, and a scoring system that rewards accuracy and speed.

### Core Gameplay
- **Duration**: 60-90 seconds per round
- **Mechanics**: Click to clear enemy utility, avoid clicking friendly utility
- **Progression**: Increasing speed and difficulty
- **Scoring**: Points for correct clears, combo bonuses for streaks, penalties for friendly fire

## Basic Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Game Application                      │
├─────────────────────────────────────────────────────────┤
│                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │  Game Loop   │  │  Renderer    │  │  Input       │  │
│  │  Manager     │  │  (Canvas)    │  │  Handler     │  │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  │
│         │                  │                  │          │
│  ┌──────▼──────────────────▼──────────────────▼──────┐  │
│  │           Game State Manager                      │  │
│  │  - Timer                                           │  │
│  │  - Score                                           │  │
│  │  - Combo Multiplier                                │  │
│  └──────┬────────────────────────────────────────────┘  │
│         │                                                 │
│  ┌──────▼────────────────────────────────────────────┐  │
│  │           Utility Spawner                         │  │
│  │  - Enemy Utility (Smokes, Mollies, Trips, Flashes)│  │
│  │  - Friendly Utility                               │  │
│  │  - Spawn Rate Controller                          │  │
│  └──────┬────────────────────────────────────────────┘  │
│         │                                                 │
│  ┌──────▼────────────────────────────────────────────┐  │
│  │           Collision Detection                     │  │
│  │  - Click Detection                                │  │
│  │  - Utility Type Identification                   │  │
│  └──────┬────────────────────────────────────────────┘  │
│         │                                                 │
│  ┌──────▼────────────────────────────────────────────┐  │
│  │           localStorage Manager                    │  │
│  │  - Leaderboard (Top 10)                          │  │
│  │  - High Score Tracking                           │  │
│  └───────────────────────────────────────────────────┘  │
│                                                           │
└─────────────────────────────────────────────────────────┘
```

## Software Used

### Core Technologies
- **Single HTML File** - Everything in one file (HTML, CSS, JavaScript)
- **HTML5 Canvas API** - Rendering game graphics
- **Vanilla JavaScript (ES6+)** - Game logic and interactivity
- **CSS3** - UI styling and animations
- **Font Awesome** - Icons for utility types (CDN)
- **localStorage API** - Score and leaderboard persistence

### No Build Tools Required
- **Zero Dependencies** - No npm, no build process
- **Direct Deployment** - Just upload the HTML file
- **Fast Loading** - No bundling overhead

### Asset Sources (All Free & Legal)
- **Font Awesome** - Icons (CDN, no attribution needed)
- **Google Fonts** - Typography (Orbitron, Rajdhani, Exo 2)
- **Freesound.org** - Sound effects (CC0/CC BY)
- **Kenney.nl** - Game sound packs (Public Domain)
- **Mixkit.co** - High-quality sound effects

### Attribution
- See **CREDITS.txt** file for complete asset attribution
- All assets used are under Creative Commons or open licenses
- Credits menu available in-game via Settings → Credits

### Deployment
- **GitHub Pages** - Upload single HTML file
- **Any Static Hosting** - Netlify, Vercel, Cloudflare Pages
- **Local File** - Can run directly from file system

## Feature Description

### Core Features
1. **Utility Spawning System**
   - Random spawn of enemy and friendly utility
   - Increasing spawn rate over time
   - Visual distinction between enemy and friendly utility

2. **Click Detection**
   - Precise mouse click hit detection
   - Instant feedback on click
   - Visual effects for successful clears

3. **Scoring System**
   - Base points for each correct clear
   - Combo multiplier for consecutive correct clicks
   - Penalty deduction for friendly fire
   - Real-time score display

4. **Progressive Difficulty**
   - Speed increases over time
   - More utility spawns as game progresses
   - Maintains playability while challenging players

5. **Visual Feedback**
   - Clear visual distinction between utility types
   - Animation effects for clears
   - Combo indicator
   - Timer countdown

### UI Features
- Start screen with instructions
- Game over screen with final score
- Local leaderboard (localStorage) - Top 10 scores
- Responsive design for different screen sizes
- Cloud9 & JetBrains branded theme

### Brand Integration
- **Cloud9 Blue** (#03A9F4) as primary color
- **JetBrains Dark Theme** (#2B2B2B background)
- **C9 Logo** in corner
- **Junie Mascot** as helper character
- Enemy utilities = opponent team colors
- Friendly utilities = C9 blue with C9 agent icons

## Playing Steps

1. **Launch the Game**
   - Open the game in a web browser
   - Click "Start Game" button

2. **Gameplay**
   - Watch for utility appearing on screen
   - Click on **enemy utility** (red/opponent colored) to clear it
   - **Avoid clicking** on friendly utility (blue/teammate colored)
   - Build combos by clearing multiple enemy utility in succession
   - Game lasts 60-90 seconds

3. **Scoring**
   - Earn points for each correct clear
   - Combo multiplier increases with consecutive correct clicks
   - Lose points for clicking friendly utility (breaks combo)
   - Aim for the highest score possible

4. **Game Over**
   - View your final score
   - See if you beat your high score
   - Click "Play Again" to restart

## Future Steps

### Phase 1: Core Development (Week 1-2)
- [ ] Set up project structure and build pipeline
- [ ] Implement game loop and canvas rendering
- [ ] Create utility spawning system
- [ ] Implement click detection and collision
- [ ] Add scoring and combo system
- [ ] Create basic UI (start screen, game over)

### Phase 2: Polish & Visuals (Week 2-3)
- [ ] Design and implement VALORANT-themed assets
- [ ] Add particle effects and animations
- [ ] Implement sound effects and background music
- [ ] Create visual feedback for combos
- [ ] Add difficulty progression tuning

### Phase 3: Booth Optimization (Week 3-4)
- [ ] Optimize for touch screens (tablet mode)
- [ ] Add kiosk mode (auto-restart, fullscreen)
- [ ] Implement leaderboard system (local/cloud)
- [ ] Add QR code for sharing scores
- [ ] Performance optimization for smooth 60fps

### Phase 4: Advanced Features (Priority Order)
- [ ] **Local Leaderboard** - localStorage for top scores (Top 10)
- [ ] **Difficulty Progression** - Speed increases every 15 seconds
- [ ] **Power-ups** - Temporary 2x score, freeze time, clear all
- [ ] **Achievements** - "C9 Pro" for 50+ combo, "Perfect Retake" for no mistakes
- [ ] Social sharing integration (optional)
- [ ] Analytics tracking for booth engagement (optional)

## Target Market

### Primary Audience
- **Gaming Event Attendees** - Cloud 9 and JetBrains booth visitors
- **VALORANT Fans** - Players familiar with the game's utility mechanics
- **Casual Gamers** - Easy-to-learn, quick gameplay appeals to all skill levels

### Use Cases
1. **Event Booths** - Interactive demo at gaming conventions and tech events
2. **Community Events** - Engagement tool for VALORANT community gatherings
3. **Streaming** - Content for Cloud 9 streamers and content creators
4. **Marketing** - Brand awareness tool showcasing Cloud 9's connection to VALORANT

### Key Demographics
- Age: 16-35 (primary gaming demographic)
- Interest: Esports, competitive gaming, VALORANT
- Engagement: Short attention span, social media active
- Platform: Web-based (accessible on any device)

### Success Metrics
- **Engagement**: Average play time per session
- **Retention**: Return players at booth
- **Social**: Shares and screenshots of high scores
- **Brand**: Association with Cloud 9 and VALORANT


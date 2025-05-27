# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a browser-based UFO catcher (crane game) implemented as a single HTML file with inline CSS and JavaScript. The game simulates a Japanese arcade claw machine where players catch prizes.

## Architecture

The entire application is contained in `ufo-catcher.html`:
- **Lines 7-185**: CSS styling and animations
- **Lines 188-211**: HTML structure 
- **Lines 213-388**: JavaScript game logic

Key architectural decisions:
- Single-file architecture for simplicity and portability
- No build tools or external dependencies
- Event-driven game loop using DOM manipulation
- CSS transitions for smooth animations

## Development Commands

```bash
# Run the game
open ufo-catcher.html  # macOS
# or simply open the file in any web browser

# No build, test, or lint commands - this is a simple HTML file
```

## Game Components

1. **Claw Machine System**
   - Position tracking: `clawPosition` (0-100%)
   - State management: `isDropping`, `gameActive`
   - Animation timing: 500ms for each movement phase

2. **Prize System**
   - Three types: alien (green), robot (pink), star (yellow)
   - Random positioning and point values (10-30 points)
   - Collision detection based on pixel distances

3. **Control System**
   - Keyboard: Arrow keys for movement, Space/Down for drop
   - Mouse: Click buttons for all controls
   - Movement restricted during claw operations

## Code Patterns

- Prize catching logic uses getBoundingClientRect() for collision detection (line 310-336)
- CSS classes toggle for animations (`.open` class for claw state)
- All game state stored in global variables for simplicity
- Prize removal uses opacity transition before DOM removal